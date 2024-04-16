# A Tempalte to Create a Research Project Repo

### How to use it (a dirty way)
A linux-based example. Adjust it accordingly for windows.
```
# gie clone it
git clone https://github.com/stormliucong/my-research-project-template.git
# enter it
cd my-research-project-template
# delete git
rm -rf .git
# change name
cd ../
mv my-research-project-template [your-research-project]
# re init
cd your-research-project
git init
```

### House Keeping Items
#### Set up environment (Linux example)
```python
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```
#### Update requirements.txt
```python
pip freeze > requirements.txt
# or only packages beening used.
pip install pipreqs
pipreqs ./
```
#### Secrets and configuration
Create a `secrete.ini` file in the project root folder and make sure it is added to the `.gitignore`. 
```env
[database]
host = localhost
port = 5432
database = mydatabase
user = myuser
password = mypassword

[app]
debug = True
```
To read an .ini file in Python, you can use the built-in configparser module. Here's how you can do it:
```python
import configparser
# Create a ConfigParser object
config = configparser.ConfigParser()
# Read the configuration file
config.read('config.ini')
# Access values from the configuration and convert them to uppercase use a convention for ENV.
DATABASE_HOST = config['database']['host'].upper()
DATABASE_PORT = config['database']['port'].upper()
DATABASE_NAME = config['database']['database'].upper()
DATABASE_USER = config['database']['user'].upper()
DATABASE_PASSWORD = config['database']['password'].upper()
APP_DEBUG = config['app'].getboolean('debug')
```

#### Commit and commit msg
- The principle is to maximize reproducibility and minimize redundant work. To achieve this, adhere to three key principles:
    1. Before committing any changes, ensure that the documentation and code reflect the same procedure. If they do not, update the documentation first, then commit with the message *'MAJOR description.'* 
        - **This type of commit should typically align with the transition to the next stages of manuscript development.**. See [Manuscript develop cycle](./docs/README.md) for details.
    2. For minor corrections related to bug fixes or grammar in the documentation, (if you want to commit), commit with the message *'MINOR description.'*
    3. For updates to the data, always commit with a message like *'DATA raw/v1 description.'* 

