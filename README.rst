Cookiecutter Business Intelligence Project with Python
########################################################

This project contains a Cookiecutter template that helps you create new Python
3.10+ package projects by automatically generating most of the boilerplate
content for you.

Cookiecutter is a command-line utility that creates projects from templates.
Cookiecutter lets you easily and quickly bootstrap a new project from a
template which allows you to skip all manual setup and common mistakes when
starting a new project.

Cookiecutter takes a source directory tree and copies it into your new project.
It replaces all the names that it finds surrounded by templating tags `{{`
and `}}` with names that it finds in the file `cookiecutter.json`.

The Python project structure produced by this Cookiecutter template contains
the following items:

- A minimal README.md file.
- A Makefile that automates many common developer tasks.
- A `setup.py` file used to generate project install and releases.
- A `CONTRIBUTING.md` guide.
- An empty `CHANGELOG.md` file.
- A `License` file that defaults to the MIT License.
- An `airflow` directory with DAGs, plugins, and configuration.
- A `bin` directory for executable scripts.
- A `data` directory for raw and cleaned data.
- A `docs` directory for project documentation.
- A `src` directory containing the main project source code, including:
  - An `etl` module for extract, transform, and load operations.
  - A `models` module for machine learning model training, prediction, and evaluation.
  - An `api` module for API code (using FastAPI, Flask, etc.).
- A `tests` directory for test scripts.
- A `notebooks` directory for Jupyter notebooks.
- A `dashboard` directory for dashboard code (using Streamlit or Dash).
- A Dockerfile and docker-compose.yml for containerization.
- Various configuration files (.env, .gitignore, pytest.ini, .flake8).
- A Github Actions workflow configuration.

It is assumed that the new Python package will eventually be:

- hosted on Github (or perhaps GitLab)
- published to PyPI
- deployed using Docker
- use Airflow for workflow management
- include a web API and dashboard

The generated docs have some references and links to those components.

Getting Started
===============

One Time Setup Steps
--------------------

The process for using Cookiecutter to create a new Python package project
starts with installing Cookiecutter. This is best done by creating a new
virtual environment specifically for cookiecutter and then installing
cookiecutter using `pip`. The example below shows how to do this.

```console
$ python -m venv ccvenv --prompt cc
$ source ccvenv/bin/activate
(cc) $ pip install pip -U  # update pip to avoid any warnings
(cc) $ pip install cookiecutter
```

You are now ready to create a new Python project from the Cookiecutter
template provided by this project.

Create a new project
--------------------

To create a new Python package project based on this cookiecutter template,
simply navigate to a directory where you want to create the new project, then
run the `cookiecutter` command with a command line argument referencing this
template.

```console
(cc) $ cookiecutter gh:yourusername/cookiecutter-python-project
```

You will be prompted for user input to configure the project. Prompts are the
keys in 'cookiecutter.json' and default responses are the values.

Once you have generated your new Python package project, you can exit the
cookiecutter virtual environment as it is no longer required.

```console
(cc) $ deactivate
$
```

Manual Modifications
--------------------

Some aspects of generating a project in a generic approach are not practical
to completely automate, so there may be a few steps remaining before you begin
using the new project:

- Update the `airflow.cfg` file with your specific Airflow configurations.
- Modify the Dockerfile and docker-compose.yml as needed for your project.
- Update the Github Actions workflow to fit your CI/CD needs.
- If you're not using certain components (e.g., dashboard or API), you may want to remove those directories.

Example
=======

Below is an example showing how to create a new Python project using
this template. In this scenario, the project is called `data_pipeline`.

After running the cookiecutter command, you might see prompts like this:

```console
(ccenv) $ cookiecutter gh:yourusername/cookiecutter-python-project
project_name [Data Pipeline]: data_pipeline
project_slug [data_pipeline]: 
project_short_description [A data pipeline project]: This is my data pipeline project.
python_version [3.10]: 
use_docker [y]: 
use_airflow [y]: 
use_dashboard [y]: 
Select dashboard_framework:
1 - Streamlit
2 - Dash
Choose from 1, 2 [1]: 1
github_username [YourGithubUsername]: datauser
year [2024]: 
```

The project will be created in the `data_pipeline` directory. You can then navigate to this directory and start customizing your project.

Remember to create a virtual environment, install dependencies, and follow the project-specific README for further setup instructions.
