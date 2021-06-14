# 4 - Âncoras

Existem diversas âncoras, `^`, `\A`, `\b`, `\B`, `$`, `\z`, `\Z` e `\G`, todos são metacaracteres e regulam onde a expressão regular deve atuar.

## Começo da linha
As âncoras `^` e `\A` dizem que o que estiver após a ela deverá se casar apenas no começo da linha.

Por exemplo, a expressão `^a` casa com `abc`, pois no começo dela existe `a`, agora `^b` não casa com `abc` já que `b` não está no começo do texto.

### Nota
A âncora `\A` não é afetada pelo modo `m`, ela faz com que seja apenas no começo de todo texto, diferente da `^`.

Faça os testes com as expressões `\A\d` e `^\d` com o seguinte texto
```
0
1
2
```

> Cuidado ao utilizar `\a` ao invés da âncora `\A`. O metacaratere `\a` representa o caractere [BEL (ASCII 7)](https://en.wikipedia.org/wiki/Bell_character).


## Final da linha
As âncoras `$`, `\Z` e `\z` são iguais as anteriores, mas ao invés de ser no começo, é no final da linha.

Exemplo, `a$` casa com `banana`, `laranja`, `manga` e entre outros, mas não casa com `maçã`.

### Nota
As âncoras `\Z` e `\z` não são afetadas pelo modo `m`, a `\z` é mais especial, ela não corresponderá antes de uma nova linha que nem `\Z`, essa âncora verifica o final do texto de forma absoluta.

Faça os testes com as expressões `\d$`, `\d\Z` e `\d\z` com o seguinte texto
```
0
1
2 3

```
> Note que o texto tem quatro linhas, a última está vazia (ela é necessária para entender o `\z`)!


# Nota
Algumas âncoras não existem em algumas *engines*, por exemplo, `\A` e `\Z` não existem em JavaScript, `\G` não existe em Go e Python... Sempre leia a documentação de onde estiver tentando utilizar expressões regulares!


> Ir para [`Módulo básico:Parabéns`](congratulations.md)
