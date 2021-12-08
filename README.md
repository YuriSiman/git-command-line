<div id="top"></div>

<br/>
<div align="center">
    <img src="./readme-images/git.png" alt="Logo" width="100" height="100" />
    <h1 align="center">Comandos Git</h1>
    <p align="center">Comandos git para controle de versão</p>
</div>

<br/>

<div align="center">
    <a href="https://github.com/YuriSiman/git-command-line/blob/master/LICENSE" target="_blank">
      <img alt="LICENSE" src="https://img.shields.io/badge/license-mit-%23A6CE39?style=for-the-badge&logo=github" />
    </a>
    <a href="https://github.com/YuriSiman" target="_blank">
      <img alt="GitHub" src="https://img.shields.io/badge/github-perfil-%237159c1?style=for-the-badge&logo=github" />
    </a>
    <a href="https://yurisiman.com.br" target="_blank">
      <img alt="Site" src="https://img.shields.io/badge/site-yurisiman-E0A80D?style=for-the-badge&logo=Purism" />
    </a>
    <a href="https://www.linkedin.com/in/yurisiman/" target="_blank">
      <img alt="Linkedin" src="https://img.shields.io/badge/linkedin-social-0A66C2?style=for-the-badge&logo=LinkedIn" />
    </a>
    <a href="mailto:contato@yurisiman.com.br" target="_blank">
      <img alt="Gmail" src="https://img.shields.io/badge/email-contato-EA4335?style=for-the-badge&logo=Gmail" />
    </a>
</div>

<br/>

## :clipboard: Sobre o Projeto

Este repositório foi criado com o objetivo de ser uma fonte de consulta para desenvolvedores que trabalham com versionamento de código utilizando git em linha de comando.

Aproveite! :octocat:

---

## :pencil: Pré-requisitos

1. Se você não possui o git instalado, acesse [aqui](https://git-scm.com/downloads) e instale conforme o seu sistema operacional.
2. Clone este repositório em sua máquina local

   ```sh
   git clone https://github.com/YuriSiman/git-command-line.git
   ```

---

## :dart: Tópicos

<details>
  <summary>Comandos</summary>
  <ul>
    <li><a href="#configuracoes-iniciais">Configurações Iniciais</a></li>
    <li><a href="#trabalhando-com-repositorio-local">Trabalhando com Repositório Local</a></li>
    <li><a href="#trabalhando-com-branchs">Trabalhando com Branchs</a></li>
    <li><a href="#trabalhando-com-repositorio-remoto">Trabalhando com Repositório Remoto</a></li>
  </ul>
</details>

---

## :rocket: Vamos Começar

### Comandos Git

<div id="configuracoes-iniciais"></div>

### Configurações Iniciais

Exibir credenciais de email, usuário e outros...

```sh
git config --list
```

Configurando seu nome de usuário

```sh
git config --global user.name "Nome Usuário"
```

Configurando seu e-mail

```sh
git config --global user.email "seuemail@gmail.com"
```

Verificar a versão do git instalada

```sh
git --version
```

Buscando por mais informações e comandos git

```sh
git help
```

<p align="right"><a href="#top">Início ↑</a></p>

---

<div id="trabalhando-com-repositorio-local"></div>

### Trabalhando com Repositório Local

Iniciando um repositório local

```sh
git init
```

Deletando um repositório local - deletando a pasta oculta .git (powershell)

```sh
rm .git -force
```

Adicionando as modificações realizadas na Staging Area (track)

```sh
git add .

ou

git add nome-do-arquivo.txt
```

Verificando o status da branch

```sh
git status
```

Removendo as modificações realizadas antes de ir para a Staging Area

```sh
git checkout .

ou

git checkout nome-do-arquivo.txt
```

Desfazer o comando git add, retirando as modificações da Staging Area

```sh
git reset

ou

git rm --cached nome-do-arquivo.txt
```

Gerar o commit das suas modificações

```sh
git commit -m "Nome do Commit"
```

Visualização de log - histórico de todos os commits que foram realizados dentro do repositório local

```sh
git log --oneline

ou

git log
```

Visualizar as modificações que foram adicionadas ou removidas

```sh
git diff
```

Sobrescrever o commit anterior do repositório local - "Editar" o commit anterior do repositório local

```sh
git commit -m "Nova Mensagem" --amend
```

Cancelar um ou mais commits na ordem conforme o número informado, devolvendo os arquivo modificados para a Staging Area

```sh
git reset HEAD~1 --soft
```

Cancelar um ou mais commits na ordem conforme o número informado, permanentemente, excluindo as implementações

```sh
git reset HEAD~1 --hard
```

Definindo uma versão para o seu repositório

```sh
git tag nome-da-versao
```

Voltando à versão desejada - Apaga tudo o que foi implementado e volta o repositório para a sua versão da tag criada

```sh
git checkout nome-da-versao
```

Voltando a qualquer commit conforme o seu número

```sh
git checkout nome-do-commit
```

Mostrar conteúdo de um commit

```sh
git show
```

<p align="right"><a href="#top">Início ↑</a></p>

---

<div id="trabalhando-com-branchs"></div>

### Trabalhando com Branchs 

Criando uma nova branch e acessando ela, mudando da branch atual para a que foi criada

```sh
git checkout -b nome-da-branch
```

Criando uma nova branch sem acessar ela, permanendo na branch atual

```sh
git branch nome-da-branch
```

Navegando entre branchs

```sh
git checkout nome-da-branch
```

Ver todas as branchs

```sh
git branch
```

Deletando uma branch

```sh
git branch -d nome-da-branch
```

Fazer merge da master com alguma feature - É preciso ir para a master primeiro para efetuar o merge. Este comando faz com que todos os commits da sua feature passem a fazer parte do log da master

```sh
git merge nome-da-branch
```

Fazer merge da master com alguma feature - É preciso ir para a master primeiro para efetuar o merge. Este comando não gera um commit automaticamente, ele faz com que apenas o commit desse merge passe a fazer parte do log da master

```sh
git merge nome-da-branch --squash
```

Desfazer um merge dentro da master

```sh
git reset HEAD~1 --hard
```

Abortar o merge em caso de conflitos

```sh
git merge --abort
```

Pegar tudo que não foi commitado numa feature e "esconder" para que se possa mudar de branch sem levar as alterações junto - isso quando ainda não foi gerado o commit

```sh
git stash
```

Visualizar todos os stash

```sh
git stash list
```

Pega as modificações "escondidas" pelo stash, é possível puxar pelo índice - continua com uma cópia no stash

```sh
git stash apply 1
```

Deletando um stash conforme a sua referência numérica

```sh
git stash drop 1
```

Deleta todos os stash

```sh
git stash clear
```

<p align="right"><a href="#top">Início ↑</a></p>

---

<div id="trabalhando-com-repositorio-remoto"></div>

### Trabalhando com Repositório Remoto 

Adicionando um repositório "origin" remoto em um repositório local

```sh
git remote add origin https://nome-do-repositorio.git
```

Visualizando os repositórios remotos adicionados ao seu repositório local 

```sh
git remote
```

Verificando se há diferenças entre o repositório remoto adicionado com o que está remoto no GitHub

```sh
git remote show origin
```

Enviando conteúdo do repositório local para o remoto - no exemplo, da branch master

```sh
git push -u origin master
```

Enviando conteúdo do repositório local para o remoto - todas as branches

```sh
git push -u origin --all
```

Enviando conteúdo do repositório local para o remoto - comando simplificado para os envios após o primeiro git push -u origin master

```sh
git push
```

Forçando o envio de um push - não funciona na master

```sh
git push --force

ou

git push -f
```

Removendo um repositório "origin" de um repositório local (desvinculando o repositório local com o remoto)

```sh
git remote remove origin
```

Mostra todo o histórico de commits realizados, excluídos ou não

```sh
git reflog
```

Voltando seu repositório a um commit qualquer, seja deletado ou não

```sh
git cherry-pick número-do-commit
```

Baixar o conteúdo do repositório remoto para o seu local já fazendo um commit e mesclando os conteúdos

```sh
git pull
```

Baixar o conteúdo do repositório remoto para o seu local, sem mesclar (É interessante para poder validar primeiro o conteúdo que foi baixado, dentro da origin/master, e depois fazer o merge)

```sh
git fetch
```

Clonar o repositório remoto para o seu local

```sh
git clone https://nome-do-repositorio.git
```

Clonar uma branch específica de um repositório remoto para o seu local

```sh
git clone --single-branch --branch nome-da-branch https://nome-do-repositorio.git
```

Clonar o repositório remoto para o seu local sem trazer os arquivos e implementações

```sh
git clone -n https://nome-do-repositorio.git
```

Após um ```git clone -n https://nome-do-repositorio.git ``` você precisa especificar o que você quer que venha do repositório clonado para o seu local

```sh
git checkout HEAD nome-do-arquivo

ou

git checkout HEAD nome-do-diretório
```

Visualizando os commit do seu repositório remoto

```sh
git log origin/master
```

<p align="right"><a href="#top">Início ↑</a></p>

---

## :vertical_traffic_light: Status do Projeto

:heavy_check_mark: Concluído

---

## :thinking: Contribuindo

> Passo a passo de como contribuir...

### Passo 1

* :fork_and_knife: Fork este repositório!

### Passo 2

* :dancers: Clone este repositório para sua máquina local usando `git clone https://github.com/YuriSiman/git-command-line.git`

### Passo 3

* :trident: Crie sua feature branch usando `git checkout -b minha-feature`

### Passo 4

* :white_check_mark: Commit suas mudanças usando `git commit -m "feat: Minha nova feature"`

### Passo 5

* :pushpin: Dê um push usando `git push -u origin minha-feature`

### Passo 6

* :arrows_clockwise: Crie um novo pull request

Depois que seu pull request for mesclado, você pode excluir sua feature branch  

> Caso tenha dúvidas, confira este guia de como [contribuir no GitHub](https://github.com/firstcontributions/first-contributions)  

---

## :speech_balloon: Suporte

> Entre em contato comigo...  

* Me chame pelo [Linkedin](https://www.linkedin.com/in/yurisiman/)  
* Me mande um e-mail [contato@yurisiman.com.br](mailto:contato@yurisiman.com.br)  

---

## :pencil: Licença

<a href="https://github.com/YuriSiman/git-command-line/blob/master/LICENSE" target="_blank">
  <img alt="LICENSE" src="https://img.shields.io/badge/license-mit-%23A6CE39?style=for-the-badge&logo=github" />
</a>

##

Code your life :octocat:

<p align="right"><a href="#top">Início ↑</a></p>
