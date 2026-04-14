GitHub Action Example
This repository demonstrates a simple GitHub Actions workflow for running Python tests automatically on every push.

Workflow
The workflow is defined in first-action.yaml.
It runs on every push to the repository.
It sets up Python (versions 3.8 and 3.9), installs dependencies, and runs tests using pytest.
Project Structure
src/addition.py: Example Python file to be tested.
first-action.yaml: GitHub Actions workflow file.
How to Trigger the Workflow
Make any commit and push to the repository. The workflow will run automatically.

Additional Workflow Example
Run job only if commit message contains 'deploy'
jobs:
  build:
    if: contains(github.event.head_commit.message, 'deploy')
    runs-on: ubuntu-latest
    steps:
      # ...existing steps...

--------
Lint Python code with flake8
jobs:
  lint:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - name: Set up Python
        uses: actions/setup-python@v2
        with:
          python-version: '3.x'
      - name: Install flake8
        run: pip install flake8
      - name: Run flake8
        run: flake8 src/
Manual workflow dispatch
on:
  workflow_dispatch: