# 3.2 Quantifiers
Os quantificadores fazem com que o seu precedente se repita em alguma quantidade.

Os simbolos `?`, `*`, `+` e `{n,m}` são usados para representar os quantificadores.

Os quantificadores que eu citei acima são chamados de **quantificadores gulosos** (Greedy quantifiers), os **não gulosos** (Lazy quantifiers) utilizam os mesmos simbolos mas sufixados com um `?`.

### O quantificador base
Antes de entendermos os outros quantificadores e as "classes" deles, vamos ver o quantificador `{n,m}`.

Com esse quantificador podemos estabelecer uma quantidade mínima e máxima para a repetição do precedente, ou seja, `n` é a quantidade mínima que *deve* ser igual ou maior do que zero e `m` é a quantidade máxima que deve ser igual ou maior do que `n`.

Se deixarmos de colocar o `m`, mas deixarmos a vírgula, a quantidade máxima será infinita. Se tirarmos o `m` e a vírgula, a quantidade será exatamente `n`.

## O quantificador 'opcional'
Esse quantificador faz com que o precedente tenha que ter ou não, é representado pelo símbolo `?` e faz a mesma coisa que `{0,1}`.

## O quantificador 'opcional ou infinito'
Esse quantificador faz com que o precedente não exista ou exista só que em uma quantidade não declarada, é representado pelo símbolo `*` e faz a mesma coisa que `{0,}`.

> O nome real desse quantificador é `star`.

## O quantificador 'infinito'
Esse quantificador faz com que seu precedente repita uma ou mais vezes, é representado pelo símbolo `+` e faz a mesma coisa que `{1,}`.

> O nome real desse quantificador é `plus`.


## Quantificadores preguiçosos
Os quantificadores preguiçosos também são os quantificadores não gulosos.

A diferença é bem simples, eles também utilizam os símbolos dos quantificadores gulosos, mas sufixados com um `?`.

Não é só isso, a quantidade de repetições é modificada para o mínimo possível, ou seja, se tivermos a expressão regular `a{2,3}?` e o texto `aaa` ela vai casar apenas com os dois primeiros `a`s.

Os quantificadores preguiçosos são basicamente o contrário dos quantificadores gulosos.

Esse tipo de quantificador pode ser considerado inútil em uma expressão muito pequena, por exemplo, podemos usar `a` ao invés de `a+?`, o uso desses quantificadores são bem específicos e dependem também da expressão regular

# Nota
Se houver um erro de sintáxe no quantificador `{n,m}`, ele será tratado como um literal, dê uma olhada nesse exemplo: https://regex101.com/r/nKpx1t/1.
