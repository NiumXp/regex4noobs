# 5 - *Congratulações*!
**Parabéns**!! Você acabou de terminar o módulo básico!

A partir de agora você já sabe criar expressões regulares para chegar em uma informação!

No próximo módulo veremos como capturar e não capturar algumas coisas específicas nas informações!

> Apenas algumas coisas como os comentários são "modernos" (por isso não é possível utilizar os comentários em algumas *engines*), as outras como as classes de caracteres já existiam antigamente.

## Nota
Muita gente utiliza a palavra "checar" ao invés de "chegar" quando se trata de utilizar as expressões regulares, não está "errado", mas não é muito legal de se falar isso...

Muitos iniciantes podem entender as *regex*s como algo para validar/checar coisa, e essa ideia está totalmente errada!

> Lembre-se, uma expressão regular nunca irá retornar um valor *booleano*, sempre será uma *string* - se não for essêncialmente isso, tem algo de errado e, bem errado acontecendo...

O que eu quero dizer é que quem faz a checagem é o próprio código em cima do retorno da expressão regular, exemplo:

```python
import re

regex = r"^-?\d+$"
texto = "-10a1"

match = re.match(regex, texto)
if match:
    print("Opa, é um número inteiro!")
else:
    print("Xii, não é um número inteiro...")
```

Nesse código Python podemos ver a expressão `regex` que será usada em `texto` para **checar** se ele **REPRESENTA** um número inteiro.

Note que assim que "executamos" `regex` em `texto`, salvamos uma informação (`match`) e logo abaixo **checamos** se ela existe, se existir é porquê nosso texto casa com `regex`.

---

Ir para [`ROADMAP`](../../README.md#ROADMAP).
