<!-- BANNER -->
<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&height=220&color=0:0d1117,100:30363d&text=Caio%20Henry&fontColor=ffffff&fontSize=52&fontAlignY=38&desc=Estudante%20de%20TI&descColor=8b949e&descSize=18&descAlignY=58&animation=fadeIn" alt="Banner Caio Henry" />
</div>

<!-- TYPING ANIMATION -->
<div align="center">
  <a href="https://github.com/Shiroo849">
    <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=500&size=20&duration=3000&pause=1000&color=8B949E&center=true&vCenter=true&width=520&lines=Estudante+de+TI;Java+%7C+Python;Aprendendo+na+pr%C3%A1tica" alt="Typing SVG" />
  </a>
</div>

<br>

## 👤 Sobre mim

Sou o **Caio**, estudante de TI. Uso o GitHub para colocar em prática o que aprendo, hoje principalmente com **Java** e **Python**.

<br>

## 🛠️ Tecnologias

<div align="center">
  <img src="https://skillicons.dev/icons?i=java,python,github&theme=dark" alt="Tecnologias" />
</div>

<br>

## 🚀 Projetos

<div align="center">
  <a href="https://github.com/Shiroo849/cadastro-produtos">
    <img src="https://github-readme-stats.vercel.app/api/pin/?username=Shiroo849&repo=cadastro-produtos&theme=dark&bg_color=0d1117&title_color=ffffff&text_color=8b949e&icon_color=ffffff&border_color=30363d" alt="cadastro-produtos" />
  </a>
  <a href="https://github.com/Shiroo849/Estacionamento">
    <img src="https://github-readme-stats.vercel.app/api/pin/?username=Shiroo849&repo=Estacionamento&theme=dark&bg_color=0d1117&title_color=ffffff&text_color=8b949e&icon_color=ffffff&border_color=30363d" alt="Estacionamento" />
  </a>
</div>

<br>

## 📊 GitHub Stats

<div align="center">
  <img height="170" src="https://github-readme-stats.vercel.app/api?username=Shiroo849&show_icons=true&hide_border=true&bg_color=0d1117&title_color=ffffff&text_color=8b949e&icon_color=ffffff&ring_color=ffffff" alt="GitHub Stats" />
  <img height="170" src="https://github-readme-stats.vercel.app/api/top-langs/?username=Shiroo849&layout=compact&hide_border=true&bg_color=0d1117&title_color=ffffff&text_color=8b949e" alt="Top Languages" />
</div>

<br>

<div align="center">
  <img src="https://streak-stats.demolab.com?user=Shiroo849&theme=dark&hide_border=true&background=0d1117&ring=ffffff&fire=ffffff&currStreakLabel=ffffff&sideLabels=8b949e&currStreakNum=ffffff&sideNums=ffffff&dates=6e7681" alt="GitHub Streak" />
</div>

<br>

## 📈 Atividade

<div align="center">
  <img src="https://github-readme-activity-graph.vercel.app/graph?username=Shiroo849&bg_color=0d1117&color=8b949e&line=ffffff&point=ffffff&area=true&area_color=30363d&hide_border=true" alt="Activity Graph" />
</div>

<br>

## 🏆 Troféus

<div align="center">
  <img src="https://github-profile-trophy.vercel.app/?username=Shiroo849&theme=onedark&no-frame=true&no-bg=true&margin-w=12&row=1&column=7" alt="GitHub Trophies" />
</div>

<br>

## 🐍 Contribuições

<div align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/Shiroo849/Shiroo849/output/github-contribution-grid-snake-dark.svg" />
    <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/Shiroo849/Shiroo849/output/github-contribution-grid-snake.svg" />
    <img alt="Snake animation" src="https://raw.githubusercontent.com/Shiroo849/Shiroo849/output/github-contribution-grid-snake.svg" />
  </picture>
</div>

<br>

## 🌐 Contato

<div align="center">
  <a href="https://www.linkedin.com/in/caio-henry-45787341a/">
    <img src="https://img.shields.io/badge/LinkedIn-Caio%20Henry-0d1117?style=for-the-badge&logo=linkedin&logoColor=white&labelColor=30363d" alt="LinkedIn" />
  </a>
  <a href="https://github.com/Shiroo849">
    <img src="https://img.shields.io/badge/GitHub-Shiroo849-0d1117?style=for-the-badge&logo=github&logoColor=white&labelColor=30363d" alt="GitHub" />
  </a>
</div>

<!-- RODAPÉ -->
<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&height=120&color=0:30363d,100:0d1117&section=footer&text=Sempre%20aprendendo.&fontColor=8b949e&fontSize=18&fontAlignY=68" alt="Rodapé" />
</div>name: Generate Snake

on:
  schedule:
    - cron: "0 0 * * *"
  workflow_dispatch:
  push:
    branches:
      - main

permissions:
  contents: write

jobs:
  generate:
    runs-on: ubuntu-latest
    steps:
      - uses: Platane/snk/svg-only@v3
        with:
          github_user_name: ${{ github.repository_owner }}
          outputs: |
            dist/github-contribution-grid-snake.svg
            dist/github-contribution-grid-snake-dark.svg?palette=github-dark

      - uses: crazy-max/ghaction-github-pages@v3.1.0
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
