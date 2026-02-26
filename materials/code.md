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
