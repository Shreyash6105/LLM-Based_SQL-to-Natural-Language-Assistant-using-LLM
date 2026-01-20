# Text-to-SQL Assistant using LLM (LangChain + MySQL)

This project converts **natural language questions into SQL queries** and then returns the answer in **plain English**.  
The goal was to understand how Large Language Models (LLMs) can interact with real databases using LangChain, without using any web UI.

---

## What This Project Does
1. Takes a question from the user in simple English  
2. Converts it into a **valid MySQL SELECT query**  
3. Executes the query on a MySQL database  
4. Converts the SQL result into a **clear natural language answer**

---

## Tools & Technologies Used
- Python
- LangChain
- Ollama (LLaMA 3 model)
- MySQL

---

## Project Structure
Text-to-SQL-Assistant/

##### code_final.py # Main application code
##### README.md
##### requirements.txt
##### Data_CSV

---

## Steps Followed to Build This Project

### First of all Create a DataBase in SQL Workbench or any other SQL tool, and add all tables from Data_CSV

---

### 1. Database Connection
- Connected Python to a MySQL database using LangChain’s `SQLDatabase`
- Used a real database schema instead of dummy data
- Verified tables and columns were loaded correctly

---

### 2. SQL Query Generation (LLM – First Step)
- Created a prompt that:
  - Forces correct table and column names
  - Handles column names with spaces
  - Prevents hallucinated queries
- Used LLaMA 3 via Ollama to generate **read-only SQL queries**

---

### 3. SQL Execution
- Automatically executed the generated SQL query on MySQL
- Extracted the required value safely from the result

---

### 4. Natural Language Answer Generation (LLM – Second Step)
- Passed the SQL result back to the LLM
- Generated a clean, short, human-readable answer
- Ensured the final answer does **not mention SQL or databases**

---

### 5. Interactive Command Line Interface
- User can continuously ask questions
- Displays:
  - Generated SQL query
  - Raw database result
  - Final natural language answer
- Type `exit` to stop the program

---

## Example Flow
**User Question:**  
“What is the total sales for Geiss Company?”

**Output:**
- SQL query is generated automatically
- Query runs on MySQL
- Final answer is returned in plain English

---

## Key Learnings
- How LLMs can be grounded using database schemas
- Prompt engineering for strict SQL generation
- Chaining multiple LLM calls for better results
- Practical use of LangChain in real applications

---

## Author
**Shreyash More**  
