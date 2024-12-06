---
title: "Lab10 - Hugo Web Page"
description: "A simple web page created using Hugo."
draft: false
---

## Installation Steps:

### Local Deployment

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

2. **Verify the Hugo installation**:
   - Confirm the installation by checking the Hugo version:

     ```bash
     hugo version
     ```

3. **Create a new Hugo site**:
   - Initialize a new site using the command:

     ```bash
     hugo new site mywebsite
     ```

4. **Add a theme**:
   - Navigate to the project directory and add a theme as a Git submodule:

     ```bash
     cd mywebsite
     git init
     git submodule add https://github.com/theNewDynamic/gohugo-theme-ananke themes/ananke
     ```

   - Update the `config.toml` file to specify the theme:

     ```toml
     theme = "ananke"
     ```

5. **Add content**:
   - Create content by adding a new Markdown file, e.g., `content/_index.md`, and populate it with your content.

6. **Run the Hugo development server**:
   - Test the site locally with the following command:

     ```bash
     hugo server
     ```

   - Open the site in a browser at `http://localhost:1313`.

### Challenges Encountered
- **Theme Issues**: The site didn't render initially due to the theme not being set. Fixed by updating `theme` in `config.toml`.
- **Draft Content**: Content marked as draft did not appear. Changed `draft: true` to `draft: false`.

---

## Deployment on Netlify

### Prerequisites:
- A Netlify account.
- Git installed locally.
- A GitHub repository containing the Hugo project.

### Steps to Host on Netlify:

1. **Push your site to GitHub**:
   - Initialize a Git repository (if not already done):
     ```bash
     git init
     ```
   - Commit all changes and push to GitHub:
     ```bash
     git add .
     git commit -m "Initial commit"
     git branch -M main
     git remote add origin <your-github-repo-url>
     git push -u origin main
     ```

2. **Log in to Netlify**:
   - Log in and navigate to the "Sites" page.

3. **Import the project**:
   - Click **Add new site** > **Import an existing project**.

4. **Authorize GitHub access**:
   - Authorize Netlify to connect with your GitHub account and select the repository.

5. **Configure build settings**:
   - Set the build command to `hugo`.
   - Set the publish directory to `public`.

6. **Set environment variables**:
   - Add an environment variable for the Hugo version:
     ```bash
     Key: HUGO_VERSION
     Value: 0.139.3
     ```

7. **Deploy the site**:
   - Click **Deploy my new site** and wait for the build process to complete.

8. **Verify the deployment**:
   - Once deployed, click **Open production deploy** to view the live site.

---

## Configuration Files

### `netlify.toml`:
```toml
[build]
  command = "hugo"
  publish = "public"

[build.environment]
  HUGO_VERSION = "0.139.3"
```

### `config.toml`:
```toml
baseURL = "http://example.org/"
languageCode = "en-us"
title = "Hugo Web Page"
theme = "ananke"

[build]
  publish = "public"
  command = "hugo"
```

---

## Conclusion:
Hugo is a powerful static site generator that simplifies web development. While local development was straightforward, hosting on Netlify with continuous deployment added another layer of automation, enhancing productivity.
