---
title: "Normalizacão De Banco De Dados"
date: 2023-04-18T21:33:20-03:00
draft: false
---

## Introdução
Como sempre na hora do sofrimento eu vou buscar conhecer como resolver alguns problemas encontrados e dessa vez o problema foi relacionado com banco de dados e então vamos falar sobre a normalização de banco de dados.
É um processo que visa a redução da redundância de dados em um banco de dados relacional, mantendo a consistência e integridade dos dados. Existem várias formas normais (NF) que um banco de dados pode atender, sendo as mais comuns 1NF, 2NF, 3NF, 4NF e 5NF.

A normalização de banco de dados é um processo importante que deve ser aplicado durante o projeto e a modelagem de um banco de dados relacional. É importante realizar a normalização de um banco de dados para garantir a integridade dos dados e evitar a redundância de informações, o que pode levar a inconsistências e anomalias nos dados.
A normalização é especialmente importante em bancos de dados maiores, com muitas tabelas e relacionamentos complexos. Nestes casos, a normalização pode ajudar a melhorar a eficiência e a performance do banco de dados, uma vez que a redundância de dados é reduzida e as informações são armazenadas de forma mais organizada.
No entanto, a normalização também pode trazer alguns desafios e trade-offs, como a complexidade da modelagem e o aumento do número de tabelas e relacionamentos, o que pode tornar as consultas mais complexas. Portanto, é importante encontrar um equilíbrio entre a normalização e a simplicidade do modelo de banco de dados, de modo a garantir a eficiência, a integridade e a facilidade de uso do sistema.

## Motivação

Por experiência de vida eu conheci alguns bancos de dados com muitos problemas e então foi necessário eu entender e compreender como eu deveria agir nessas situações, e foi aí que eu conheci alguns conceitos como a normalização de banco de dados que traz algumas vantagens como redução da redundância de dados ao eliminar a redundância de informações em uma tabela, a normalização ajuda a economizar espaço de armazenamento e a manter a consistência dos dados. Isso também ajuda a evitar inconsistências nos dados, já que não há duplicação de informações, melhora da performance do banco de dados, com uma estrutura de dados normalizada, as consultas podem ser mais eficientes e rápidas, pois há menos dados a serem acessados e processados. Isso é especialmente importante em bancos de dados grandes e complexos.
Facilita a manutenção do banco de dados: Um banco de dados normalizado é mais fácil de manter e modificar, pois a estrutura é organizada e consistente. Isso também facilita a adição ou remoção de dados, ou a criação de novas tabelas e relacionamentos.

Como eu havia dito no início desse texto existem várias formas normais que um banco de dados pode atender, sendo as mais comuns 1NF, 2NF, 3NF, 4NF e 5NF.

Forma Normal (1NF): Nesta forma normal, todos os atributos de uma tabela devem conter valores atômicos, ou seja, indivisíveis. Cada coluna de uma tabela deve conter apenas um valor para cada registro. Caso uma tabela tenha valores multivalorados, ela não está em 1NF.
2ª Forma Normal (2NF): Para atender a esta forma normal, uma tabela precisa estar na 1NF e todos os seus atributos não-chave devem ser totalmente dependentes da chave primária. Se houver atributos que dependam apenas de parte da chave primária, então é necessário criar uma nova tabela para estes atributos.
3ª Forma Normal (3NF): Para atender a esta forma normal, uma tabela precisa estar na 2NF e todos os seus atributos não-chave devem ser independentes entre si. Ou seja, não deve haver dependência transitiva entre os atributos não-chave.
4ª Forma Normal (4NF): Esta forma normal é menos conhecida e mais avançada do que as anteriores. Para atender a 4NF, uma tabela precisa estar na 3NF e não pode ter múltiplas relações de dependência multi-valoradas. Em outras palavras, se houver atributos que dependam de múltiplas combinações de valores de outras colunas, eles devem ser movidos para uma nova tabela.
5ª Forma Normal (5NF): Esta forma normal é a mais avançada e menos comum do que as anteriores. Para atender a 5NF, uma tabela precisa estar na 4NF e não pode ter dependências de junção. Isso significa que não deve haver duas ou mais tabelas que possam ser combinadas para recuperar um atributo.

## Conclusão

A normalização de banco de dados é um tópico importante para projetar bancos de dados bem estruturados e eficientes, evitando a redundância de dados e garantindo a integridade dos dados. Mas acredito que o maior problema é a complexidade de realizar a simplificação de um banco de dados, sem causar mudanças drásticas, normalmente uma simples mudança no banco de dados gera impacto em diversos serviços e isso gera trabalho, custos e tempo.

**Referências:**
- [Vídeo de referência](https://www.youtube.com/watch?v=GFQaEYEc8_8)
- [Playlist completa de referência](https://www.youtube.com/playlist?list=PLNITTkCQVxeXryTQvY0JBWTyN9ynxxPH8)
