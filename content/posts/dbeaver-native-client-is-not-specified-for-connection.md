---
title: "DBeaver Native client is not specified for connection"
date: 2023-03-23T21:03:22-08:00
draft: false
---
## Introdução

Quando você precisa fazer um dump atual da base de dados de produção ou quando você precisa fazer uma migração de dados de um banco de dados para outro, você pode precisar de um cliente nativo para fazer isso. O DBeaver é um ótimo cliente de banco de dados que permite que você faça isso facilmente, mas você pode encontrar um erro como este:
**DBeaver Native client is not specified for connection**. Vamos ver como resolver isso.

### Verificando se o cliente nativo está instalado

Você pode verificar se o cliente nativo do banco de dados que você deseja está instalado executando o seguinte comando no terminal, caso você não esteja usando o mysql como banco de dados, substitua o mysql pelo nome do banco de dados que você está usando.

```bash
$ mysql --version
```
Se você receber uma mensagem de erro como esta:
```bash
$ mysql: command not found
```
Isso significa que o cliente nativo não está instalado. Você pode instalá-lo executando o seguinte comando:

```bash
$ sudo apt-get install default-mysql-client
```

### Configurando o cliente nativo no DBeaver

Depois de instalado o cliente você precisa saber o caminho do executável do cliente nativo. Você pode encontrar o caminho executando o seguinte comando no terminal:

```bash
$ which mysql
```

O resultado deve ser algo como:

```bash
$ /usr/bin/mysql
```
Agora você precisa configurar o caminho do executável no DBeaver. Para fazer isso, vá para o seu banco de dados desejado e clique com o botão direito do mouse e selecione **Ferramentas**. Em seguida, vá para a guia **Dump Database** e clique no botão **Local Client**. Em seguida, você deve colocar o caminho do executável do cliente nativo no campo **Client Home**.

### Conclusão

O Dbeaver é uma otima ferramenta para gerenciar seus bancos de dados, mas você pode encontrar alguns erros ao usá-lo. Espero que este artigo tenha ajudado você a resolver o problema. Obrigado por ler e nos vemos no próximo post!
