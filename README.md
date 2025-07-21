# Hi, I'm Ofeleon 👋

A Computer Science student passionate about **Web3** and **AI**.  
Currently building JavaScript, Solidity, and Python skills through hands-on projects.

## 🔭 Featured Project  
- [Palindrome Checker](https://xvioz.github.io/palindrome-checker/) — simple palindrome validator with HTML/CSS/JS

## 🌱 Learning Path  
- Phase 1: JavaScript & Web Essentials  
- Phase 2: Solidity & Web3 dApps  
- Phase 3: Python & Machine Learning  
- Phase 4: Integrate AI + Web3

## 🔹 Learning roadmap:
- Web foundations (JS, HTML, CSS)
- Solidity & dApp development
- Python for AI + ML

## 📬 Let's Connect  
- [LinkedIn](https://www.linkedin.com/in/ofeleon-moreno/)  
- GitHub: `@Xvioz`

# 📊 GitHub Stats:
![](https://github-readme-stats.vercel.app/api?username=Xvioz&theme=tokyonight&hide_border=false&include_all_commits=false&count_private=false)<br/>
![](https://nirzak-streak-stats.vercel.app/?user=Xvioz&theme=tokyonight&hide_border=false)<br/>
![](https://github-readme-stats.vercel.app/api/top-langs/?username=Xvioz&theme=tokyonight&hide_border=false&include_all_commits=false&count_private=false&layout=compact)

---
[![](https://visitcount.itsvg.in/api?id=Xvioz&icon=0&color=0)](https://visitcount.itsvg.in)


<!-- Proudly created with GPRM ( https://gprm.itsvg.in ) -->
name: Generate pacman animation

on:
  schedule: # execute every 12 hours
    - cron: "* */12 * * *"

  workflow_dispatch:

  push:
    branches:
    - main

jobs:
  generate:
    permissions:
      contents: write
    runs-on: ubuntu-latest
    timeout-minutes: 5

    steps:
      - name: generate pacman-contribution-graph.svg
        uses: abozanona/pacman-contribution-graph@main
        with:
          github_user_name: ${{ github.repository_owner }}


      - name: push pacman-contribution-graph.svg to the output branch
        uses: crazy-max/ghaction-github-pages@v3.1.0
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
