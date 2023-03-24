---
title: 'Como instalar o PHP-8 no debian 9/10/11'
date: 2022-09-06T21:03:22-08:00
draft: false
---

## Introdução

Neste pequeno guia, mostrarei como instalar o PHP 8.0 no Debian 11, 10, 9. PHP é uma poderosa linguagem de script para desenvolvimento web.
Qualquer script PHP pode ser executado em sistemas Linux, Windows, MacOS e Unix com o tempo de execução do PHP instalado.
A versão oficial do PHP 8 é 26 de novembro de 2020. Esta versão básica do PHP tem muitos novos recursos e melhorias de desempenho.

Você também deve esperar novas mudanças, o que significa que algumas modificações em seu código podem precisar ser implementadas no PHP 8. Alguns dos melhores conjuntos de novos recursos que vêm com o PHP 8 são desenvolvedores JIT, discussões nomeadas, fusões, recursos e muitos mais.

## Primeiro passo atualizar o repositório
Atualize seu sistema para a versão mais recente antes de instalar o PHP 8 no seu Debian.

```bash
sudo apt update
sudo apt -y upgrade
```

## Passo 2 Adicionar o repositório

Os pacotes PHP 8 para Debian estão disponíveis no repositório [DEB SURY ORG](https://deb.sury.org/) Estabeleça as dependências necessárias.
```bash
sudo apt install -y lsb-release ca-certificates apt-transport-https software-properties-common gnupg2
```

Adicione o repositório PHP APT a sua sourcelist Debian.

```bash
echo "deb https://packages.sury.org/php/ $(lsb_release -sc) main" | sudo tee /etc/apt/sources.list.d/sury-php.list
```

Importe a chave do repositorio

```bash
wget -qO - https://packages.sury.org/php/apt.gpg | sudo apt-key add -
```

Atualize os repositorios

```bash
sudo apt update
sudo apt -y upgrade
```

## Passo 3 Instalar o PHP 8

Agora sim  com os repositorios adicionados e atualizados, instale o PHP 8.

```bash
sudo apt install php8.0
```

Depois para confirmar se deu boa

```bash
php -v
```

## Extensões PHP 8

Tenho certeza que você vai precisar de algumas extensões PHP 8 algumas para conectar com bancos ou qualquer outra coisa.
Vou deixar uma listinha que normalmente é muito útil quando preciso trabalhar com PHP.

```bash
sudo apt install php8.0-bcmath php8.0-curl-dbgsym php8.0-gmp-dbgsym php8.0-mysql php8.0-pspell-dbgsym php8.0-tidy php8.0-bcmath-dbgsym php8.0-dba php8.0-imap php8.0-mysql-dbgsym php8.0-readline php8.0-tidy-dbgsym php8.0-bz2 php8.0-dba-dbgsym php8.0-imap-dbgsym php8.0-odbc php8.0-readline-dbgsym php8.0-xdebug php8.0-bz2-dbgsym php8.0-dev php8.0-interbase php8.0-odbc-dbgsym php8.0-snmp php8.0-xml php8.0-cgi php8.0-enchant php8.0-interbase-dbgsym php8.0-opcache php8.0-snmp-dbgsym php8.0-xml-dbgsym php8.0-cgi-dbgsym php8.0-enchant-dbgsym php8.0-intl php8.0-opcache-dbgsym php8.0-soap php8.0-xsl php8.0-cli php8.0-fpm php8.0-intl-dbgsym php8.0-pgsql php8.0-soap-dbgsym php8.0-zip php8.0-cli-dbgsym php8.0-fpm-dbgsym php8.0-ldap php8.0-pgsql-dbgsym php8.0-sqlite3 php8.0-zip-dbgsym php8.0-common php8.0-gd php8.0-ldap-dbgsym php8.0-phpdbg php8.0-sqlite3-dbgsym php8.0-common-dbgsym php8.0-gd-dbgsym php8.0-mbstring php8.0-phpdbg-dbgsym php8.0-sybase php8.0-curl php8.0-gmp php8.0-mbstring-dbgsym php8.0-pspell php8.0-sybase-dbgsym
```

## De brinde, Vamos instalar o composer já né

O [PHP Composer](https://getcomposer.org/) é basicamente uma ferramenta de gerenciamento de dependências para aplicativos PHP. Isso facilita a instalação de módulos PHP. O composer vem com todos os módulos necessários para o programa e os instala em um comando. Ele também permite que o dev atualize módulos constantemente.
Com o Composer, você pode instalar facilmente todos os pacotes de que precisa.
O desenvolvedor mantém uma lista de pacotes necessários em um arquivo JSON chamado **composer.json**.

Um documento PHP é enviado pelo painel de controle para configurar o autor em seu sistema. Você pode removê-lo com um utilitário de substituição de linha de comando ou wget. Além disso, você pode baixá-lo com script PHP.
Os comando que eu vou deixar aqui estão também no site oficial do composer. Esse comando vai baixar o composer-setup.php.

```bash
php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
```

Para instalar o composer, execute o arquivo.

```bash
php composer-setup.php --install-dir=/usr/local/bin --filename=composer
chmod +x /usr/local/bin/composer
```

Agora para verificar se tudo está funcionando, execute o comando.

```bash
composer --version
```

## Ultimo detalhe atualizar o composer

O PHP Composer tem a capacidade de atualizar automaticamente para as versões mais recentes. Se o Composer já estiver instalado em seu sistema, digite o seguinte comando para atualizar o PHP Composer para a versão mais recente.

```bash
composer self-update
```

Fechou agora é só criar seus bugs, ops... códigos 🙃 hehe
