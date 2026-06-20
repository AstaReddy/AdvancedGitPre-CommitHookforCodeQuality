# Advanced Git Pre-Commit Hook for Code Quality

## Overview

This project demonstrates a Git pre-commit hook that enforces code quality checks before code is committed.

## Checks Performed

### 1. Code Formatting

Uses Black to verify Python code formatting.

```bash
black --check
```

### 2. Linting

Uses Flake8 to identify code quality issues.

```bash
flake8
```

### 3. Sensitive Information Detection

Blocks commits containing:

- TODO comments
- Hardcoded passwords
- API keys
- Secrets

Example patterns:

```python
password = "12345"
api_key = "abc123"
# TODO fix this
```

## Project Structure

```text
.
├── hooks/
│   └── pre-commit
├── source/
│   ├── badexample.py
│   └── goodexample.py
├── requirements.txt
├── .gitignore
└── README.md
```

## Installation

```bash
pip install black flake8
```

## Usage

Attempting to commit code with formatting issues, TODO comments, or sensitive information will block the commit.

After corrections are made, commits proceed successfully.

## Demonstration

The hook was tested by:

1. Committing unformatted code.
2. Committing code containing TODO comments and passwords.
3. Fixing all issues and committing successfully.
