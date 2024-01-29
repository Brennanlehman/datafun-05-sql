## datafun-05-sql
## Project 5 repository

### Step 1. Start a new project repository in GitHub with default ReadME

### Step 2.  Clone down to local machine. I leveraged VS Code clone functionality

### Step 3. Open project in VS Code 

### Step 4. Create and activate Virtual Environment

```shell

py -m venv .venv
.venv\Scripts\Activate


```

### Step 5. Add requirements folder

```shell

ni requirements.txt

py -m pip install -r requirements.txt
```

### Step 6. Add gitignore and  with .vscode/ and .venv/ and whatever else doesn't need to go in the repo.

```shell

ni gitignore
```
## How to Install and Run the Project

### Step 7. Add script

```shell
brennan_sql.py
```

### Step 8. Add dependencies

```shell

py -m pip install jupyterlab
py -m pip install numpy
py -m pip install pandas
py -m pip install matplotlib 
py -m pip install seaborn
py -m pip install scipy
```

### Step 9. Freeze dependencies

```shell

py -m pip freeze > requirements.txt
```

### Step 10. Git add and commit 

```shell
git add .
git commit -m "add .gitignore, cmds to readme"
git push origin main
```