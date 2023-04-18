# 💫 About Me:
👨‍💻 Olá, sou um desenvolvedor em aprendizado e atualmente estou focando meus estudos em Python. Meu objetivo é me tornar um especialista em backend e construir soluções robustas e escaláveis para as necessidades dos usuários.<br><br>💻 Estou aprendendo sobre os principais frameworks de desenvolvimento web em Python, como Django e Flask, bem como aprimorando meus conhecimentos em bancos de dados relacionais e não relacionais.<br><br>📚 Além disso, estou me mantendo atualizado com as melhores práticas de desenvolvimento de software, incluindo versionamento de código, testes automatizados e implementação contínua.<br><br>🤝 Estou animado para colaborar com outros desenvolvedores e aprender com a comunidade de desenvolvimento de software. Estou buscando oportunidades para desenvolver minhas habilidades e aplicar meus conhecimentos em projetos desafiadores.<br><br>🚀 Estou comprometido em evoluir constantemente como desenvolvedor e em fornecer soluções de alta qualidade para atender às necessidades dos usuários finais.


## 🌐 Socials:
[![Instagram](https://img.shields.io/badge/Instagram-%23E4405F.svg?logo=Instagram&logoColor=white)](https://instagram.com/bren.o_) [![LinkedIn](https://img.shields.io/badge/LinkedIn-%230077B5.svg?logo=linkedin&logoColor=white)](https://linkedin.com/in/brenovinicius-dev) [![Stack Overflow](https://img.shields.io/badge/-Stackoverflow-FE7A16?logo=stack-overflow&logoColor=white)](https://stackoverflow.com/users/21673167) 

# 💻 Tech Stack:
![Python](https://img.shields.io/badge/python-3670A0?style=flat&logo=python&logoColor=ffdd54) ![.Net](https://img.shields.io/badge/.NET-5C2D91?style=flat&logo=.net&logoColor=white) ![Angular](https://img.shields.io/badge/angular-%23DD0031.svg?style=flat&logo=angular&logoColor=white) ![MySQL](https://img.shields.io/badge/mysql-%2300f.svg?style=flat&logo=mysql&logoColor=white)
# 📊 GitHub Stats:
![](https://github-readme-stats.vercel.app/api?username=Brenoglobdev&theme=dracula&hide_border=false&include_all_commits=true&count_private=false)<br/>
![](https://github-readme-streak-stats.herokuapp.com/?user=Brenoglobdev&theme=dracula&hide_border=false)<br/>
![](https://github-readme-stats.vercel.app/api/top-langs/?username=Brenoglobdev&theme=dracula&hide_border=false&include_all_commits=true&count_private=false&layout=compact)

---
[![](https://visitcount.itsvg.in/api?id=Brenoglobdev&icon=5&color=1)](https://visitcount.itsvg.in)

<!-- Proudly created with GPRM ( https://gprm.itsvg.in ) -->

# Nome da Actions:  
name: Snake Game

# Controlador do tempo que sera feito a atualização dos arquivos.
on:
  schedule:
      # Será atualizado a cada 5 horas.
    - cron: "0 */5 * * *"

# Permite executar na na lista de Actions (utilizado para testes de build).
  workflow_dispatch:

# Regras
jobs:
  build:
    runs-on: ubuntu-latest
    steps:

    # Checks repo under $GITHUB_WORKSHOP, so your job can access it
      - uses: actions/checkout@v2

    # Repositorio que será utilizado para gerar os arquivos.
      - uses: Platane/snk@master
        id: snake-gif
        with:
          github_user_name: Formandodev #Seu usuario
          gif_out_path: dist/github-contribution-grid-snake.gif
          svg_out_path: dist/github-contribution-grid-snake.svg

      - run: git status

      # Para as atualizações.
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

