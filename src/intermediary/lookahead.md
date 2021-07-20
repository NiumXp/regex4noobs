# 3.1 - *Lookahead*

O *lookahead* é expresso por `(?=)` em sua forma positiva e em `(?!)` quando negativa.

Com essa asserção apenas fazemos a *engine* checar alguns passos a frente do nosso *match* para confirmar se está realmente certo.

A asserção não leva em conta o tamanho da expressão que você passar a ela. Por exemplo, vamos ver esse *lookahead* negativo: `Nium(?!Xp)`, queremos `Nium` e uma asserção de que à frente não haja `Xp`, ou seja, se aplicarmos em `Nium!`, teriamos a resposta `Nium` sem problemas.

---

Ir para [`Módulo Intermediário:Look:Lookbehind`](lookbehind.md).
