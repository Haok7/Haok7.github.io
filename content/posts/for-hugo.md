---
title: "For Hugo"
date: 2023-03-20T12:56:14Z
draft: true
summary: "Tutorial for Hugo."
tags: ["Hugo","PaperMod","github pages","github actions"]
categories: ["Tutorial"]
---

## Quick Start

```
brew install hugo

hugo new site myblog -f yml
cd myblog
git init

git submodule add --depth=1 https://github.com/adityatelange/hugo-PaperMod.git themes/PaperMod

# When you reclone your repo (submodules may not get cloned automatically)
git submodule update --init --recursive
# Updating theme
git submodule update --remote --merge

echo "theme: PaperMod" >> config.yml
echo "buildDrafts: true" >> config.yml
hugo new posts/my-first-post.md

hugo server
```

## Customisation

### [Robots.txt File](https://gohugo.io/templates/robots/)

```
User-agent: *
{{ range .Pages }}
Disallow: {{ .RelPermalink }}
{{ end }}
```

This template creates a robots.txt file with a `Disallow` directive for each page on the site. Search engines that honor the [Robots Exclusion Protocol](https://robot-txt.com/sem-glossary/a-guide-to-robot-txt-files/?gclid=CjwKCAjwiOCgBhAgEiwAjv5whFDwgp3ozM9vDqtDSRS-AU46ZzygnMEzApETKhD6OaYGkFI7Vdp4aRoCMD8QAvD_BwE) will not crawl any page on the site.

### [Github Pages & Actions](https://theplaybook.dev/docs/deploy-hugo-to-github-pages/)

```
echo "foopi.top" >> README.md
echo ".hugo_build.lock\npublic/\nresources/" > .gitignore
git init
git config --global --edit
git add ./
git commit -m "first commit"
git remote add origin git@github.com:Haok7/Haok7.github.io.git
git push -u origin main
```

