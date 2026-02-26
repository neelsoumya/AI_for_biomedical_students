# Introduction to code in Python

Let's build a **"Smart Syllabus Assistant"** that calculates grades and visualizes class performance.

---

## 🕒 The "Hour of Code" Agenda

| Segment | Topic | Faculty Outcome |
| --- | --- | --- |
| **0-10m** | **The Sandbox** | Learning how to "Play" a cell in Colab. |
| **10-25m** | **Digital Folders** | Using variables to store student names and scores. |
| **25-45m** | **The Grade Cruncher** | Using Python to calculate averages and curves. |
| **45-60m** | **Visualizing Success** | Turning a list of numbers into a professional chart. |

---

## 📓 Step 1: The Sandbox (Introduction)

**Instructions for Faculty:** "Think of Google Colab as a digital notebook where you can write text and run code in the same place. No installation required."

1. Open [Google Colab](https://colab.research.google.com/).
2. Click **"New Notebook."**
3. Type the following into the first box (cell) and hit the **Play** button:

```python
# This is a comment. The computer ignores it.
print("Coding is just a very literal assistant.")

```

---

## 📁 Step 2: Digital Folders (Variables)

**The Concept:** In programming, we store information in "variables." Think of them as labeled folders on your desk.

**Exercise:**
Create a new code cell and define a student's data:

```python
student_name = "Professor Smith"
midterm_score = 85
final_exam_score = 92

# Let's calculate the total
total_score = midterm_score + final_exam_score
print(f"{student_name} earned a total of {total_score} points.")

```

---

## 🧮 Step 3: The Grade Cruncher (Lists & Math)

**The Concept:** Faculty rarely deal with one student. They deal with a class. We use **Lists** (square brackets `[]`) to hold multiple values.

**Exercise:**

```python
# A list of student scores
class_scores = [78, 92, 85, 64, 95, 88, 72]

# Python has built-in 'powers' (functions) to help us
number_of_students = len(class_scores)
highest_grade = max(class_scores)
average_grade = sum(class_scores) / number_of_students

print(f"Class Size: {number_of_students}")
print(f"Highest Grade: {highest_grade}")
print(f"Class Average: {round(average_grade, 2)}")

```

---

## 📊 Step 4: Visualizing Success (Data Viz)

**The Concept:** This is the "Magic Moment." We will use a library called `matplotlib` to turn those boring numbers into a visual report.

**Exercise:**
Copy and paste this into a final cell to see the power of Python:

```python
import matplotlib.pyplot as plt

# Data
students = ["A", "B", "C", "D", "E", "F", "G"]
scores = [78, 92, 85, 64, 95, 88, 72]

# Creating the chart
plt.bar(students, scores, color='skyblue')
plt.axhline(y=75, color='red', linestyle='--', label='Passing Grade') # A 'passing' line

# Adding labels
plt.title("Section 101: Midterm Results")
plt.xlabel("Student ID")
plt.ylabel("Score")
plt.legend()

# Show the plot
plt.show()

```

---

## 🎓 The "Take-Home" Message

Wrap up by explaining that they just performed **Data Science**. They took raw data, processed it with logic, and generated a visualization—all in under an hour.

### Pro-Tips for the Facilitator:

* **Embrace the Error:** When a faculty member gets a "SyntaxError," celebrate it! Show them that the computer is just saying, "I don't understand that specific typo," not "You aren't a programmer."
* **The "Play" Button:** Remind them constantly that nothing they type can "break" their computer. It's a safe sandbox.



---

## 🐍 Python for Faculty: The 60-Minute Cheat Sheet

This "Cheat Sheet" is designed to be a single-page reference that faculty can keep open in a tab or printed on their desk. It focuses on the "grammar" of Python without the jargon.


### 1. The Google Colab Environment

* **Code Cell:** A box where you type instructions.
* **The Play Button:** Click the "Play" icon (or press `Shift + Enter`) to run the code in that cell.
* **Comments (`#`):** Anything after a `#` is a note for you. The computer ignores it.
* *Example:* `# This is a note to remind me what this does.`



---

### 2. Storing Information (Variables)

Think of a variable as a **labeled drawer** where you store a piece of data for later.

| Type | Example | Use Case |
| --- | --- | --- |
| **String** | `name = "Dr. Smith"` | Text (always use "quotes"). |
| **Integer** | `points = 100` | Whole numbers for grades/counts. |
| **Float** | `average = 85.5` | Numbers with decimals. |

---

### 3. Working with Groups (Lists)

When you have a whole class, you use a **List**. Lists always live inside **square brackets `[]**`.

* `class_grades = [88, 92, 75, 100]`
* **To get the first item:** `class_grades[0]` (Computers start counting at zero!)

---

### 4. Built-in "Powers" (Functions)

Functions are pre-written shortcuts that do work for you. They always end in **parentheses `()**`.

* `print()` — Shows the result on your screen.
* `len()` — Tells you the **len**gth (how many items are in a list).
* `sum()` — Adds all the numbers in a list together.
* `round(x, 2)` — Rounds a number to 2 decimal places.

---

### 5. The Golden Rule: Indentation

In Python, **space matters**. If you are writing a "loop" or a "condition," the code underneath must be indented (usually by hitting the `Tab` key). This tells Python, "This code belongs to the block above it."

---

### 6. Troubleshooting (Don't Panic!)

If your code turns **Red**, it just means the computer is confused.

* **SyntaxError:** You likely missed a quote `"`, a bracket `]`, or a parenthesis `)`.
* **NameError:** You tried to use a variable name you haven't "saved" yet (did you forget to press Play on the cell where you defined it?).

> **Pro-Tip:** Coding is 10% writing logic and 90% figuring out where you forgot to close a parenthesis. You’re doing great!

---