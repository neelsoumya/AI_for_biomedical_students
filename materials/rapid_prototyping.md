# Rapid prototyping using `streamlit` and `gradio`

- [🎥 Lecture on deeplearning.ai](https://learn.deeplearning.ai/courses/fast-prototyping-of-genai-apps-with-streamlit/lesson/egrcal/scoping-an-mvp)

- ⬆️📎 [Code github](https://github.com/https-deeplearning-ai/fast-prototyping-of-genai-apps-with-streamlit)

## Co-creating an MVP with GenAI

- [🎥 Lecture](https://learn.deeplearning.ai/courses/fast-prototyping-of-genai-apps-with-streamlit/lesson/i1aro4/lab-1%3A-co-creating-an-mvp-plan-with-genai)

- Use a GenAI app to prototype (turn PDF notes into clinical insight)

- Brainstorm end goal

- Who is audience? (non-technical people)

- What does the app look like?

- Features (drag and drop, export to csv, etc.)

- be specific (do not give open ended tasks to GenAI apps)

⚠️ _NOTE_

> Give the AI a role _act as a product manager_


## ⬆️📎 Tools

[🎥 Lecture](https://learn.deeplearning.ai/courses/fast-prototyping-of-genai-apps-with-streamlit/lesson/hl2zjx/setting-up-your-environment)

- Google Colab

- Streamlit

- ngrok account and auth token

- Sarvam AI API key


Optional


- Python

- Local files


## 🎮 🛠️ Activity using Streamlit

- [streamlit](https://streamlit.io/playground?example=charts)

- [Interactive streamlit GDP dashboard](https://github.com/neelsoumya/gdp-dashboard)

- [Deploy on _streamlit.io_](https://streamlit.io/cloud)

- Click on [_New app_](https://share.streamlit.io/new)

- [Here](https://gdp-dashboard-t19rvs9nq2m.streamlit.app/) is a deployed app

- Push your code to github and deploy

- [Course on deeplearning.ai on streamlit](https://learn.deeplearning.ai/courses/fast-prototyping-of-genai-apps-with-streamlit/lesson/79cfr0/setting-up-your-environment)

- Setup a repository in _github_

- Or run in Google _Colab_

- Run _streamlit_ using

```bash
streamlit run script.py
```

- Here is an example script

```python
import streamlit as st
import pandas as pd
import numpy as np

st.write("Streamlit supports a wide range of data visualizations")

all_users = ["Alice", "Bob", "Charly"]
with st.container(border=True):
    users = st.multiselect("Users", all_users, default=all_users)
    rolling_average = st.toggle("Rolling average")

np.random.seed(19)
data = pd.DataFrame(np.random.randn(20, len(users)), columns=users)

if rolling_average:
    data = data.rolling(7).mean().dropna()

tab1, tab2 = st.tabs(["Chart", "Dataframe"])
tab1.line_chart(data, height=250)
tab2.dataframe(data, height=250, use_container_width=True)

```

- [ngrok signup](https://dashboard.ngrok.com/signup)

- [create an auth token](https://dashboard.ngrok.com/authtokens/new)

- [Google Colab notebook](https://github.com/neelsoumya/visualization_lecture/blob/main/streamlit.ipynb)

- To save your `ngrok` authtoken securely in Google Colab, you should use Colab's **Secrets** feature. This allows you to store sensitive information like API keys or tokens without embedding them directly in your code, which is important for security and when sharing notebooks.

1.  **Open the Secrets Panel:** In the left sidebar of your Colab notebook, click on the **"🔑 Secrets"** icon (it looks like a key).
2.  **Add a new secret:** Click the **"+ Add new secret"** button.
3.  **Name the secret:** For your `ngrok` authtoken, you could name it `YOUR_AUTHTOKEN` (or any other descriptive name you prefer, but remember it for later).
4.  **Enter the secret value:** Paste your `ngrok` authtoken into the "Value" field.
5.  **Save:** Click "Save secret".

Once saved, you can access this secret in your Python code using `from google.colab import userdata` and then `userdata.get('YOUR_AUTHTOKEN')` (replacing `'YOUR_AUTHTOKEN'` with the name you gave your secret).


## Streamlit commands

- [🎥 Lecture](https://learn.deeplearning.ai/courses/fast-prototyping-of-genai-apps-with-streamlit/lesson/154mpf/making-your-first-interactive-streamlit-app)

- `st.slider` `st.button` `st.text_input()` `st.selectbox()` `st.checkbox()` `st.file__uploader()`


## 🎮 💡🛠️Activity: chatbot and streamlit

- [Code to wrap a streamlit UI around chatbot](https://github.com/https-deeplearning-ai/fast-prototyping-of-genai-apps-with-streamlit/blob/main/M1/Lesson_02/M1L2V3.py)


- Code from deeplearning.ai

```python
# import packages
from dotenv import load_dotenv
import openai
import streamlit as st


# load environment variables from .env file
load_dotenv()

# Initialize OpenAI client
client = openai.OpenAI()

st.title("Hello, GenAI!")
st.write("This is your first Streamlit app.")

response = client.responses.create(
    model="gpt-4o",
    input=[
        {"role": "user", "content": "Explain generative AI in one sentence."}  # Prompt
    ],
    temperature=0.7,  # A bit of creativity
    max_output_tokens=100  # Limit response length
)

# print the response from OpenAI
st.write(response.output[0].content[0].text)

```


## Visualization

- [🎥 Lecture video](https://learn.deeplearning.ai/courses/fast-prototyping-of-genai-apps-with-streamlit/lesson/op1g8l/data-visualization)

- `st.bar_chart()`

- `st.scatter_chart(df)`, works with _pandas_ dataframe

- use with _matplotlib_ `st.pyplot(fig)`

- use with _plotly_ `st.plotly_chart(fig, use_container_width = True)`

## Deploy app

- [🎥 Lecture video](https://learn.deeplearning.ai/courses/fast-prototyping-of-genai-apps-with-streamlit/lesson/y8oa6j/publish-your-app-online)


### 📚 📝 Deployment for `streamlit`

- [Github](https://github.com/) Create new account on github

- Create new app and connect to [github](https://github.com/)

- Create new repository on github

- Upload your code to github (code below)

```python
import streamlit as st
import pandas as pd
import numpy as np
import folium
from folium.plugins import HeatMap
from streamlit_folium import st_folium

st.title("Outbreak Investigator")
st.write("Adjust the settings in the sidebar, then try to identify the source of the outbreak from the map.")

# --- SIDEBAR CONTROLS ---
st.sidebar.header("Settings")
total_cases = st.sidebar.slider("Total cases", 100, 1000, 500)
cluster_pct = st.sidebar.slider("% of cases near the source", 10, 90, 70)
show_source = st.sidebar.checkbox("Reveal the true source")

# --- GENERATE SYNTHETIC DATA ---
market_lat, market_lon = 30.6195, 114.2577

cluster_count = int(total_cases * cluster_pct / 100)
noise_count = total_cases - cluster_count

np.random.seed(420)
cluster_lats = np.random.normal(market_lat, 0.005, cluster_count)
cluster_lons = np.random.normal(market_lon, 0.005, cluster_count)
noise_lats = np.random.uniform(30.50, 30.70, noise_count)
noise_lons = np.random.uniform(114.20, 114.40, noise_count)

cases = pd.DataFrame({
    'lat': np.concatenate([cluster_lats, noise_lats]),
    'lon': np.concatenate([cluster_lons, noise_lons]),
})

pois = pd.DataFrame({
    'name': ['Wuhan International Plaza', 'Huanan Seafood Market', 'Hankou Railway Station', 'Wuhan CDC'],
    'lat':  [30.584,   30.6195, 30.618, 30.612],
    'lon':  [114.271,  114.2577, 114.250, 114.265],
    'is_source': [False, True, False, False],
})

# --- SHOW STATS ---
st.write(f"**Total cases:** {total_cases} — **Clustered:** {cluster_count} — **Scattered:** {noise_count}")

# --- BUILD MAP ---
m = folium.Map(location=[30.61, 114.28], zoom_start=13, tiles='cartodbpositron')

HeatMap(cases[['lat', 'lon']].values.tolist(), radius=12, blur=15).add_to(m)

for _, poi in pois.iterrows():
    if poi['is_source'] and show_source:
        color = 'red'
        label = f"TRUE SOURCE: {poi['name']}"
    else:
        color = 'black'
        label = poi['name']

    folium.Marker(
        location=[poi['lat'], poi['lon']],
        popup=label,
        tooltip=label,
        icon=folium.Icon(color=color, icon='question-sign'),
    ).add_to(m)

st_folium(m, width=900, height=550)
```

- `requirements.txt` is here

```bash
streamlit>=1.35.0
streamlit-folium>=0.20.0
folium>=0.17.0
pandas>=2.0.0
numpy>=1.26.0
```

- [Connect to code on github](https://github.com/neelsoumya/wuhan_covid_scavenger_hunt_streamlit_teaching)

- Go to [Streamlit](https://share.streamlit.io/new) and connect your github repository


- [Deployed app](https://wuhan-scavenger-hunt-interactive.streamlit.app/)

- can also deploy on [Huggingface spaces](https://huggingface.co/spaces)



## (Optional) Data handling

- [🎥 Lecture video](https://learn.deeplearning.ai/courses/fast-prototyping-of-genai-apps-with-streamlit/lesson/moieyb/integrating-genai-for-data-handling)

- `st.session_state()`



## `Gradio`

- [Gradio](https://www.gradio.app/)

- here is python code using gradio and plotly.express libraries to create an interactive web application that visualizes car-sharing data on a map.

Here is a breakdown of what it does:

* Loads Data: It starts by loading a built-in spatial dataset called carshare from Plotly, which contains information about car availability, centroids (latitude and longitude), and peak hour usage.

* `generate_map` function: This function takes a peak_hour_threshold as input. It filters the carshare data to only include entries where the peak_hour is less than or equal to the provided threshold. Then, it creates a scatter mapbox plot using plotly.express, displaying car availability (car_hours) at different geographical locations (centroid_lat, centroid_lon). The color and size of the points on the map are determined by car_hours, and the map style is set to carto-positron.

* Gradio Interface: It defines a Gradio application using `gr.Blocks`:

It adds a title and a descriptive markdown text.
It includes a `gr.Slider` component, allowing users to select a peak_hour value (from 0 to 23). This slider acts as the input to filter the data.
It defines a `gr.Plot()` component as the output, which will display the Plotly map generated by the generate_map function.

* Interaction Logic: The `hour_slider.change()` method connects the slider's value to the generate_map function. This means that whenever the slider's value changes, the generate_map function is called with the new slider value, and the updated map is displayed in map_output.

* Initial Load: `demo.load()` ensures that the map is generated and displayed with the initial slider value (12) when the application first loads.

* Launch: Finally, `demo.launch()` starts the Gradio web server, making the interactive application accessible.


- Code is here

```python
import gradio as gr
import plotly.express as px

# 1. Load a built-in spatial dataset from Plotly
df = px.data.carshare()

def generate_map(peak_hour_threshold):
    """
    Filters the dataframe based on peak hour and returns a Plotly figure.
    """
    # Filter data based on the user's slider input
    filtered_df = df[df['peak_hour'] <= peak_hour_threshold]
    
    # Create the spatial scatter plot
    fig = px.scatter_mapbox(
        filtered_df, 
        lat="centroid_lat", 
        lon="centroid_lon", 
        color="car_hours", 
        size="car_hours",
        color_continuous_scale=px.colors.sequential.Plasma, 
        size_max=15, 
        zoom=10,
        mapbox_style="carto-positron",
        title=f"Car Availability (Peak Hour ≤ {peak_hour_threshold})"
    )
    
    fig.update_layout(margin={"r":0,"t":40,"l":0,"b":0})
    return fig

# 2. Define the Gradio Interface
with gr.Blocks() as demo:
    gr.Markdown("# 🚗 Montreal Ride-Sharing Explorer")
    gr.Markdown("Adjust the slider to filter car availability by peak hour usage.")
    
    with gr.Row():
        # Input: A slider for filtering
        hour_slider = gr.Slider(
            minimum=0, 
            maximum=23, 
            value=12, 
            step=1, 
            label="Filter by Peak Hour"
        )
    
    # Output: The Plotly Map
    map_output = gr.Plot()

    # Trigger logic: When the slider moves, update the map
    hour_slider.change(fn=generate_map, inputs=hour_slider, outputs=map_output)
    
    # Run the map on load
    demo.load(fn=generate_map, inputs=hour_slider, outputs=map_output)

if __name__ == "__main__":
    demo.launch()
```

## More materials

- [Additional materials](https://neelsoumya.github.io/visualization_lecture/exercises/exercise_week7.html). See _Exercise Week 7_ activities with `streamlit`, `gradio`