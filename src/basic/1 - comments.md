# 1 - Comentários
Comentários são muitos importantes na hora de escrever uma expressão regular extensa.

Imagine só você ter mais de 100 casos que precisam casar e uma expressão bem grande e do nada alguns casos param de ser aceitos, ia dar um trabalinho rever a expressão toda não é? Para evitar isso, os comentários são de grande ajuda!

## Quando eu devo usar os comentários?
Você sempre deve utilizar comentários enquanto estiver escrevendo uma expressão regular!
Assim que você a terminar, vai de você apagar os comentários ou não, eu geralmente os mantenho!

## Exemplos
Um comentário pode ser feito escrevendo `(?#)` e colocando o conteúdo após o `#`.
```
(?#Eu sou um comentário)\w+?

(\d+)(?#Eu também sou um comentário! Mas de outra RegExp!).*
```
Não tenha medo do `\w+?`, `(\d+)` ou `.*` ao lado das expressões, veremos mais para frente o que essas coisas fazem. Por enquanto atente-se apenas aos comentários!

### Nota
Você pode colocar qualquer coisa dentro de um comentário, menos um `)`.
A *engine* irá ignorar tudo após `(?#` até um `)`.

Algumas *engines* de algumas linguagens de programação não suportam essa sintaxe e geralmente possui um jeitinho único, por exemplo, no caso do [Python](https://www.python.org) - utilizando o módulo [`re`](https://docs.python.org/3/library/re.html) - podemos utilizar uma *long string*, escrever a expressão regular em diversas linhas e adicionar comentários no final delas:

```python
pattern = r"""
^                   # COMEÇO da string
[^\n]               # Qualquer coisa QUE NÃO SEJA uma quebra de linha
*                   # Precedente se REPETE zero ou mais vezes
$                   # FINAL da string
"""
```

Esses tipos de comentários únicos inviabilizam testar as expressões externamente, ou seja, esse tipo de comentário só pode ser utilizado quando as expressões não serão mais modificadas!

---

Ir para [`Módulo básico:Funcionamento`](operation.md).
