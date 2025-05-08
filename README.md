# Snake-Animation-Readme

<div align="center">

<picture>
  <source
    media="(prefers-color-scheme: dark)"
    srcset="https://raw.githubusercontent.com/platane/snk/output/github-contribution-grid-snake-dark.svg"
  />
  <source
    media="(prefers-color-scheme: light)"
    srcset="https://raw.githubusercontent.com/platane/snk/output/github-contribution-grid-snake.svg"
  />
  <img
    alt="github contribution grid snake animation"
    src="https://raw.githubusercontent.com/platane/snk/output/github-contribution-grid-snake.svg"
  />
</picture>
</div>
<hr>

###

Here’s a complete `README.md` file you can add to your GitHub repository. 
It explains `how to add the GitHub Snake Contribution Animation` step by step and includes the final embedding to show the snake animation in your profile.

---

### 
📄 `README.md`

```md
# 🐍 GitHub Snake Contribution Animation Guide

This guide explains how to add a **GitHub contribution snake animation** to your profile using GitHub Actions.

---

## 📦 Prerequisites

- A GitHub profile repository named exactly as your username.  
  Example: For username `ankz01`, repo should be `ankz01/ankz01`.

---

## ⚙️ Step 1: Create GitHub Workflow

Create the following folder and file in your profile repo:

```

.github/workflows/generate-snake.yml

````

Paste the following content into `generate-snake.yml`:

```yml
name: Generate Snake

on:
  schedule:
    - cron: "0 0 * * *" # runs daily at midnight
  push:
    branches:
      - main

jobs:
  generate:
    runs-on: ubuntu-latest
    steps:
      - uses: Platane/snk@v3
        with:
          github_user_name: ankz01
          outputs: |
            dist/github-contribution-grid-snake.svg

      - name: Push snake to the output branch
        uses: crazy-max/ghaction-github-pages@v3.1.0
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
````

---

## 🚀 Step 2: Update Your Profile README

In your `README.md`, add the following line to show the animation:

```md
![GitHub Snake](https://github.com/ankz01/ankz01/blob/output/github-contribution-grid-snake.svg)
```

---

## 🔁 Step 3: Push and Let the Action Run

1. Commit and push your changes.
2. Wait 1–2 minutes for the workflow to finish.
3. Make sure a new branch named `output` appears with `github-contribution-grid-snake.svg`.
4. The snake should now be visible in your README!

---

## 🛠 Common Issues

* ❗ Make sure the repo is named `ankz01/ankz01` (case-sensitive).
* ❗ Your `output` branch must not be protected.
* ❗ You must allow GitHub Actions to run on your repo (in Settings > Actions).
* ✅ The snake updates automatically every day.

---

## 🐍 Result Preview

> 🟢 Your GitHub contribution grid will animate like a snake crawling through your activity history!

---
###

Below is the complete `generate-snake.yml` file. Add this to your GitHub repo at:

```
.github/workflows/generate-snake.yml
```

---

### 
📄 `.github/workflows/generate-snake.yml`

```yml
name: Generate Snake

on:
  schedule:
    - cron: "0 0 * * *"  # Runs every day at midnight UTC
  push:
    branches:
      - main

jobs:
  generate:
    runs-on: ubuntu-latest

    steps:
      # Generates the snake animation in SVG
      - uses: Platane/snk@v3
        with:
          github_user_name: ankz01
          outputs: |
            dist/github-contribution-grid-snake.svg

      # Pushes the generated SVG to the output branch
      - name: Push snake to the output branch
        uses: crazy-max/ghaction-github-pages@v3.1.0
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```

---

### 
✅ Quick Recap:

1. Add this file to `.github/workflows/generate-snake.yml`
2. Commit and push to `main` branch
3. Wait for GitHub Actions to generate the SVG
4. Add this to your profile README:

```md
![GitHub Snake](https://github.com/ankz01/ankz01/blob/output/github-contribution-grid-snake.svg)
```


