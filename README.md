# Student Blog Template

This repository is a template for students to create and deploy their own blog using Markdown files.

## Creating a Blog Post
1. Open the `/posts` folder.
1. Copy `_template.md`
1. Rename your copy (example: `2026-02-14-first-blog.md`)
1. Edit the front matter at the top:
    - title
    - date
    - summary (optional)
    - tags (optional)
1. Write your blog post underneath in markdown
1. [Commit](https://docs.github.com/en/desktop/making-changes-in-a-branch/committing-and-reviewing-changes-to-your-project-in-github-desktop) and [push](https://docs.github.com/en/desktop/making-changes-in-a-branch/pushing-changes-to-github-from-github-desktop) your changes to the `main` branch.

Your blog will automatically update and publish online.

Your site will be available at: `https://<your-github-username>.github.io/<repository-name>`.

### Professional Tip
Your blog is public and can be shared with future employers. Consider treating posts as part of your portfolio and edit the `/assets/style.css` to show off your design skills.

## What Happens Behind the Scenes
This template automatically:
- Builds your blog
- Converts Markdown into webpages
- Publishes your site online
- The only configuration needed is to set the "Build and deployment" source to "GitHub Actions". This is found in "Settings" ➔ "Pages".


## Do Not Edit These Folders
These are automatically generated or required for publishing:
```
dist/
.github/
scripts/
```

## Optional: Preview Your Blog Locally
This is only needed if you want to test changes before publishing.
1. Install the required dependencies: `npm install`
1. Run the build script: `npm run build`

The generated files will be in the `dist` folder. You can launch this using Live Server in VSCode.

# AI Acknowledgement

This project concept and design direction were developed from my own ideas and decision-making process. I used AI assistance to help organise my thoughts, refine written explanations, compare possible directions, and structure my development blog posts more clearly.

AI was used as a support tool for wording, planning, and reflection. The core project idea, community direction, feature selection, design judgement, and final decisions are my own. I reviewed and edited the AI-assisted text to ensure that it accurately represents my thinking and the development process of my A2 Web App Prototype.

AI was not used as a replacement for my own design decisions. It was used to help communicate my reasoning more clearly.