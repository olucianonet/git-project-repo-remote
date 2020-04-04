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
