# Virtual Environment Workflow for Machine Learning Projects

This guide outlines the recommended workflow for using a virtual environment in your project.

---

## 🔁 Typical Workflow with `ml-env` Virtual Environment

### ✅ Step 1: Open Terminal or Command Prompt

### ✅ Step 2: Navigate to Your Main Project Folder
```bash
cd path/to/Machine-Learning-AI-Complete-01
```

### ✅ Step 3: Activate Your Virtual Environment

**Windows:**
```bash
ml-env\Scripts\activate
```

**macOS/Linux:**
```bash
source ml-env/bin/activate
```

### ✅ Step 4: Install Required Packages Inside the Activated Environment
```bash
pip install package-name
```

### ✅ Step 5: Work on Your Project

You can run scripts or notebooks from any subfolder (like `section 1_2 introduction ml 101/`) while the environment is activated.

### ✅ Step 6: Deactivate the Virtual Environment When Done
```bash
deactivate
```

---

## 🔎 Notes

- You don’t have to deactivate immediately after installing packages if you plan to continue working.
- Deactivation is useful when you're done or want to switch environments.
- While activated, **all `python` and `pip` commands** refer to your virtual environment, no matter where in the project you are working.

---

> 🔁 Always activate your virtual environment before starting work to ensure package consistency.

# For Python 3.11
   py -3.11 -m venv venv   | python3.11 -m venv venv
   venv\Scripts\activate
   
# For Python 3.13
   py -3.13 -m venv venv   | python3.13 -m venv venv
   venv\Scripts\activate

# for checking installed python version
C:\Users\heman>where python <br>
C:\Users\heman\AppData\Local\Programs\Python\Python311\python.exe <br>
C:\Users\heman\AppData\Local\Programs\Python\Python313\python.exe <br>
C:\Users\heman\AppData\Local\Microsoft\WindowsApps\python.exe

C:\Users\heman>py -0 <br>
 -V:3.13 *        Python 3.13 (64-bit) <br>
 -V:3.11          Python 3.11 (64-bit)