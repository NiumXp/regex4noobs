# 3.3 - Sequências
Sequências de metacaracteres são classes de caracteres pré-definidas.


## Whitespaces
O metacaractere `\s` é uma sequência pré-definida para espaços em branco, pode ser representado por `[\r\n\t\f\v ]`.

> `\r` (Carriage Return), `\n` (New line/Line feed), `\t` (Horizontal tabulation), `\f` (Formfeed) e `\v` (Vertical tabulation) e `\0` (Null character) também são metacaracteres.


## Digitos e Letras
A sequência `\d` representa qualquer digito de 0 à 9, pode ser entendida como `[0-9]`.

A sequência `\w` é uma extensão de `\d` com as letras do alfabeto (sem acentuações) e o *underline* (`_`), pode ser entendido como `[a-zA-Z0-9_]`.


## Negando *Meta sequences*
As vezes precisamos de tudo menos do que estiver em uma sequência... 

Por exemplo, podemos utilizar `\S` para capturar qualquer coisa que não esseja em `\s`. Essa mesma ideia também se aplica ao digitos, usando o `\D` pegaremos tudo que não esteja na sequência `\d`.

Ou seja, podemos apenas passar a letra da *meta sequence* para maisculo!

> E aí, você se lembra de como negar uma classe de caracteres?

### Outras negações
Algumas *engines* também suportam negações para o `\n`, `\h`, etc... transformando a letra em maisculo também (`\N`).

---

Ir para [`Módulo básico:Âncoras`](../anchors.md).
