---
title: "Normalizacão De Banco De Dados"
date: 2023-04-18T21:33:20-03:00
draft: false
---

## Introdução
Um dia, enfrentei um problema com um banco de dados que me levou a aprender sobre normalização. Queria compartilhar com vocês o que aprendi sobre a normalização de banco de dados. Em resumo, é um processo que visa reduzir a redundância de dados em um banco de dados relacional, mantendo a consistência e integridade dos dados. Existem várias formas normais (NF) que um banco de dados pode atender, sendo as mais comuns 1NF, 2NF, 3NF, 4NF e 5NF.

## Motivação

A normalização é importante durante o projeto e a modelagem de um banco de dados relacional. Ela ajuda a garantir a integridade dos dados e evitar a redundância de informações, o que pode levar a inconsistências e anomalias nos dados. É especialmente importante em bancos de dados maiores e com relacionamentos complexos, pois pode melhorar a eficiência e a performance do banco de dados, uma vez que a redundância de dados é reduzida e as informações são armazenadas de forma organizada. No entanto, é importante encontrar um equilíbrio entre a normalização e a simplicidade do modelo de banco de dados para garantir a eficiência, a integridade e a facilidade de uso do sistema.

Existem várias formas normais que um banco de dados pode atender, sendo as mais comuns a 1NF, 2NF, 3NF, 4NF e 5NF. Cada uma delas apresenta critérios específicos que devem ser atendidos para que a tabela esteja em conformidade com a forma normal correspondente. Por exemplo, na 1NF, todos os atributos de uma tabela devem conter valores atômicos, ou seja, indivisíveis. Na 2NF, todos os atributos não-chave devem ser totalmente dependentes da chave primária, e assim por diante.

## Forma Normal (1NF)

Nesta forma normal, todos os atributos de uma tabela devem conter valores atômicos, ou seja, indivisíveis. Cada coluna de uma tabela deve conter apenas um valor para cada registro. Caso uma tabela tenha valores multivalorados, ela não está em 1NF.

Imagine que você tem uma tabela com informações de alunos de uma escola. Uma das colunas dessa tabela é "Disciplinas", e nessa coluna são listadas todas as disciplinas em que o aluno está matriculado. Mas um mesmo aluno pode estar matriculado em mais de uma disciplina, então essa coluna tem valores multivalorados, ou seja, não contém apenas um valor para cada registro. A primeira forma normal (1NF) é uma regra que exige que cada coluna de uma tabela tenha apenas um valor para cada registro.

Ou seja, cada célula da tabela deve conter apenas um único valor indivisível. Então, para deixar a tabela em 1NF, a coluna "Disciplinas" deveria ser dividida em várias colunas, cada uma representando uma disciplina. Dessa forma, cada célula teria apenas um valor para cada registro.

## 2ª Forma Normal (2NF)

Para atender a esta forma normal, uma tabela precisa estar na 1NF e todos os seus atributos não-chave devem ser totalmente dependentes da chave primária. Se houver atributos que dependam apenas de parte da chave primária, então é necessário criar uma nova tabela para estes atributos.

Por exemplo, suponha que você tenha uma tabela chamada "Pedidos" com as colunas "Número do Pedido", "Código do Produto", "Descrição do Produto" e "Quantidade". O número do pedido e o código do produto juntos formam a chave primária composta. Se houver várias entradas para o mesmo número do pedido e cada uma delas tiver uma descrição diferente do produto, a descrição do produto dependerá apenas da parte "Código do Produto" da chave primária e não da chave completa. Nesse caso, você precisa dividir a tabela em duas, uma para os pedidos e outra para os detalhes do produto, onde o código do produto seria a chave primária da segunda tabela.

Isso ajuda a evitar a redundância de dados e garante que cada tabela possua apenas as informações necessárias para representar adequadamente os dados daquele tipo de entidade, facilitando o gerenciamento do banco de dados.

## 3ª Forma Normal (3NF)

Para atender a esta forma normal, uma tabela precisa estar na 2NF e todos os seus atributos não-chave devem ser independentes entre si. Ou seja, não deve haver dependência transitiva entre os atributos não-chave. Imagine que você tem uma tabela com informações sobre alunos de uma escola. Nessa tabela, as colunas são o nome do aluno, o nome do professor, a matéria, o número da sala e o telefone do aluno.

A primeira coisa que precisamos fazer é verificar se a tabela está na primeira forma normal (1NF), que significa que não deve haver valores repetidos na tabela. Neste caso, cada linha representa um aluno, então não há valores repetidos, então já estamos na 1NF.

Agora, precisamos verificar se a tabela está na segunda forma normal (2NF), que significa que não pode haver dependências parciais. Uma dependência parcial ocorre quando uma coluna depende apenas de uma parte da chave primária. A chave primária é a coluna que identifica unicamente cada linha na tabela.

No exemplo da tabela de alunos, a chave primária pode ser o número da sala e o nome do aluno, já que uma sala pode ter vários alunos e um aluno pode ter várias aulas em diferentes salas. Neste caso, a coluna "nome do professor" depende apenas do número da sala, e não da combinação do número da sala e do nome do aluno, o que significa que a tabela não está na 2NF. Para resolver isso, podemos dividir a tabela em duas: uma tabela para informações de alunos (com nome, número da sala e telefone) e outra tabela para informações de aula (com número da sala, nome do professor e matéria).

Agora, chegamos à terceira forma normal (3NF), que significa que não deve haver dependências transitivas entre os atributos não-chave. Isso ocorre quando uma coluna depende de outra coluna que não é a chave primária. Por exemplo, se tivéssemos uma coluna "cidade" na tabela de informações de aluno, e essa coluna dependesse da coluna "telefone", que por sua vez depende do nome do aluno, teríamos uma dependência transitiva e a tabela não estaria na 3NF. Para resolver isso, precisaríamos criar uma nova tabela para informações de cidades, com o nome da cidade e seu código postal, e ligá-la à tabela de informações de alunos através de um relacionamento.

Então, resumindo, para atender à terceira forma normal (3NF), precisamos garantir que a tabela esteja na segunda forma normal (2NF) e que não haja dependências transitivas entre os atributos não-chave.

## 4ª Forma Normal (4NF)

Esta forma normal é menos conhecida e mais avançada do que as anteriores. Para atender a 4NF, uma tabela precisa estar na 3NF e não pode ter múltiplas relações de dependência multi-valoradas. Em outras palavras, se houver atributos que dependam de múltiplas combinações de valores de outras colunas, eles devem ser movidos para uma nova tabela.

Imagine que você tem uma tabela de alunos na sua escola, onde cada linha representa um aluno e cada coluna representa uma informação sobre o aluno, como nome, idade, turma e matérias que ele está cursando. Se essa tabela estiver na 3ª Forma Normal, isso significa que cada coluna deve depender somente da chave primária da tabela, que no caso pode ser o número de matrícula do aluno. Por exemplo, se um aluno muda de turma, a única informação que precisa ser atualizada na tabela é a coluna da turma dele.

Mas, se na tabela de alunos houver uma coluna que indica as atividades extracurriculares que cada aluno participa, e um aluno pode participar de várias atividades, como esportes, artes e música, aí surge um problema. Essa coluna está criando uma dependência multivalorada, ou seja, uma atividade pode ter vários alunos e um aluno pode ter várias atividades. Isso quebra a 3ª Forma Normal.

Para resolver esse problema, é preciso aplicar a 4ª Forma Normal. Nesse caso, a tabela de alunos precisaria ser dividida em duas: uma tabela para armazenar informações dos alunos, como nome e turma, e outra tabela para armazenar as informações sobre as atividades extracurriculares, com uma coluna para o nome da atividade e uma coluna para a matrícula do aluno que participa daquela atividade. Dessa forma, cada tabela tem uma única relação de dependência e a tabela está na 4ª Forma Normal.

## 5ª Forma Normal (5NF)

Esta forma normal é a mais avançada e menos comum do que as anteriores. Para atender a 5NF, uma tabela precisa estar na 4NF e não pode ter dependências de junção. Isso significa que não deve haver duas ou mais tabelas que possam ser combinadas para recuperar um atributo.

O que isso significa é que, em uma tabela na 5NF, as informações devem ser organizadas de tal forma que não haja dependências entre tabelas. Ou seja, não deve haver duas ou mais tabelas que precisem ser combinadas para encontrar um pedaço de informação.

Isso é importante porque ajuda a garantir que as informações estejam organizadas de uma maneira que seja fácil de usar e gerenciar. Além disso, também ajuda a garantir que as informações estejam corretas e atualizadas.

A normalização de banco de dados pode trazer algumas vantagens, como a redução da redundância de dados, melhoria da performance do banco de dados, facilidade de manutenção e modificação, além de evitar inconsistências e anomalias nos dados. No entanto, também pode trazer desafios e trade-offs, como a complexidade da modelagem e o aumento do número de tabelas e relacionamentos.

## Conclusão

Em resumo, a normalização de banco de dados é um tópico importante para projetistas e desenvolvedores de banco de dados. É um processo que visa garantir a integridade dos dados e evitar redundância de informações, melhorando a eficiência e a performance do banco de dados. É importante encontrar um equilíbrio entre a normalização e a simplicidade do modelo de banco de dados para garantir a eficiência, a integridade e a facilidade de uso do sistema.

**Referências:**
- [Vídeo de referência](https://www.youtube.com/watch?v=GFQaEYEc8_8)
- [Playlist completa de referência](https://www.youtube.com/playlist?list=PLNITTkCQVxeXryTQvY0JBWTyN9ynxxPH8)
