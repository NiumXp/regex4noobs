# 2.1 - *Backreference*

Um *backreference* casa com o mesmo texto de um grupo de captura anterior. Algumas pessoas gostam de explicar *backreferences* usando tags HTML, eu também sou uma delas!

Imagine que você tenha que capturar uma tag qualquer, podemos usar `<(\w+)>[^\n]*<\/(\w+)>`.

Só que repare numa coisa, podemos passar `<a></b>` e a expressão vai aceitar, isso pode ser um problema para nós, e se quissésemos aceitar apenas que o segundo grupo de caputra deve ter o resultado que o primeiro grupo capturou? Simples, devemos utilizar *backreferences*.

## Identificadores
Alguns grupos recebem um identificador (ID), um identificador sempre será único e começará pelo `1`.

O grupo de captura não nomeado e nomeado (próximo tópico) são alguns dos grupos que criam um identificador.

```
(Olá|Oi) \1 (pessoal|galera) \2
└-ID 1-┘  │ └-----ID 2-----┘  │
         Chama resultado     Chama resultado da captura 2
         da captura 1
```
Na expressão acima, um caso válido seria `Oi Oi galera galera`.

### Nota
Em algumas *engines* só é possível acessar até o identificador `9`, a única linguagem de programação que conheço que permite ir além do `9` é o Python.

Quando o *backreference* só vai até `9`, geralmente a *engine* entende como `octal escape`.

---

Ir para [`Módulo Intermediário:Grupos:Nomeando Grupos`](named.md).
