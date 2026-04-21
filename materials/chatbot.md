# Designing a chatbot in Sarvam

- Create an account in [Sarvam](https://login.sarvam.ai/welcome)

- get [API key](https://dashboard.sarvam.ai/)

- open [Google Colab](https://colab.research.google.com/)

- save your API key in `secrets` tab in Google Colab

securely in Google Colab, you should use Colab's **Secrets** feature. This allows you to store sensitive information like API keys or tokens without embedding them directly in your code, which is important for security and when sharing notebooks.

1.  **Open the Secrets Panel:** In the left sidebar of your Colab notebook, click on the **"🔑 Secrets"** icon (it looks like a key).
2.  **Add a new secret:** Click the **"+ Add new secret"** button.
3.  **Name the secret:** For your `Sarvam` API key, you could name it `YOUR_AUTHTOKEN` (or any other descriptive name you prefer, but remember it for later).
4.  **Enter the secret value:** Paste your `Sarvam` API key into the "Value" field.
5.  **Save:** Click "Save secret".

Once saved, you can access this secret in your Python code using `from google.colab import userdata` and then `token = userdata.get('YOUR_AUTHTOKEN')` (replacing `'YOUR_AUTHTOKEN'` with the name you gave your secret).



- type the following code in Colab

```python
'''
Sarvam voice model starter kit

Documentation:
- https://docs.sarvam.ai/api-reference-docs/getting-started/quickstart

Installation:

    python -m venv sarvam_venv

    source sarvam_venv/bin/activate

    pip install -r requirements_sarvam.txt

Usage:
    python sarvam_voice_model.py
    
Author: Soumya Banerjee

'''

from sarvamai import SarvamAI
import dotenv
import os
import logging
import wave
import sounddevice as sd
import numpy as np

# Load environment variables from .env file
# CAUTION: add SARVAM_API_KEY to .env file before running this code
# Also please add .env to .gitignore to avoid pushing your API key to github
dotenv.load_dotenv()
client = SarvamAI(
    api_subscription_key=os.getenv("SARVAM_API_KEY")
)

# create wav file from mic 
def record_wav(filename="hello.wav", seconds=5, samplerate=16000):
    '''
    record audio from mic and save file
    '''
    print(f"Recording for {seconds} seconds... speak now")
    audio = sd.rec(
        int(seconds * samplerate),
        samplerate=samplerate,
        channels=1,
        dtype="int16",
    )
    sd.wait()

    with wave.open(filename, "wb") as wf:
        wf.setnchannels(1)
        wf.setsampwidth(2)  # int16 = 2 bytes
        wf.setframerate(samplerate)
        wf.writeframes(audio.tobytes())

    print(f"Saved {filename}")

record_wav(filename="audio.wav",
           seconds=5,
           samplerate=16000)    

str_mode = "translate" # or "transcribe", "verbatim", "translit", "codemix"

response = client.speech_to_text.transcribe(
    file = open("audio.wav", "rb"),
    model = "saaras:v3",
    mode = str_mode
    # mode="transcribe" # or "translate", "verbatim", "translit", "codemix"
)

print("Response from SarvAM API: \n")
print(response)

# TODO: appify using streamlit or gradio or huggingface spaces

```