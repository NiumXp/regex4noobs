# 3.2 Quantifiers
Os quantificadores fazem com que o seu precedente se repita em alguma quantidade.

Os simbolos `?`, `*`, `+` e `{n,m}` são usados para representar os quantificadores.

Os quantificadores que eu citei acima são chamados de **quantificadores gulosos** (Greedy quantifiers), os **não gulosos** (Lazy quantifiers) utilizam os mesmos simbolos mas sufixados com um `?`.

### O quantificador base
Antes de entendermos os outros quantificadores e as "classes" deles, vamos ver o quantificador `{n,m}`.

Com esse quantificador podemos estabelecer uma quantidade mínima e máxima para a repetição do precedente, ou seja, `n` é a quantidade mínima que **deve** ser igual ou maior do que zero (`n >= 0`) e `m` é a quantidade máxima que **deve** ser igual ou maior do que `n` (`m >= n`).

Se deixarmos de colocar o `m`, mas deixarmos a vírgula (`{n,}`), a quantidade máxima será infinita. Se tirarmos o `m` e a vírgula (`{n}`), a quantidade será exatamente `n`.

> Se `n` e `m` forem iguais, a sintaxe `{n,m}` acaba sendo redundante e pode ser trocada apenas por `{n}`.

## O quantificador 'opcional'
Esse quantificador faz com que o seu precedente tenha de existir ou não, é representado pelo símbolo `?` e faz a mesma coisa que `{0,1}`.

Por exemplo, vamos dar uma olhada nas palavras `fricção` e `ficção`, a diferença gramatical entre elas é o `r`, uma tem e a outra não. Se precisarmos criar uma a expressão em que case com ambas palavras, precisamos apenas colocar o quantificador ao lado do `r` na palavra `fricção`, dessa forma: `fr?icção`.

## O quantificador 'opcional ou infinito'
Esse quantificador faz com que o seu precedente se repita em uma quantidade infinita ou nula, é representado pelo símbolo `*` e faz a mesma coisa que `{0,}`.

> O nome real desse quantificador é `star`.

## O quantificador 'infinito'
Esse quantificador faz com que seu precedente se repita uma ou mais vezes, é representado pelo símbolo `+` e faz a mesma coisa que `{1,}`.

> O nome real desse quantificador é `plus`.

## Quantificadores preguiçosos
Os quantificadores preguiçosos também são os quantificadores não gulosos.

A diferença é bem simples, eles também utilizam os símbolos dos quantificadores gulosos, mas sufixados com um `?`.

Não é só isso, a quantidade de repetições é modificada para o mínimo possível, ou seja, se tivermos a expressão regular `a{2,3}?` e o texto `aaa` ela vai casar apenas com os dois primeiros `a`s.

Os quantificadores preguiçosos são basicamente o contrário dos quantificadores gulosos.

Esse tipo de quantificador pode ser considerado inútil em uma expressão muito pequena, por exemplo, podemos usar `a` ao invés de `a+?`, o uso desses quantificadores são bem específicos e dependem também da expressão regular

# Nota
Se houver um erro de sintaxe no quantificador `{n,m}`, ele será tratado como um literal, dê uma olhada nesse exemplo: https://regex101.com/r/nKpx1t/1.

Qualquer quantificador dentro de uma classe de caracteres se torna um literal.

> Ir para [`Módulo básico:Metacaracteres:Sequências`](sequences/README.md)
