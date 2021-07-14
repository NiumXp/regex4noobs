# 3 - *Lookaround*

De vez em quando precisamos criar afirmações sobre o que estiver ao lado do que quisermos capturar. Por exemplo, vamos supor - mesmo sendo verdade - que nós tenhamos o texto

```
Gosto de utilizar o nome Nium no Discord e NiumXp em outras plataformas, tipo o GitHub.
```

..e queiramos pegar a palavra `Nium` que está ao lado de `Xp`, poderiamos até usar a expressão `NiumXp`, só que eu disse que queriamos apenas a palavra `Nium` e não `NiumXp` - que será retornado na expressão `NiumXp`.

### Vamos fazer alguns testes?
Vamos dizer que `texto` seja `NiumXp` e bora lá, veja este código
```py
resultado = re.match(r"NiumXp", texto)
assert resultado.string == "Nium"
```
..ele irá dar erro, já que a expressão `NiumXp` casa apenas com `NiumXp` - que também é o valor de `resultado.string` - que não é valor esperado (`Nium`).

Podemos criar um grupo para pegar apenas `Nium`, saca só
```py
resultado = re.match(r"(Nium)Xp", texto)
assert resultado.groups()[0] == "Nium"
```
..pegar o resultado ficou mais estranho não é? Fica até complicado de explicar porque o `[0]` está ali...

Eu sei, eu sei que daria para trocar por `resultado.group(1)`, só que, porque `1` ao invés de `0` que nem ali em cima?...

Esqueça tudo isso por agora e olhe só como um *lookahead* negativo deixa nosso código bonitão
```py
resultado = re.match(r"Nium(?=Xp)", texto)
assert resultado.string == "Nium"
```
..é, bem melhor!


## Comportamento

Quando utilizamos algum *lookaround*, estamos dizendo para a *engine* dar alguns passos e confirmar se ali existe algo só que não nos retorne o que está ali.

Ou seja, queremos a palavra `Nium` em que `Xp` esteja seguinte à ela.

---

> Ir para [`Módulo Intermediário:Look:Lookahead`](lookahead.md).
