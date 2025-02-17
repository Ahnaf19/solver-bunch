# solver-bunch: Development Workflow

Please follow this workflow when making code changes to the system.

## Development Workflow

- Pull the latest version of the **"main"** branch

- Create venv

  ```console
  python3.10 -m venv solverB
  source .venv/bin/activate

  # use conda env
  conda create -n "solverB" python=3.10.16
  conda activate solverB
  ```

- Install the development dependencies

  ```console
  pip3 install --upgrade pip
  pip3 install -r requirements-dev.txt
  ```

- Checkout to a new development branch
- Make your code changes
- Add/update unit tests for your changes

- Run unit tests

  ```console
  pytest
  ```

- Start up the solver-bunch service locally (docker)

> [WARNING]
> Dockerfile yet to be added

```console
docker build -t solverB:latest .
```

Then you can start solver-bunch in development mode:

```console
docker run -dp 8000:8000 solverB:latest
```

- Run pre-commit workflow

  ```console
  pre-commit install
  python3 -m pre_commit run --all-files
  ```

- Commit changes to your local branch, ensure commit name is 3-10 words and summarizes the changes
- Create a Pull Request to merge your changes into the **"main"** with the following:
  - Clear and concise description of the changes made
  - Testing procedure - how did you test that your code didn't break anything?
  - Any relevant execution logs or screenshots
- Submit the Pull Request
