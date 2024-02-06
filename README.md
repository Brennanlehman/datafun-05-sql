# datafun-05-sql
# Project 5 repository
## Objective: Create a Python script that demonstrates the ability to interact with a SQL database, including creating a database, defining a schema, and executing various SQL commands. Incorporate logging to document the process and provide user feedback.

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
### How to Install and Run the Project

### Step 7. Add script

```shell
ni book_authors_sql.py
```

### Step 7.1 Added second python program to run sql scripts from
```shell
ni book_author_sql_execute.py
```

### Step 8. Add dependencies

```shell

py -m pip install pandas
py -m pip install pyarrow
python.exe -m pip install --upgrade pip

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
# Project components

### Step 1. Create python script 
```shell
ni books_authors_sql.py
ni author_sql_execute.py
```
### Step 2. Create database using the python file
```shell
db_file = pathlib.Path("project.db")

def create_database():
    """Function to create a database. Connecting for the first time
    will create a new database file if it doesn't exist yet.
    Close the connection after creating the database
    to avoid locking the file."""
    try:
        conn = sqlite3.connect(db_file)
        conn.close()
        print("Database created successfully.")
    except sqlite3.Error as e:
        print("Error creating the database:", e)
```

### Step 3. Create sql scripts in sql_file folder, individual queries contained in each file

```shell
ni create_tables.sql
ni delete_tables.sql
ni insert_records.sql
ni query_aggreation.sql
ni query_filter.sql
ni query_sorting.sql
ni query_group_by.sql
ni query_join.sql
```

### Step 4. Python and SQL Integration
```shell
import sqlite3

def execute_sql_from_file(db_filepath, sql_file):
    with sqlite3.connect(db_filepath) as conn:
        with open(sql_file, 'r') as file:
            sql_script = file.read()
        conn.executescript(sql_script)
        print(f"Executed SQL from {sql_file}")
```

### 5. Define Main Function
```shell
def main():
    db_filepath = pathlib.Path("C:\\Users\\blehman\\Projects\\datafun-05-sql\\project.db")

    # Create database schema and populate with data
    execute_sql_from_file(db_filepath, 'sql_file/create_tables.sql')
    execute_sql_from_file(db_filepath, 'sql_file/insert_records.sql')
    execute_sql_from_file(db_filepath, 'sql_file/update_records.sql')
    execute_sql_from_file(db_filepath, 'sql_file/delete_records.sql')
    execute_sql_from_file(db_filepath, 'sql_file/query_aggregation.sql')
    execute_sql_from_file(db_filepath, 'sql_file/query_filter.sql')
    execute_sql_from_file(db_filepath, 'sql_file/query_sorting.sql')
    execute_sql_from_file(db_filepath, 'sql_file/query_group_by.sql')
    execute_sql_from_file(db_filepath, 'sql_file/query_join.sql')

    logging.info("All SQL operations completed successfully")
```
### 6. Logging
```shell
# Configure logging to write to a file, appending new logs to the existing file
logging.basicConfig(filename='log.txt', level=logging.DEBUG, filemode='a', format='%(asctime)s - %(levelname)s - %(message)s')

logging.info("Program started")
logging.info("Program ended")
```
