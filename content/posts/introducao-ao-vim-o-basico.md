---
title: "Introdução ao Vim: o básico"
date: 2023-02-28T21:03:22-08:00
draft: false
---

## Introdução

Um certo dia percebi que um amigo meu estava editando e criando arquivos pelo vim. Logo perguntei, Por que você está usando o vim? Ele enfatiza e me diz;
Cara depois que você pega o jeito você tem uma produtividade maior e além do mais faz você parecer sênior 😅.

Brincadeiras à parte eu fiquei curioso e fui pesquisar, não achei nenhuma pesquisa que afirmava que utilizar vim é mais produtivo porém, lendo em alguns blogs algo me chamou muito a atenção que a velocidade de digitação será a mesma independente da IDE que você está utilizando. A velocidade de digitação é irrelevante até um certo nível mas o que de fato faz toda diferença é a capacidade e desempenho de navegar pelo código ou arquivos é o mais importante.

Estou utilizando essa ferramenta faz alguns meses, o fato que muitos desenvolvedores comentam é a queda de desempenho no começo do aprendizado, claro que como qualquer coisa que você aprende no início a velocidade para o desempenho esperado é menor, mas as boas notícias são que pelo menos ao que muitos afirmam, a longo prazo o desempenho aumenta significamente.

## Observação

Particularmente eu notei que para algumas tarefas do dia eu preciso utilizar uma IDE que tenha as ferramentas necessárias para o sucesso da minha tarefa. Mas por outro lado, eu consigo usar o vim com tranquilidade em outras tarefas. Vejo que quando preciso trabalhar somente com o backend eu sinto uma facilidade maior pois eu posso utilizar apenas o terminal sem precisar abrir um navegador ou outra ferramenta.

## Opinião

No meu ponto de vista, fica que eu não sou obrigado a usar somente uma ferramenta para desenvolver e sim usar a ferramenta que melhor se adeque ao que você precisa fazer no momento e que no meio social dos desenvolvedores experientes a maioria indica que pelo menos você precisa aprender o básico do vim.
Vou deixar aqui alguns comandos básicos para você experimentar e se divertir. Antes, deixa eu te mostrar os modos básicos que o vim tem.

* Modo normal onde você pode navegar pelo arquivo

* Modo Inserção para inserir e modificar o texto explicitamente

* Modo linha de comando para operações como salvar, editar, sair etc…

## Comandos básicos

Para criar um arquivo ou abrir um arquivo:

vim CreatePerson.js

- **ESC** entra para o modo normal
- **:q** saí do arquivo sem salvar
- **:wq** saí do arquivo e salva o arquivo
- **i** entra em modo de inserção no arquivo
- **:30** dois pontos mais o numero o numero se refere a linha que você pretende ir diretamente
- **:$** vai diretamente para o final do arquivo
- **dd** se você apertar a tecla d duas vezes rapidamente a linha em que o cursor estiver sera deletada
- **u** funciona como o CTRL Z
- **v** entra em modo de selecionar o texto ou caractere desejado
- **y** depois de pressionar v e deixar o texto selecionado pressione y que irá copiar o texto para a área de transferência, esse é o modo yank
- **p** cola o texto que estiver na area de transferencia
- **/** quando estiver no modo normal pressione / e em seguida uma palavra que existe dentro do arquivo e você será levado até a palavra
- **:split** cria uma divisão horizontal
- **:vsplit** cria uma divisão vertical

pressione CTRL e **w** duas vezes seguidas para navegar pelos splits criados


## Importante

É sempre muito importante quando você quer aprender alguma tecnologia ou ferramenta nova buscar informações sobre ela, na sua documentação,
vou deixar dois sites que me ajudaram a aprender mais sobre essa ferramenta.

- https://www.vim.org/docs.php
- https://vim.rtorr.com/lang/pt_br

**Referências:**

- https://shivansivakumaran.com/coding/how-i-got-started-with-vim-and-become-more-productive-while-coding/
- https://stackoverflow.com/questions/1346820/what-are-the-efficiencies-afforded-by-emacs-or-vim-vs-eclipse
- https://stackoverflow.com/questions/1088387/what-specific-productivity-gains-do-vim-emacs-provide-over-gui-text-editors
- https://dev.to/meenachinmay/will-vim-give-me-more-productivity-2ing
