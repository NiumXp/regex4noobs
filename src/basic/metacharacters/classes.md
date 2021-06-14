# 3.3 - Classe de caracteres

Ok, classe de caracteres parece um nome complicado, mas não se preocupe! classe de caracteres é um conjunto de caracteres - também é chamado dessa forma hodiernamente.

Bom, se é um conjunto de caracteres não tem mistério, não é mesmo?

## Sintaxe
Um conjunto pode ser representado por `[^?c]`, onde `c` sempre deve existir e representa os caracteres do conjunto, e `^` é para a negação de `c`, que pode ou não existir.

O `[` é o metacaractere reponsável pela sintaxe de um conjunto, quando um `^` vier logo em seguida, o conjunto aceita tudo que não estiver em `c`.

O `[` irá procurar pelo primeiro `]` que existir, caso não exista, ocorrerá um erro de sintaxe! também ocorrerá caso o conjunto esteja vazio.

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
Na representação da sintaxe anterior, aquele `c` pode ser entendido como qualquer caractere e/ou outro(s) conjunto(s) pré-definido(s)! Nós veremos alguns daqui a pouco, mas tente usar o `\d`, veja o que acontece!

Por exemplo, no conjunto `[Nn]`, `Nn` é o nosso maravilhoso `c`! Agora no conjunto `[NnIiUuMm]`, você consegue me dizer qual valor `c` representa?

###### Ps: E aí, você já tentou criar um conjunto dentro de outro conjunto?

---

Ir para [`Módulo básico:Metacaracteres:Classe de caracteres:Range`](range.md).
