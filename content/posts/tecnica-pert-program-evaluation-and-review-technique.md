---
title: "Técnica PERT (Program Evaluation and Review Technique)"
date: 2023-03-27T23:53:20-08:00
draft: false
---

## Introdução

A técnica PERT **(Program Evaluation and Review Technique)** foi desenvolvida durante a década de 1950 pelo Departamento de Defesa dos Estados Unidos, em parceria com a empresa de consultoria Booz Allen Hamilton e a empresa de tecnologia Lockheed Martin.

Na época, o Departamento de Defesa dos Estados Unidos enfrentava grandes desafios na gestão de projetos complexos, especialmente na construção de equipamentos militares sofisticados, como submarinos nucleares e mísseis balísticos. Nesse contexto, surgiu a necessidade de uma técnica que ajudasse a gerenciar melhor o tempo e os recursos envolvidos em projetos complexos.

Foi então que, em 1957, a Booz Allen Hamilton e a Lockheed Martin desenvolveram a técnica PERT para ajudar a gerenciar o Projeto Polaris, um programa de desenvolvimento de submarinos nucleares dos Estados Unidos. A técnica ajudou a equipe do projeto a prever com mais precisão o tempo e os recursos necessários para concluir o projeto, o que ajudou a manter o projeto dentro do prazo e do orçamento.

## Motivação

A técnica PERT baseia-se na ideia de que o tempo necessário para concluir uma tarefa pode variar dependendo de muitos fatores, como disponibilidade de recursos, habilidade da equipe, mudanças nas condições do mercado, entre outros. A técnica usa a distribuição probabilística para estimar o tempo necessário para concluir uma tarefa ou projeto.

Ao usar três valores para cada tarefa **(Estimativa Otimista, Estimativa Nominal e Estimativa Pessimista)**, permite que as equipes de projeto tenham uma visão mais completa e realista do tempo necessário para concluir uma tarefa.

Além disso, a técnica também permite que as equipes de projeto identifiquem as tarefas críticas que podem atrasar todo o projeto, para que possam ser gerenciadas com mais eficiência.

Atualmente, a técnica é amplamente usada em gerenciamento de projetos, especialmente em projetos complexos e de longo prazo, como a construção de grandes instalações, desenvolvimento de software e programas governamentais.

## Como funciona a técnica PERT

Em vez de fornecer uma única estimativa de tempo, será utilizado três valores:

* O (Estimativa Otimista): Este número é altamente otimista e representa o tempo que seria necessário para concluir a tarefa se tudo der certo.
* N (Estimativa Nominal): Esta é a estimativa com a maior chance de sucesso.
* P (Estimativa Pessimista): Este número é altamente pessimista e representa o tempo que seria necessário para concluir a tarefa se tudo der errado, exceto por eventos extremos.

Para calcular a estimativa de tempo, podemos usar a fórmula:

```bash
R = (O + 4N + P)/6
```

Estimativa de tempo = (Valor otimista + (4 x valor mais provável) + valor pessimista) / 6 podemos criar uma função em javascript para melhor entendermos como funciona a técnica PERT:

```javascript
function calcularPERT(o, n, p) {
  const r = (o + (4 * n) + p) / 6;
  return Math.round(r * 100) / 100;
}

const resultado = calcularPERT(1, 3, 6);
console.log(resultado);
```

Neste exemplo, a função calcularPERT recebe os valores otimista (o), mais provável (n) e pessimista (p) da tarefa, e retorna a estimativa probabilística da tarefa usando a fórmula R = (O + 4N + P) / 6. O resultado é arredondado para duas casas decimais usando o método Math.round.

Para usar a função, basta passar os valores otimista, mais provável e pessimista como parâmetros e armazenar o resultado em uma variável. No exemplo acima, o resultado é armazenado na variável resultado e exibido no console usando o console.log.

## Conclusão

O uso da técnica PERT pode melhorar a precisão das estimativas de tempo claro que nunca será algo exato, mas é fundamental para garantir que os prazos sejam cumpridos. Além disso, a PERT ajuda a identificar quais tarefas são mais críticas para o sucesso do projeto, permitindo que os gerentes de projetos priorizem as atividades de forma mais eficiente. Eu estou utilizando essa técnica para gerenciar o meu tempo e o tempo de entrega dos projetos em que eu atuo, pelo inicio me parece que vai ser muito útil.
