# Basics of AI

- [Material](https://github.com/neelsoumya/outreach_ppi)

- [Basics of a biological neural network works](https://ncase.me/neurons/)

> This is actually an interactive animation that students can play around. Like what happens if they click on this neuron? This neuron will send out an impulse that triggers other neurons. And then over time, these, as I start clicking on these connections will get sort of reinforced or not, and these connections will get sort of amplified over time. So this is how biological neural networks learn.

> So if somebody has been bitten by a dog and this is done in therapy, you're sort of really afraid of dogs. You can't, you want to avoid them. But that's not the way to sort of get over the fear of these, of dogs. You repeatedly expose yourself to dogs and say, well, they're not so bad.

> As time goes on, I can repeatedly give signals to these neurons and they are sending signals to each other and these connections get reinforced over time. And this is what's called Hebbian learning.

- The idea behind artificial neural networks is to really encapsulate these, but within computers and we can do lots of interesting stuff with it

- [Practical use of AI to visualize big data](https://projector.tensorflow.org/)

>  In today's day and time we hear about big data. That is, for example, in this particular case, each of these dots may be a single cell. Each cell has thousands of genes within them. There is no way we can visualize this huge amount of data. But using the magic of a machine learning algorithm, say a neural network or something called `PCA`, I can _squish_ this data down into this three dimensional plot and I can play around with this data. 

> So for example, this particular cell maybe is associated with a disorder. How far apart you are from each other tells you what different diseases each of these cells have.

- _Concept_ 🧩 🚀 So machine learning/AI is an intelligent way to really do interesting things with data and give you certain insights


- [Activity to teach AI for facial detection](https://teachablemachine.withgoogle.com/)

- 💡 🛠️Activity on bias detection

-  🧩 🚀 Even though these machine learning algorithms appear fancy, they can make stupid mistakes. It is incumbent upon us to curate the data that is going into this: `garbage in, garbage out`. That is a big concept.

- CCTV cameras are getting used for say, racial discrimination and racial profiling. 

- 💡 Thornier issues that are coming up in machine learning. Not everything in AI is about terminators and them taking over the world. 

- There are multiple immediate risks that AI poses to us. Bias in AI is one of them and _we_ can fix it.

## Understanding how neural networks work

- [Animation](https://teaching-neural-network-animation.streamlit.app/)

## Activity using Google `QuickDraw`

Google [**Quick, Draw!**](https://quickdraw.withgoogle.com/) is a fantastic tool for introducing artificial intelligence to children because it turns complex concepts like machine learning and neural networks into a game.


---

### Activity 1: The Human vs. AI Challenge

**Objective:** Understand that AI doesn't "see" like we do; it recognizes patterns in data.

* **The Setup:** Divide the class into pairs. One student is the "Drawer" and the other is the "Guesser."
* **The Game:** Give the Drawer a word (e.g., "Owl"). They have 20 seconds to draw it while the Guesser tries to identify it.
* **The Comparison:** Now, have the Drawer play *Quick, Draw!* using the same word.
* **Discussion Points:**
* Who guessed faster? The human or the AI?
* The AI often guesses correctly before the drawing is finished. Why?
* **The Concept:** Explain that the AI isn't looking at the final "art." It is tracking the *sequence* of your strokes and comparing them to millions of other drawings of owls it has already "seen."



---

### Activity 2: Exploring the "Brain" (Neural Networks)

**Objective:** Learn how a computer connects visual patterns to labels.

* **The Activity:** After students play a round, click on one of their drawings to see the "Neural Network's" perspective. Scroll down to see what other objects the AI thought the drawing looked like (e.g., "I thought it was a circle, or a wheel...").
* **The Lesson:** Explain that AI uses a "Neural Network," which works like a series of filters. Each layer looks for something specific: lines, then curves, then shapes, and finally, a "Cat."

---

### Activity 3: The "World Museum" & Data Bias

**Objective:** Understand that an AI is only as "smart" as the data it is fed.

* **The Activity:** Visit the [Quick, Draw! Dataset](https://quickdraw.withgoogle.com/data). Search for a common object like "Bread."
* **The Discovery:** Show the students how people from different countries draw "Bread." In some countries, it might be a loaf; in others, a baguette or a flatbread.
* **The Challenge:** If we only showed the AI drawings of baguettes, would it recognize a piece of toast?
* **The Concept:** This teaches **Data Bias**. If the data used to train the AI is limited, the AI will be limited (and potentially unfair) in its results.

---

### How it Works: Behind the Scenes

To help the students visualize how the "guessing" actually happens, you can use this interactive simulation to show how a simple network processes information.

### Teacher Tips for Implementation

1. **Iterative Learning:** Encourage students to try drawing the same object three times. Ask them: "Did you change your drawing style to help the AI understand better?" This introduces the idea of **Prompt Engineering**.
2. **The "Failure" Discussion:** When the AI fails, ask why. Is the drawing too messy, or has the AI just not seen enough examples of that specific style?
3. **No Tech Version:** If computers are limited, have one student "train" another by showing them 10 very specific ways to draw a "Dog" (e.g., only drawing the ears). Then, see if a third student can guess the "Dog" based only on the ears.


## Activity on what is PCA doing

- [Activity](https://cambiotraining.github.io/ml-unsupervised/materials/walkthrough.html#projection-of-3d-data)

