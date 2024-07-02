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











