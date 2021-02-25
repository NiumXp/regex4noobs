# 2. Funcionamento
Antes de vermos os metacaracteres eu acho necessário explicar como uma expressão regular funciona quando você for escrever uma.

A expressão `aa` casa com `aa` por exemplo, isso só funcionou porque na primeira posição eu quero que o literal `a` case com a letra `a`, o mesmo acontece na segunda posição.

Ou seja, as expressões regulares são baseadas em posições, mas não se preocupe, não é limitado a só uma posição não, podemos utilizar os quantificadores e criar listas de caracteres para uma posição ocupar o espaço de outras.

A expressão `[a-c]` faz com que você crie uma lista dos caracteres que você quer casar na posição, ali eu quero apenas os caracteres de `a` a `c`, ou seja, `a`, `b` e `c` são letras que casam com a expressão regular.

Agora vamos supor que eu tenha a lista `\d` (apenas digitos) e preciso repetir ela para as 3 próximas posições, para isso utilizamos um quantificador, espcialmente o `{n,m}` já que temos uma quantidade fixa, então nossa expressão ficaria `\d{4}`. Agora nossa expressão casaria com qualquer numero que contenha 4 digitos - mesmo se tiver zeros no começo.

Estes breves exemplos são muito bons entender de começo, te ajudará bastante!

> Ir para [`Módulo básico:Metacaracteres`](metacharacters/README.md)
