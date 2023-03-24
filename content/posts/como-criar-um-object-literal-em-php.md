---
title: "Como criar um object literal em PHP"
date: 2022-11-10T21:03:22-08:00
draft: false
---

## Introdução

Infelizmente no PHP não existe object literal, mas é possível "falsificar" colocar arrays em objetos, no código abaixo observe que os objetos são sempre passados ​​por "referência" eles são passados ​​por um valor numérico chamado identificador de objeto. Portanto alterar um atributo de um objeto o altera em todos os lugares em que o objeto foi atribuído.


```php
$funtionResult = array(
    (object)array("name" => "John", "age" => function () {
        return 30;
    }),
    (object)array("name" => "Jane", "hobby" => function() {
        return "painting";
    })
);
```

## Observação

Neste exemplo foi possível escrever uma function como o valor do elemento hobby que foi atribuído a variável $funtionResult e ao executar a variável agora com a atribuição utilizando $funtionResult(); ele executa a function com o retorno de uma string "painting"

```php
    $funtionResult = $testArray[1]->hobby;
    var_dump($funtionResult());
```

## Opinião

Veja que o que estamos fazendo aqui é fazer o com a utilização do PHP consigamos uma similaridade com a sintaxe de javascript, com PHP também é possível criar arrays associativos facilmente assim como no javascript, como vimos no código acima é possível criar algo semelhante, mas dependendo do contexto da situação em utilizar object literal é melhor utilizar de outras alternativas.

>Se quiser testar o código: https://3v4l.org/kSZvs

**Referências:**

 - https://stackoverflow.com/questions/9644870/php-object-literal/9644977#9644977
 - https://www.php.net/manual/en/language.types.array.php
 - https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Operators/Object_initializer
 - https://betterprogramming.pub/object-literal-in-javascript-d3e0e7d58f3b
 - https://www.saurabhmisra.dev/create-object-literal-php
