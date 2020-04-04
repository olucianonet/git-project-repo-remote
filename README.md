# Git e Github

## Índice

1. O que é Git?
2. Iniciando os trabalhos
3. Compartilhando o trabalho
4. Trabalhando em equipe
5. Manipulando as versões
6. Gerando entregas
7. Referências

## 1. O que é Git?

É um sistema de controle de versões.

### 1.1. Instalação

Para instalar em um sistema Linux, baseado no Debian, execute:

```
$ sudo apt install git-all
```

### 1.2. Criar repositórios

Para criar um repositório, execute:

```
$ git init
```

dentro do diretório desejado.

### 1.3. Verificando o status 

Nesse momento, já é possível executar o comando:

```
$ git status
```

Esse comando, exibe o estado atual do seu repositório.

## 2. Iniciando os trabalhos

### 2.1. Monitorando arquivos

Para começar a monitor uma arquivo, execute:

```
$ git add <nome-do-arquivo> # arquivo específico
$ git add . # todos os arquivos de um diretório
```

### 2.2. Salvando alterações

Após incluir um arquivo no monitoramento, salve suas alterações:

```
$ git commit -m 'Mensagem de commit'
```

## 3. Compartilhando o trabalho

### 3.1. Repositórios remotos

Para criar um servidor remoto, execute:

```
$ git init --bare
```

Após esse procedimento, volte ao seu projeto e adicione o repositório remoto 
como repositório destino, com o comando:

```
git remote add <nome-repo> <caminho>
```

Para visualizar os repositórios remotos de um projeto, execute:

```
$ git remote -v
```

### 3.2. Sincronizando dados

Com o repositório remoto configurado, já é possível enviar suas alterações para
lá. Para isso, após o `commit`, execute:

```
$ git pull local master
```

### 3.3. Compartilhando as alterações

Com o envio das alterações para o reposítório central, outros usuários poderão
fazer uma cópia do projeto. Para isso, execute:

```
$ git clone <local-do-repositorio-central> <nome-do-projeto>
```

Com esse comando será criado um diretório com o projeto.

## 5. Desfazendo coisas

### 5.1. Antes do `stage`

Quando efetuamos alguma alteração em um arquivo, ao executar o `status`,
recebemos a seguinte mensagem:

```
  (use "git checkout -- <file>..." to discard changes in working directory)

	modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")
```

Nesse estado, é possível desfazer a alteração apensar executando:

```
$ git checkout -- README.md
```

### 5.2. NO `stage`

Quando adicionamos uma alteração no `stage` e precisamos desfazer, executamos:

```
$ git reset HEAD README.md
$ git checkout -- README.md
```

### 5.3. No commit

Para desfazer uma alteração após o `commit`, execute:

```
$ git lg
```

Para recuperar o `hash` do último `commit` realizado. E após isso execute:

```
$ git rever 689cb5c
```

Será adicionado um novo `commit` com o `revert` executado e as alterações 
serão desfeitas.

### 5.4. Salvando alterações temporariamente

Para guardar temporariamente alterações que ainda não foram enviadas para o 
`stage`, execute:

```
$ git stash
```

Para visualizar as alterações do `stash`, execute:

```
$ git stash list
stash@{0}: WIP on capitulo-05: 2842336 Revert "Adicionado capitulo 05, v. 3"
```

### 5.5. Recuperando conteúdo do stash

Para recuperar um conteúdo do stash, execute:

```
$ git stash <numero do stash>
```

Fazendo isso, o stash será aplicado, mas também continuará na lista de `stash` disponível.

Para aplicar e excluir da lista de `stash`, execute:

```
$ git stash pop
```

Esse comando removerá o primeiro item do `stash` e aplicará no branch atual.

