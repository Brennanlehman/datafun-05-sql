## datafun-05-sql
## Project 5 repository

## Start a new project repository in GitHub and then clone down to local machine. I leveraged VS Code clone functionality

## Create Virtual Environment

```shell

py -m venv .venv
.venv\Scripts\Activate


```

## Add requirements folder

```shell

ni requirements.txt

py -m pip install -r requirements.txt
```

## Add gitignore

```shell

ni gitignore
```
## Add script

```shell
brennan_sql.py
```

## How to Install and Run the Project
## Add dependencies

```shell

py -m pip install jupyterlab
py -m pip install numpy
py -m pip install pandas
py -m pip install matplotlib 
py -m pip install seaborn
py -m pip install scipy
```

## Freeze dependencies

```shell

py -m pip freeze > requirements.txt
```

## Git add and commit 

```shell
git add .
git commit -m "add .gitignore, cmds to readme"
git push origin main
```