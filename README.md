<h1 align="center">Oi 👋, eu sou a Helen</h1>
<h3 align="center">Apaixonada por tecnologia e desenvolvimento</h3>

- 💬 Me pergunte sobre **ServiceDesk, Suporte de TI, Hardware e Software.**

- 📫 Você me encontra através do e-mail: **contatohelenlopes@gmail.com**

- 📄 Experiências profissionais: [https://www.linkedin.com/in/helenblopes](https://www.linkedin.com/in/helenblopes)

- 💡 Conheça um pouco do meu desenvolvimento: [https://github.com/helenblopes/portfolio](https://github.com/helenblopes/portfolio)

<h3 align="left">Connect with me:</h3>
<p align="left">
<a href="https://www.linkedin.com/in/helenblopes" target="blank"><img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/linked-in-alt.svg" alt="https://www.linkedin.com/in/helenblopes" height="30" width="40" /></a>
<a href="https://discord.gg/helenblopes" target="blank"><img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/discord.svg" alt="helenblopes" height="30" width="40" /></a>
</p>

name: Generate snake animation

on:
  schedule: # execute every 12 hours
    - cron: "* */12 * * *"

  workflow_dispatch:

  push:
    branches:
    - master

jobs:
  generate:
    permissions:
      contents: write
    runs-on: ubuntu-latest
    timeout-minutes: 5

    steps:
      - name: generate snake.svg
        uses: Platane/snk/svg-only@v3
        with:
          github_user_name: ${{ github.repository_owner }}
          outputs: dist/snake.svg?palette=github-dark


      - name: push snake.svg to the output branch
        uses: crazy-max/ghaction-github-pages@v3.1.0
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}


<!---
helenblopes/helenblopes is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
