---
title: 🧑‍💻️ GitHub Actions in the iGEM Distribution repository
summary: Let's dive into GitHub Actions and their role in the iGEM Engineering distribution repository
date: 2024-06-11

# Featured image
# Place an image named `featured.jpg/png` in this page's folder and customize its options here.
image:
  caption: 'Image credit: [Link](https://igem.org/)'

authors:
  - admin

#tags:
#  - Academic
#  - Wowchemy
#  - Markdown 
---

Hi 👋

## Overview

There is a [centralized page](https://github.com/iGEM-Engineering/iGEM-actions) that manages the iGEM Engineering organization GitHub Actions.


![This is how it should look like](igem_actions_1.jpg)


The idea is that the different iGEM packages(i.e. Plants, Anderson Promoters) have their own repository and within this, it will call the iGEM Actions.

Let's breakdown the code in the [action.yml](https://github.com/iGEM-Engineering/iGEM-actions/blob/main/action.yml) file that is in the repository. This file is in charge or running the actions when they are called from other repositories.

This GitHub Action workflow file is designed to automate a series of tasks to generate a distribution from user-readable files. Below is an explanation of each part of the workflow:

## Workflow Metadata

* **name**: generate-distribution - The name of the GitHub Action.
* **description**: Describes what the GitHub Action does - "A Github action to generate a distribution from user-readable files."

## Inputs

* **repo-token**:
  * **description**: The GitHub token used to manage committing and pushing changes.
  * **required**: true - This input is mandatory for the action to run.
  * **default**: **${{ github.token }}** - Default value is the GitHub token provided by the GitHub Actions runtime.

## Runs

* **using**: composite - Indicates that this is a composite action composed of multiple steps.
* **steps**: Each step in the composite action.

## Steps

1. **Check out this repository for building**
  * Uses **actions/checkout@v3** to check out the repository so that the workflow has access to the code.

2. **Set up Python 3.9**
  * Uses **actions/setup-python@v4** to set up Python 3.9.

3. **Set up Node.js 14**
  * Uses **actions/setup-node@v3** to set up Node.js 14.

4. **Install dependencies**
  * Uses **bash** to run commands to upgrade pip and install dependencies listed in **scripts/requirements.txt**.

5. **Regularize directories**
  * Uses **bash** to run a Python script **regularize_directories.py** to standardize directory structure.

6. **Update CSVs**
  * Uses **bash** to run a Python script **export_csvs.py** to update CSV files.

7. **Update SBOL**
  * Uses **bash** to run a Python script **export_sbol.py** to update SBOL files.

8. **Import parts and devices**
  * Uses **bash** to run a Python script **import_parts.py** to import parts and devices.

9. **Convert SBOL2 imports to SBOL3**
  * Uses **bash** to run a Python script **convert_sbol_2to3.py** to convert SBOL2 imports to SBOL3.

10. **Collate packages**
  * Uses **bash** to run a Python script **collate_packages.py** to collate packages.

11. **Create vector build plans**
  * Uses **bash** to run a Python script **expand_combinations.py** to create vector build plans.

12. **Generate markdown from packages**
  * Uses **bash** to run a Python script **generate_markdown.py** to generate markdown documentation from packages.

13. **Build distribution**
  * Uses **bash** to run a Python script **build_distribution.py** to build the distribution.

14. **Commit changes, ready to push**
  * Uses **bash** to run a series of Git commands to:
    * Configure Git user email and name.
    * Add files to the staging area (*.nt, *.md, *.fasta, *.gb, README.md, and files in the **views** directory).
    * Commit the changes if there are any differences.

15. **Push changes**
  * Uses **ad-m/github-push-action@master** to push the committed changes to the repository.
  * Uses the provided **repo-token** for authentication.
  * Pushes to the current branch **${{ github.ref }}**.

## Author and Branding

* **author**: iGEM-Engineering - The author of the action.
* **branding**:
  * **icon**: layers - The icon for the action.
  * **color**: purple - The color for the action.

## Important Points

* **${{ github.token }}**: A default token provided by GitHub Actions that allows the workflow to interact with the GitHub API.
* **${{ github.action_path }}**: The path to the directory containing the action definition file.
* **${{ github.ref }}**: The branch or tag ref that triggered the workflow.





