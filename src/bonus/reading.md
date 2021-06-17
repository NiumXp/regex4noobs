# 2 - Decifrando expressões regulares

Algumas expressões regulares são bem complicadas de se ler as vezes.

Por exemplo, olhe esta expressão `-?[0-9]+\.?[0-9]+` e tente ver qual das opções abaixo não é válida à ela:

- A expressão pega qualquer número inteiro que tenha ou não decimais;
- A expressão pega apenas números inteiros com ou não, decimais, que a parte inteira não seja nula ou assimetríca ou não à 1 até 9;
- A expressão não casa com `3`, mas casa com `3.0` e `-3.0` por causa dos quantificadores.

Antes de sabermos qual opção está errada, eu gostaria de perguntar uma coisa, como você leu a expressão? Do começo ao fim, do final até começo ou zig-zag?

Não tem jeito certo, mas acredito que a melhor forma seja o zig-zag.

Toda expressão regular tem valores absolutos, eles são os valores que existirão na saída, por exemplo, na expressão `ab?`, podemos dizer que sempre haverá `a` na saída, logo, é um valor absoluto. Não podemos dizer o mesmo no caso do `b`... podemos chama-lo de valor incerto.

Ou seja, se olharmos para nossa primeira expressão, vamos ver que existem dois valores absolutos..
```
-?[0-9]+\.?[0-9]+
  ^^^^^    ^^^^^
```
..o que tornou eles absolutos foi quantificador `+` ao lado deles.

### Por que devemos saber os valores absolutos?
Com os valores absolutos podemos imaginar a quantidade minima de caracteres que terá na saída e qual é o alvo das expressões regulares.

No caso da primeira expressão dessa sessão, a saída sempre terá de dois ou mais caracteres.

### E os valores incertos?
Vamos voltar na última expressão, podemos ver o `-?` no começo dela, isso significa que o `-` é um valor incerto. Por exemplo, o caso `25` é um caso que podemos prever por conta dos valores absolutos, agora o caso `-25` é um caso incerto já que o `-` apareceu.

Entenda os valores incertos como os valores absolutos só que de origem incerta.

## Ramos e mais ramos
Xii... essa é a pior parte de uma expressão regular. Eu tenho certeza de que você passa mal quando tem que desvendar uma expressão que utiliza *pipe*. Mas não se preocupe, você nunca mais precisará de um balde se apenas separar a expressão regular!

```
Expressão : H(i|ello)!

Ramo 1    : Hi!
Ramo 2    : Hello!
```

Muito mais fácil não é mesmo? É, pode até ser, mas irá dar um trabalinho a mais quando estivermos com expressões muito grandes...

A ideia não é fazer isso para todas as partes da expressão... apenas para as que você não entender! A expressão anterior é um exemplo de que conseguimos entender a expressão perfeitamente sem separa-la em ramos.

Aproveitando, vamos analisar esta expressão `(?:https?|ftp)`. É um caso perfeito para à separação de ramos, ela parece simples, mas pode trazer diversas dores de cabeça as vezes.

```
Expressão : (?:https?|ftp)

Ramo 1    : (?:http)
Ramo 2    : (?:https)
Ramo 3    : (?:ftp)
```

Uma variante mais explicita da expressão anterior é `(?:http|https|ftp)` - com essa fica muito melhor de explicar para outras pessoas não é? *"Aqui pode ser `http`, ou `https`, ou `ftp`!"*


# Resumindo
Uma expressão regular é como uma árvore, os valores absolutos da expressão são como o tronco. Sabemos que existem galhos no topo de uma árvore e as vezes não conseguimos exergar se ela for muito grande, esses galhos são os valores quase incertos de uma expressão regular, sabemos que existem, mas não ligamos muito para eles.

---

Ir para [`Módulo Bônus:Expressões regulares à prova d'água`](water.md).
