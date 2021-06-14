# 2 - Decifrando expressões regulares

Toda expressão regular é bem complicada de se ler as vezes.

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
..o que tornou eles absolutos foi quantificador ao lado deles.

### Por que devemos saber os valores absolutos?
Com os valores absolutos podemos imaginar a quantidade minima de caracteres que terá na saída e qual é o alvo da expressão regular.
No caso da primeira expressão dessa sessão, a saída sempre terá de dois ou mais caracteres.

---

Ir para [`Módulo Bônus:Expressões regulares à prova d'água`](water.md).
