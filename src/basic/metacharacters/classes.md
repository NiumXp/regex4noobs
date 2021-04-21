# 3.3 Classe de caracteres

Ok, classe de caracteres parece um nome complicado, mas não se preocupe! classe de caracteres é um conjunto de caracteres - também é chamado dessa forma hodiernamente.

Bom, se é um conjunto de caracteres não tem mistério, não é mesmo?

## Sintaxe
Um conjunto pode ser representado por `[^?c]`, onde `c` sempre deve exister e representa os caracteres daquele conjunto, e `^` para a oposição/negação de `c`, que pode ou não existir.

O `[` e o metacaractere reponsável pela sintaxe de um conjunto, quando um `^` vier logo após, o conjunto aceita qualquer coisa menos o que estiver em `c`.

O `[` irá procurar pelo primeiro `]` que existir, caso não exista, ocorrerá um erro de sintaxe! também ocorrerá caso o conjunto esteja vazio!

<div align="center">

| Expressão | Erro | Casos válidos |
| :-: | :-: | :-: |
| `[]` | ✅ | |
| `[nium]` | ❌ | `n`, `i`, `u`, `m` |
| `[^]` | ✅ | |
| `[^nium]` | ❌ | Qualquer coisa que não esteja no conjunto `[nium]` |
| `[[]]` | ❌ | `[]` |
| `[` | ✅ | |
| `[^` | ✅ | |
</div>

> Ou seja! O `]` é um literal e o `[` transforma o `]` em um "pseudo-metecaractere"!!

### Mas e aquele tal `c`?
Aquele `c` na representação da sintaxe anterior pode ser entendido como qualquer caractere e/ou outro(s) conjunto(s) pré-definido(s)! Nós veremos alguns daqui a pouco, mas tente usar o `\d`, veja o que acontece!

Por exemplo, no conjunto `[Nn]`, `Nn` é o nosso maravilhoso `c`! Agora no conjunto `[NnIiUuMm]`, você consegue me dizer qual valor representa `c`?

###### Ps: E aí, você já tentou criar um conjunto dentro de outro conjunto?
<br>

> Ir para [`Módulo básico:Metacaracteres:Backslash`](backslash.md)
