<h1 align="center">Comandos Git</h1>

<p align="center">Comandos git para controle de versão e branches em repositório local e remoto</p>

## :clipboard: Tópicos

* [configuracoes-iniciais](https://github.com/YuriSiman/git-command-line#configuracoes-iniciais)
* [trabalhando-com-repositório-local](https://github.com/YuriSiman/git-command-line#trabalhando-com-repositório-local)
* [trabalhando-com-branchs](https://github.com/YuriSiman/git-command-line#trabalhando-com-branchs)
* [trabalhando-com-repositório-remoto](https://github.com/YuriSiman/git-command-line#trabalhando-com-repositório-remoto)
* [tipos-de-fluxos-de-trabalho](https://github.com/YuriSiman/git-command-line#tipos-de-fluxos-de-trabalho)

---

### :dart: Objetivo

Meu objetivo é manter este arquivo como uma fonte de consulta ao trabalhar com versionamento de código com git, armazenando os comandos principais e mais utilizados.  

### Clone

Clone este repositório em sua máquina local usando:

```
git clone https://github.com/YuriSiman/git-command-line.git
```

---

## :rocket: Vamos Comaçar

## download-git

Instalar git:

[![Git - Downloads](https://img.shields.io/badge/git-%237159c1?style=for-the-badge&logo=git&color=orange)](https://git-scm.com/downloads)  

---

## configuracoes-iniciais

Exibir credenciais de email, usuário e outros...

```
git config --list
```

Configurando seu nome de usuário

```
git config --global user.name "Nome Usuário"
```

Configurando seu e-mail

```
git config --global user.email "seuemail@gmail.com"
```

Verificar a versão do git instalada

```
git --version
```

Buscando por mais informações e comandos git

```
git help
```

* [Voltar ao Início](https://github.com/YuriSiman/git-command-line)  

---

## trabalhando-com-repositório-local

Iniciando um repositório local

```
git init
```

Deletando um repositório local - deletando a pasta oculta .git (powershell)

```
rm .git -force
```

Adicionando as modificações realizadas na Staging Area (track)

```
git add .

ou

git add nome-do-arquivo.txt
```

Verificando o status da branch

```
git status
```

Removendo as modificações realizadas antes de ir para a Staging Area

```
git checkout .

ou

git checkout nome-do-arquivo.txt
```

Desfazer o comando git add, retirando as modificações da Staging Area

```
git reset

ou

git rm --cached nome-do-arquivo.txt
```

Gerar o commit das suas modificações

```
git commit -m "Nome do Commit"
```

Visualização de log - histórico de todos os commits que foram realizados dentro do repositório local

```
git log --oneline

ou

git log
```

Visualizar as modificações que foram adicionadas ou removidas

```
git diff
```

Sobrescrever o commit anterior do repositório local - "Editar" o commit anterior do repositório local

```
git commit -m "Nova Mensagem" --amend
```

Cancelar um ou mais commits na ordem conforme o número informado, devolvendo os arquivo modificados para a Staging Area

```
git reset HEAD~1 --soft
```

Cancelar um ou mais commits na ordem conforme o número informado, permanentemente, excluindo as implementações

```
git reset HEAD~1 --hard
```

Definindo uma versão para o seu repositório

```
git tag nome-da-versao
```

Voltando à versão desejada - Apaga tudo o que foi implementado e volta o repositório para a sua versão da tag criada

```
git checkout nome-da-versao
```

Voltando a qualquer commit conforme o seu número

```
git checkout nome-do-commit
```

Mostrar conteúdo de um commit

```
git show
```

* [Voltar ao Início](https://github.com/YuriSiman/git-command-line)  

---

## trabalhando-com-branchs

Criando uma nova branch e acessando ela, mudando da branch atual para a que foi criada

```
git checkout -b nome-da-branch
```

Criando uma nova branch sem acessar ela, permanendo na branch atual

```
git branch nome-da-branch
```

Navegando entre branchs

```
git checkout nome-da-branch
```

Ver todas as branchs

```
git branch
```

Deletando uma branch

```
git branch -d nome-da-branch
```

Fazer merge da master com alguma feature - É preciso ir para a master primeiro para efetuar o merge. Este comando faz com que todos os commits da sua feature passem a fazer parte do log da master

```
git merge nome-da-branch
```

Fazer merge da master com alguma feature - É preciso ir para a master primeiro para efetuar o merge. Este comando não gera um commit automaticamente, ele faz com que apenas o commit desse merge passe a fazer parte do log da master

```
git merge nome-da-branch --squash
```

Desfazer um merge

```
git reset HEAD~1 --hard
```

Abortar o merge em caso de conflitos

```
git merge --abort
```

Pegar tudo que não foi commitado numa feature e "esconder" para que se possa mudar de branch sem levar as alterações junto - isso quando ainda não foi gerado o commit

```
git stash
```

Visualizar todos os stash

```
git stash list
```

Pega as modificações "escondidas" pelo stash, é possível puxar pelo índice - continua com uma cópia no stash

```
git stash apply 1
```

Deletando um stash conforme a sua referência numérica

```
git stash drop 1
```

Deleta todos os stash

```
git stash clear
```

* [Voltar ao Início](https://github.com/YuriSiman/git-command-line)  

---

## trabalhando-com-repositório-remoto

Adicionando um repositório "origin" remoto em um repositório local

```
git remote add origin https://nome-do-repositorio.git
```

Visualizando os repositórios remotos adicionados ao seu repositório local 

```
git remote
```

Verificando se há diferenças entre o repositório remoto adicionado com o que está remoto no GitHub

```
git remote show origin
```

Enviando conteúdo do repositório local para o remoto - no exemplo, da branch master

```
git push -u origin master
```

Enviando conteúdo do repositório local para o remoto - todas as branches

```
git push -u origin --all
```

Enviando conteúdo do repositório local para o remoto - comando simplificado para os envios após o primeiro git push -u origin master

```
git push
```

Forçando o envio de um push - não funciona na master

```
git push --force

ou

git push -f
```

Removendo um repositório "origin" de um repositório local (desvinculando o repositório local com o remoto)

```
git remote remove origin
```

Mostra todo o histórico de commits realizados, excluídos ou não

```
git reflog
```

Voltando seu repositório a um commit qualquer, seja deletado ou não

```
git cherry-pick número-do-commit
```

Baixar o conteúdo do repositório remoto para o seu local já fazendo um commit e mesclando os conteúdos

```
git pull
```

Baixar o conteúdo do repositório remoto para o seu local, sem mesclar (É interessante para poder validar primeiro o conteúdo que foi baixado, dentro da origin/master, e depois fazer o merge)

```
git fetch
```

Clonar o repositório remoto para o seu local

```
git clone https://nome-do-repositorio.git
```

Clonar uma branch específica de um repositório remoto para o seu local

```
git clone --single-branch --branch nome-da-branch https://nome-do-repositorio.git
```

Clonar o repositório remoto para o seu local sem trazer os arquivos e implementações

```
git clone -n https://nome-do-repositorio.git
```

Após um ``` git clone -n https://nome-do-repositorio.git ``` você precisa especificar o que você quer que venha do repositório clonado para o seu local

```
git checkout HEAD nome-do-arquivo

ou

git checkout HEAD nome-do-diretório
```

Visualizando os commit do seu repositório remoto

```
git log origin/master
```

* [Voltar ao Início](https://github.com/YuriSiman/git-command-line)  

---

## :vertical_traffic_light: Status do Projeto

:construction: Comandos sendo implementados :construction:

---

## :thinking: Contribuindo

> Para começar...

### Passo 1

* :fork_and_knife: Fork este repositório!

### Passo 2

* :dancers: Clone este repositório para sua máquina local usando `git clone https://github.com/YuriSiman/git-command-line.git`

### Passo 3

* :trident: Crie sua feature branch usando `git checkout -b minha-feature`

### Passo 4

* :white_check_mark: Commit suas mudanças usando `git commit -m "feat: Minha nova feature"`

### Passo 5

* :pushpin: Dê um push usando `git push origin minha-feature`

### Passo 6

* :arrows_clockwise: Crie um novo pull request

Depois que seu pull request for mesclado, você pode excluir sua feature branch  

> Caso tenha dúvidas, confira este guia de como [contribuir no GitHub](https://github.com/firstcontributions/first-contributions)  

---

## :speech_balloon: Suporte

> Entre em contato comigo...  

* Me chame pelo [Linkedin](https://www.linkedin.com/in/yurisiman/)  
* Me mande um e-mail [contato@yurisiman.com.br](mailto:contato@yurisiman.com.br)  

[![Github](https://img.shields.io/badge/github-profile-%237159c1?style=for-the-badge&logo=github)](https://github.com/YuriSiman)  
[![Curriculum](https://img.shields.io/badge/site-curriculum-%23563D7C?style=for-the-badge&logo=bootstrap)](https://yurisiman.com.br)  

---

## :pencil: Licença

[![License](https://img.shields.io/badge/license-mit-%23A6CE39?style=for-the-badge&logo=github)](https://github.com/YuriSiman/git-command-line/blob/master/LICENSE)   

---

Code your life...

