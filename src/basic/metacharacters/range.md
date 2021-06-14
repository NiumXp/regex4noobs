# 3.3.1 - *Range*
Nos tópicos anteriores você já deve ter visto algo como `[0-9]`, nesse caso, a expressão captura os número de 0 à 9, isso é possível por conta do *range* (`-`), poderiamos pegar do 1 até o 5 usando `[1-5]`, por exemplo.

Podemos utilizar letras também. De `a` até `g` ficaria `[a-g]`, de `a` até `x` ficaria `[a-x]` e assim vai...

E não é limitado só à numeros e letras não hein, podemos utilizar `\u` para unicodes especificos, `\0` para octais e `\X` para decimais, exemplos:

```
Unicode     [\u00D8-\u00F6]
Decimal     [\X2B-\XFF]
Octal       [\053-\071]
```

---

Ir para [`Módulo básico:Metacaracteres:Backslash`](backslash.md).
