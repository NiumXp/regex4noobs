# 3.2 - *Lookbehind*

O *lookbehind* tem a mesma ideia que o *lookahead*, fazer uma asserção só que em alguns passos atrás.

Ele também usa a mesma sintaxe do *lookahead* só que com um `<` após o `?`, ficando `(?<=)` na forma positiva e `(?<!)` na negativa.

#### Más noticias
Diferente do *lookahead*, o *lookbehind* não permite passar uma expressão com tamanho indefinido, `(?<=a*)b` daria erro.

> Esse comportamento não quer dizer que `(?<!aa)b` possa ser equivalente a `[^a]{2}b`, mas sim como `[^a]*b`, por exemplo.

---

> Ir para [`Módulo intermediário:Parabéns`](congratulations.md).
