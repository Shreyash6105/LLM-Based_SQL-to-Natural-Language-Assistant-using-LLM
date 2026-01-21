# Text-to-SQL-to-Natural-Language Assistant using LLM (LangChain + MySQL)

This project converts **natural language questions into SQL queries** and returns the results as **clear, plain English answers**.  
The main goal of this project is to understand how **Large Language Models (LLMs) can interact with real databases** using LangChain, without relying on any web interface.

---

## What This Project Does

1. Accepts a user question written in natural language  
2. Converts the question into a **valid MySQL SELECT query**  
3. Executes the query on a real MySQL database  
4. Converts the SQL output into a **human-readable answer**

---

## Tools and Technologies Used

- Python  
- LangChain  
- Ollama (LLaMA 3 model)  
- MySQL  

---

## Project Structure
##### code_final.py # Main application code
##### README.md
##### requirements.txt
##### Data_CSV

---

## Setup Requirement

Before running the project:
- Create a database using **MySQL Workbench** or any SQL client
- Create tables using the CSV files present in the `Data_CSV/` folder
- Ensure the database credentials are correctly configured in the code

---

## Steps Followed to Build This Project

### 1. Database Connection
- Connected Python to a MySQL database using LangChain’s `SQLDatabase`
- Used a real database schema instead of mock or hardcoded data
- Verified that tables and columns were correctly loaded

---

### 2. SQL Query Generation (LLM – First Step)
- Designed prompts that:
  - Enforce correct table and column names
  - Handle column names containing spaces
  - Reduce the chances of hallucinated queries
- Used LLaMA 3 via Ollama to generate **read-only SQL queries**

---

### 3. SQL Execution
- Executed the generated SQL query directly on the MySQL database
- Retrieved query results in a safe and controlled manner

---

### 4. Natural Language Answer Generation (LLM – Second Step)
- Passed the SQL result back to the LLM
- Generated a short, clear, and user-friendly response
- Ensured the final answer does **not expose SQL syntax or database details**

---

### 5. Interactive Command-Line Interface
- Allows users to ask questions continuously
- Displays:
  - Generated SQL query
  - Raw database output
  - Final natural language response
- Typing `exit` stops the program

---

## Example Flow

**User Question:**  
“What is the total sales for Geiss Company?”

**System Behavior:**
- SQL query is generated automatically
- Query is executed on MySQL
- Final answer is returned in plain English

---

## Key Learnings

- Grounding LLMs using real database schemas
- Prompt engineering for controlled SQL generation
- Chaining multiple LLM calls for better accuracy
- Practical use of LangChain in database-driven applications

---

## Author

**Shreyash More**
