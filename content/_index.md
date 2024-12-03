---
title: "Lab10 - Hugo Web Page"
description: "A simple web page created using Hugo."
draft: false
---

## Installation Steps:

1. **Set up a Conda environment** for local testing:
   - Create and activate a new Conda environment for Hugo:
     ```bash
     conda create -n hugo_env -y
     conda activate hugo_env
     ```
   - Install Hugo from the conda-forge channel:
     ```bash
     conda install -c conda-forge hugo -y
     ```

2. **Verified the Hugo installation**:
   - Confirmed the installation by checking the Hugo version:
     ```bash
     hugo version
     ```

3. **Created a new site** using the command:
   ```bash
   hugo new site mywebsite
   ``` 

## Development Process:

I built the page by creating a new content file `_index.md` and writing content in Markdown. Hugo automatically generates the HTML pages from the Markdown files.

## Challenges Encountered:

- **Theme Issues:** Initially, the site wouldn't render properly because I forgot to set the `theme` parameter in the `config.toml` file. I fixed it by adding `theme = "ananke"`.
- **Draft Content:** My content wasn't appearing because it was marked as draft. I changed `draft: true` to `draft: false` in the front matter.

## Conclusion:

Hugo made it easy to generate a static website quickly. The main challenges were related to configuration settings, which were resolved by carefully reading the documentation.
