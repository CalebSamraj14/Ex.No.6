# Ex.No.6 – Development of Python Code Compatible with Multiple AI Tools

---

### DATE: 27-09-2025
### REGISTER NUMBER: 212222060030

---

## Aim
To **write and implement Python code** that integrates with multiple AI tools, enabling automated interactions with APIs, comparing outputs, and generating actionable insights.  

The focus is on **persona-based prompt patterns** for coding tasks in a specific application domain.

---

## AI Tools Required
- **OpenAI GPT API (ChatGPT / GPT-4)**  
- **Claude AI API** (Anthropic)  
- **Bard API** (Google) – optional, if accessible  
- **Python 3.10+** environment  
- **Requests / HTTP libraries** for API calls  

---

## Introduction
In modern AI development, leveraging multiple AI tools in **parallel** allows developers to:

- Compare outputs for **accuracy and relevance**  
- Identify **best-performing models** for a task  
- Automate tasks like **code generation, debugging, and summarization**  

In this experiment, we implement a **Python script** that interacts with multiple AI tools to generate code for a **specific task**, compare outputs, and summarize actionable insights.

---

## Persona Pattern Used
**Persona:** Programmer / Code Generator AI  
- Task: Generate Python code for **data analysis of CSV files**  
- Instructions included in prompt:  
  - Read CSV file  
  - Calculate summary statistics  
  - Visualize data using Matplotlib  

---

## Procedure

### Step 1: Define Task & Prompt
**Task:** Read a CSV of student scores and generate a **summary report** with:  

- Mean, median, standard deviation per column  
- Histogram for score distribution  

**Prompt Example:**  


---

### Step 2: Python Code to Interact with Multiple AI Tools
~~~
python


import openai
import requests
import json

# OpenAI API Configuration
openai.api_key = "YOUR_OPENAI_API_KEY"

def get_openai_response(prompt):
    response = openai.ChatCompletion.create(
        model="gpt-4",
        messages=[{"role":"user","content":prompt}],
        temperature=0.2
    )
    return response.choices[0].message.content
~~~

# Claude AI API Example (Pseudo-code)
~~~
def get_claude_response(prompt):
    url = "https://api.anthropic.com/v1/complete"
    headers = {
        "Authorization": "Bearer YOUR_CLAUDE_API_KEY",
        "Content-Type": "application/json"
    }
    data = {
        "model": "claude-v1",
        "prompt": prompt,
        "max_tokens": 500
    }
    response = requests.post(url, headers=headers, json=data)
    return response.json()["completion"]
~~~
# Task Prompt

prompt = """
You are a Python programmer. Generate code to read a CSV file "student_scores.csv"
and compute mean, median, and standard deviation for each numeric column. 
Also generate a histogram for each numeric column using matplotlib.
"""

# Generate code using OpenAI
openai_code = get_openai_response(prompt)

# Generate code using Claude
claude_code = get_claude_response(prompt)

# Print outputs for comparison
print("OpenAI GPT Output:\n", openai_code)
print("\nClaude AI Output:\n", claude_code)


Step 3: Execute and Compare Outputs



## Compare the following:

Aspect	OpenAI GPT Output	Claude AI Output	Notes
Code structure	Clear, modular	Clear, slightly verbose	Both readable, GPT slightly concise
Accuracy	Correct libraries, computations	Correct, minor differences	Both correct, GPT output ready to run
Visualization	Matplotlib histograms	Matplotlib histograms	Both generate plots
Comments / Readability	Well-commented	Less commented	GPT better for documentation


## flowchart TD
    A[Define Task & Persona] --> B[Design Prompt]
    B --> C[Send Prompt to OpenAI API]
    B --> D[Send Prompt to Claude API]
    C --> E[Receive Code from OpenAI]
    D --> F[Receive Code from Claude]
    E --> G[Compare Outputs & Evaluate]
    F --> G
    G --> H[Generate Insights & Recommendations]

## Step 5: Analysis

Both AI tools produced functional Python code for reading CSV and visualizing data.

OpenAI GPT output had better readability and comments.

Claude AI output was accurate but slightly more verbose.

Using multiple AI tools helps cross-validate code correctness.

Persona-based prompts help focus AI output for a specific role (programmer) resulting in task-specific solutions.




## Step 6: Example Generated Code Snippet (OpenAI GPT)


import pandas as pd
import matplotlib.pyplot as plt

# Read CSV file
data = pd.read_csv("student_scores.csv")

# Compute statistics
stats = data.describe()
print(stats)

# Generate histograms for numeric columns
~~~
for column in data.select_dtypes(include='number'):
    plt.figure()
    data[column].hist()
    plt.title(f'Histogram of {column}')
    plt.xlabel(column)
    plt.ylabel('Frequency')
    plt.show()


 ~~~
   
## Observations

Using persona pattern improves AI relevance for coding tasks

Multiple AI tools provide comparative insights

Refined prompts reduce ambiguity, increase code quality

AI-generated code may require manual review for optimization or edge cases

## Conclusion

The experiment demonstrates successful integration of Python with multiple AI tools.

The persona pattern enabled AI to act as a programmer, generating task-specific code

Cross-tool comparison helps identify best outputs and improve reliability

The workflow can be extended to any coding or API automation task

## Result

The prompt for the Python code generation task was executed successfully, and outputs from multiple AI tools were compared, analyzed, and actionable insights were generated.



