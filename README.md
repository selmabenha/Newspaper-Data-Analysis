# HUM-450 Impresso
This repository contains all the source code for the project of the course HUM-450. For this project, we are using the Impresso database. 
 - Link to the data: https://drive.google.com/drive/folders/1MrYjVUJPSUubAc8UD3Xr5nPydXtFjPC4?usp=drive_link
 - Link to the Minutes: https://docs.google.com/document/d/1MZljVlTuPxJEN6x6_YJ1NsprmuwVyBtuHUd1bHjtjUI/edit?usp=drive_link

## Installation
- Clone the repo

```bash
git clone git@github.com:edouardkoehn/HUM-450.git
```
- Create your virtual env
```bash
conda create -n HUM-450 python=3
conda activate HUM-450
```
- Install poetry
```bash
pip install poetry
```
- install the modul and set up the precommit
```bash
poetry install
poetry run pre-commit install
poetry env info
```

## Managing dependancies
- to add an dependancy with poetry for exemple numpy
```bash
poetry add numpy
```
It would automatically install and udpate the pyproject.toml file. If you didn't specifie it, it would add it to the tool.poetry.dependencies.

- to add an dependancy with poetry to a specific group
```bash
poetry add pytest --group test
```
It would automatically install and udpate the pyproject.toml file. The dependancie would be attached to the tool.poetry.dependcies.group.
[More info about poetry](https://python-poetry.org/docs/managing-dependencies/#adding-a-dependency-to-a-group)

## Pre-commit config
Pre-commit hook are small software that are called when you do a git commit. Those hooks do several test on you code (formating, imports, etc. ). If not all the tests have been passed, the pre-commmit would not allow you to do the commit. You would have to resolve each of the error before beeing able to do the commit.

Good pratrice with pre-commit :
1) Git commit regularly
2) Never git commit when you are in a rush
