# dbt Airbnb Project

A dbt data transformation project for Airbnb analytics using Snowflake as the data warehouse.

## Project Structure

```
dbt-airbnb-final/
├── airbnb/                    # Main dbt project
│   ├── models/               # dbt data transformations
│   │   ├── src/             # Source models (ephemeral)
│   │   ├── dim/             # Dimensional tables
│   │   └── fct/             # Fact tables
│   ├── macros/              # dbt macros and templates
│   ├── seeds/               # Static data files
│   ├── tests/               # dbt tests
│   ├── snapshots/           # Slowly changing dimension snapshots
│   ├── analyses/            # Ad-hoc analysis queries
│   ├── dbt_project.yml      # dbt project configuration
│   ├── profiles.yml         # Snowflake connection config (DON'T COMMIT)
│   └── README.md            # dbt project docs
├── pyproject.toml           # Python project dependencies
├── .venv/                   # Virtual environment (DON'T COMMIT)
└── logs/                    # dbt logs (DON'T COMMIT)
```

## Setup Instructions

### 1. Clone the Repository
```bash
git clone <repository-url>
cd dbt-airbnb-final
```

### 2. Create & Activate Virtual Environment
```bash
# Create virtual environment
python -m venv .venv

# Activate on Windows (PowerShell)
& .\.venv\Scripts\Activate.ps1

# Activate on Windows (Command Prompt)
.venv\Scripts\activate.bat

# Activate on macOS/Linux
source .venv/bin/activate
```

### 3. Install Dependencies
```bash
pip install --upgrade pip
pip install -e .
```

### 4. Configure Snowflake Connection
Create `airbnb/profiles.yml` with your Snowflake credentials:
```yaml
airbnb:
  target: dev
  outputs:
    dev:
      type: snowflake
      account: [your_account_id]
      user: [your_username]
      password: [your_password]
      role: [your_role]
      database: [your_database]
      schema: dev
      threads: 1
      client_session_keep_alive: False
```

### 5. Run dbt
```bash
cd airbnb
dbt run
dbt test
```


## Current Status

✅ Virtual environment configured
✅ dbt 1.11.0 installed
✅ Snowflake adapter installed
✅ Models running successfully

Have fun! :)  
