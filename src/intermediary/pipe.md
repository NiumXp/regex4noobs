# 1 - *Pipe*
O *pipe* é um metacaractere representado por um `|` e pode ser entendido como um "ou".

Por exemplo, vamos ver a seguinte expressão
```
[A-C]       A, B, C
|           ou
[G-Z]       De G até Z
```
Nela dizemos que não queremos as letras `D`, `E` e `F` técnicamente, podemos usar `[A-CG-Z]` para entender melhor.

### Opa opa
Não se engane pensando que o *pipe* faz o "ou" apenas com o seu precedente e subsequente. Ele irá utilizar tudo em que seu grupo e os outros *pipes* dentro permitir.

Por exemplo, `Olá|Oi` casará com `Olá` ou `Oi` ao invés de `Olài` ou `Oloi`.

# Nota
Esse metacaractere vira um literal quando estiver dentro de uma classe de caracteres.

---

Ir para [`Módulo Intermediário:Grupos`](groups/README.md).
