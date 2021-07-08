# 2.2 - Nomeando grupos

Podemos nomear grupos de captura ao invés de utilizarmos apenas seus IDs quando formos usar um *backreference* ou pega-lo na saída.

Para nomear um grupo, basta utilizar `(?P<nome>)`.
> Algumas engines permitem utilizar `(?'nome')` ou `(?<nome>)`.

### *Backreference*
Para utilizar um *backreference* nos grupos nomeados podemos utilizar seus próprios IDs (veja o tópico anterior) e o seus nomes através da sintáxe `\k<name>` - em que `nome` é o nome do grupo.

> Algumas *engines* permitem utilizar `\k'name'`.

> A *engine* do Python não permite as sintaxes de *backreference* anteriores, mas em contra partida, é utilizado `(?P=name)`. Ou seja, sempre veja a documentação da *engine* que for utilizar!!!

## Saída
Algumas linguagens de programação retornam o nome do grupo quando finalizar a execução de uma expressão em algum texto, veja o exemplo em Python a seguir

```python
import re

texto = "[NiumXp] Opa, e aí!!"
regex = r"\[(?P<name>\w+)\] (?P<message>.+)"

match = re.search(regex, texto)
match = match.groupdict()  # Retorna um dicionário em que
                           # a chave é o nome do grupo e o
                           # valor é o valor casado.

print(match["name"], "disse", match["message"])
```


---

Ir para [`Módulo Intermediário:Look:Lookahead`](../lookahead.md).
