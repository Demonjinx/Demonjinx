# 💫 Sobre eu:
Me chamo Thomas Stephan tenho 17 anos de idade<br><br>Estudante do Instituto Federal de São Paulo<br>Atuo no 3º ano do Ensino médio pelo curso de informática<br><br>Tenho conhecimento em Linguagem de programação (C, Java, Python e HTML), <br>Gerenciamento de projeto,  Lógica de programação e Banco de Dados.<br><br>Cursos feitos: Excel, PowerPoint, World.


## 🌐 Redes Sociais:
[![Instagram](https://img.shields.io/badge/Instagram-%23E4405F.svg?logo=Instagram&logoColor=white)](https://instagram.com/thomas_carm0) [![LinkedIn](https://img.shields.io/badge/LinkedIn-%230077B5.svg?logo=linkedin&logoColor=white)](https://linkedin.com/in/Thomas Stephan Carmo Claro) 

# 💻 Tech Stack:
![C](https://img.shields.io/badge/c-%2300599C.svg?style=for-the-badge&logo=c&logoColor=white) ![Java](https://img.shields.io/badge/java-%23ED8B00.svg?style=for-the-badge&logo=openjdk&logoColor=white) ![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
# 📊 GitHub Stats:
![](https://github-readme-stats.vercel.app/api?username=Demonjinx&theme=vue-dark&hide_border=false&include_all_commits=false&count_private=false)<br/>
![](https://github-readme-streak-stats.herokuapp.com/?user=Demonjinx&theme=vue-dark&hide_border=false)<br/>
![](https://github-readme-stats.vercel.app/api/top-langs/?username=Demonjinx&theme=vue-dark&hide_border=false&include_all_commits=false&count_private=false&layout=compact)

## 🏆 Uns prêmios do Git
![](https://github-profile-trophy.vercel.app/?username=Demonjinx&theme=radical&no-frame=false&no-bg=false&margin-w=4)

### 🔝 Melhores repositórios
![](https://github-contributor-stats.vercel.app/api?username=Demonjinx&limit=5&theme=dark&combine_all_yearly_contributions=true)

---
[![](https://visitcount.itsvg.in/api?id=Demonjinx&icon=0&color=0)](https://visitcount.itsvg.in)

<!-- Proudly created with GPRM ( https://gprm.itsvg.in ) -->
# GitHub Action for generating a contribution graph with a snake eating your contributions.

name: Generate Snake

# Controls when the action will run. This action runs every 6 hours.

on:
  schedule:
      # every 6 hours
    - cron: "0 */6 * * *"

# This command allows us to run the Action automatically from the Actions tab.
  workflow_dispatch:

# The sequence of runs in this workflow:
jobs:
  # This workflow contains a single job called "build"
  build:
    # The type of runner that the job will run on
    runs-on: ubuntu-latest

    # Steps represent a sequence of tasks that will be executed as part of the job
    steps:

    # Checks repo under $GITHUB_WORKSHOP, so your job can access it
      - uses: actions/checkout@v2

    # Generates the snake  
      - uses: Platane/snk@master
        id: snake-gif
        with:
          github_user_name: Demonjinx
          # these next 2 lines generate the files on a branch called "output". This keeps the main branch from cluttering up.
          gif_out_path: dist/github-contribution-grid-snake.gif
          svg_out_path: dist/github-contribution-grid-snake.svg

     # show the status of the build. Makes it easier for debugging (if there's any issues).
      - run: git status

      # Push the changes
      - name: Push changes
        uses: ad-m/github-push-action@master
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          branch: master
          force: true

      - uses: crazy-max/ghaction-github-pages@v2.1.3
        with:
          # the output branch we mentioned above
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
