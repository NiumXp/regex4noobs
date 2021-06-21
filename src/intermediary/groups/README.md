# 2 - Grupos

Eita, os grupos... Entenda eles como um... grupo qualquer! só que de expressões regulares!

Um grupo é escrito utilizando os parênteses (`()`). Caso necessário, dê uma revisada sobre o [*backslash*](../../basic/metacharacters/backslash.md) no módulo básico, há uma explicação importante sobre a sintaxe dos grupos.

### Hora do chá quente
A explicação acima foi só para te deixar tranquilo. É agora que a língua arde.

Os parênteses são um construtor de grupo, existem diversos construtores que também utilizam os parênteses só que com algo prefixado dentro deles.

Pode parecer estranho, mas você já viu um construtor e talvez já até utilizou. Você se lembra dos [comentários](../../basic/comments.md)? - Não? Como assim?! Foi a primeira coisa do módulo básico! - Na verdade aquilo se chama grupo de comentário.

## Grupo de captura
Os parêteses sem algum prefixo dentro representam um grupo de captura.
Isso significa que o que casar ali dentro será capturado e retornado na saída da expressão regular.

### Exemplo

```py
import re

texto = "Oi pessoal!!!"
regex = r"[Oo]i (pessoal|galera)"

match = re.match(regex, texto)
print(match.groups())
```

```
('pessoal',)
```
Podemos ver que na saída capturamos o que estava dentro do grupo.

## Grupo de não-captura
Esse grupo é o oposto do grupo de captura acima. Ou seja, ele não cria nenhum identificador (entederemos no próximo tópico) e não captura o que casar detro dele.

Ah, para criar esse grupo basta colocar `?:` dentro dos parênteses, desta forma `(?:)`.

> Esse grupo é bastante utilizado junto com o [*pipe*](../pipe.md). Não só ele, mas também com todos os grupos...


# Nota
Alguns grupos não permitem utilizar quantificadores dentro deles. Um grupo de captura e de não captura são alguns dos que permitem utilizar.

---

Ir para [`Módulo Intermediário:Grupos:Backreference`](backreference.md).
