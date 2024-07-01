---
title: 🧑‍💻️ Project description
summary: Project overview and motivation
date: 2024-05-27

# Featured image
# Place an image named `featured.jpg/png` in this page's folder and customize its options here.
image:
  caption: 'Image credit: [Link](https://developers.google.com/open-source/gsoc/resources/marketing?hl=es-419)'

authors:
  - admin

#tags:
#  - Academic
#  - Wowchemy
#  - Markdown 
---

Hi 👋

## Overview and motivation

This summer I am working on the Google Summer of Code(GSoC) program, under the supervision of [**Dr. Gonzalo Vidal**](https://gonza10v.github.io/), in collaboration with the [iGEM Engineering Committee](https://technology.igem.org/engineering-committee) and the [National Resource for Network Biology(NRNB)](https://nrnb.org/)

I am integrating a [script developed to check if a genetic design is synthesizable](https://github.com/SynBioDex/SBOL-utilities/blob/develop/sbol_utilities/calculate_complexity_scores.py), into the [iGEM Engineering workflow](https://github.com/iGEM-Engineering/iGEM-actions), using GitHub Actions. 

Synthetic biologists use the Design, Build, Test, Learn (DBTL) cycle to engineer biological systems. The [Synthetic Biology Open Language (SBOL)](https://sbolstandard.org/) was developed by the community as a standard to represent biological designs and covers the whole DBTL cycle. Although this standard is used and agreed by the community it is mostly used in its visual format and the data format has not been widely adopted, being PDF the primary format to share DNA sequences. The adoption of SBOL by the community can increase the reproducibility of experiments, facilitating building upon previous knowledge. 
To streamline the DBTL cycle and increase the adoption of SBOL, the development of a workflow prototyped at iGEM is necessary, that uses complexity score functions to facilitate DNA synthesis orders using Excel as user interface and storing metadata in SBOL.

