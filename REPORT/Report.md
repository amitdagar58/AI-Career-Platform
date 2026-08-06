# This is the first real development setup for your AI Carrer Platform.

---
# 1. We install Python, Create Virtual Environment, We activated virtual Environment and inside virtual environment ((.venv) appears in the terminal)

✅ Create Virtual Environment
        ↓
➡ Install Required Packages
        ↓
Create requirements.txt
        ↓
Create FastAPI Project
        ↓
Run First FastAPI Server

---
# 2. Install Required Packages
# What are Packages?

Packages are pre-written libraries created by other developers that save us from writing everything from scratch.

# Why do we install them inside .venv?

Because we want these packages to belong only to this project.

# Packages we'll install

For now, we need only the essential packages.

Run this command:
pip install fastapi uvicorn sqlalchemy pymysql python-dotenv pydantic

# What does each package do?
| Package           | Purpose                                |
| ----------------- | -------------------------------------- |
| **fastapi**       | Build REST APIs                        |
| **uvicorn**       | Run the FastAPI server                 |
| **sqlalchemy**    | Connect Python with MySQL (ORM)        |
| **pymysql**       | MySQL database driver                  |
| **python-dotenv** | Read values from the `.env` file       |
| **pydantic**      | Validate API request and response data |

---
# 3. Verify Installation
After installation, run:
pip list

- We should see packages like:
fastapi
uvicorn
sqlalchemy
pydantic
pymysql
python-dotenv

---
# Now, we ready to write our first backend code.

# Step.1: Create requirenments.txt
# What is requirements.txt?

It is a file that stores all the Python packages required for the project.

pip install -r requirements.txt
pip freeze > requirements.txt   #(Run this command for create automatically.)

# Step 2: Our First FastAPI Application
Before writing code, a quick explanation.

# What is FastAPI?

FastAPI is a Python framework used to build REST APIs.

Think of it this way:
Browser
     │
     ▼
FastAPI
     │
     ▼
Database

# Our First Goal
In this, We just want to check that our backend works.
If we can open a webpage saying:
- Welcome to AI Career Platform API

then our backend setup is successful.

# Step 3: Create main.py
Create this file:
backend/
│
└── app/
      └── main.py

- Code:
from fastapi import FastAPI

app = FastAPI(
    title="AI Career Platform API",
    version="1.0.0"
)


@app.get("/")
def home():
    return {
        "message": "Welcome to AI Career Platform API"
    }

# Line 1: from fastapi import FastAPI

# Step 4: Run the Server
Open the terminal.
Go inside the backend folder.
- cd backend

Now run:
- uvicorn app.main:app --reload

# Step 5: Open the Browser
visit:
http://127.0.0.1:8000

We should see:
{
  "message": "Welcome to AI Career Platform API"
}

---
# From now, A small improvement to our workflow
From now on, after every coding session, we'll follow this cycle:
Learn the concept
        ↓
Write the code
        ↓
Run the code
        ↓
Test the feature
        ↓
Understand the output
        ↓
Git Commit
        ↓
Push to GitHub

---
# Before we write more code
- What Happened?
When we run:
uvicorn app.main:app --reload

this is what happened internally:
Browser
      │
      ▼
http://127.0.0.1:8000
      │
      ▼
Uvicorn Server
      │
      ▼
FastAPI Application
      │
      ▼
@app.get("/")
      │
      ▼
Returns JSON Response

---
Our next milestone is:
# Backend Foundation

# Step 1: Create these files:
inside backend/app, create the following:
app/
│
├── api/
│   └── __init__.py
│
├── core/
│   ├── __init__.py
│   └── config.py
│
├── database/
│   ├── __init__.py
│   └── database.py
│
├── models/
│   └── __init__.py
│
├── schemas/
│   └── __init__.py
│
├── services/
│   └── __init__.py
│
├── utils/
│   └── __init__.py
│
└── main.py

### Why are we creating __init__.py ?
A short explanation:

If a folder contains a file named __init__.py, Python understands that this folder is a Python package.

Because it is a package, Python allows you to easily import files, classes, and functions from that folder.

For now, each __init__.py file can be empty.

### Why Do We Use __init__.py?
The Main purpose is to tell Python:
- "This Folder contains Python code that can be imported."

Think of it like an identity card for the folder.

Without it, the folder is just a folder.
With it, the folder becomes a python package.

---
### There is a question in Front of us.
- **Why do we update** requirements.txt?

Ques: What is **requirements.txt**?
**requirements.txt** is a file that contains a list of all the Python packages your project needs.

Examples:
fastapi==0.116.1
uvicorn==0.35.0
sqlalchemy==2.0.43
pymysql==1.1.2
python-dotenv==1.1.1
pydantic==2.11.7

Each line contains:
- Package name
- Exact version

### Why do we create it?
Imagine we finish this project and upload it to github.

Now a recruiter or our friend downloads our project.

Without **requirements.txt**, they don't know:
- Which packages are required.
- Which versions you used.
They would have to install everything manually.

With requirements.txt, they only run:
- pip install -r requirements.txt
and Python installs **everything automatically**.

---
# Our Next goal