# 3. Metacarateres
> Daqui pra frente você verá muito o termo "casar", entenda isso como algo combinante ou resultante.
> Por exemplo, a expressão `a+` combina com os textos `a`, `aa`, `aaa` e entre outros.

A maioria dos caracteres casam com eles mesmos pois são tratados como literais. Existem algumas exceções, essas exceções são chamadas de metacaracteres.

### Dot
É um metacaractere representado por um `.` em que casa com qualquer caractere, até ele mesmo!

Precisamos falar um pouco mais sobre esse metacaractere, ele casa com qualquer caractere, mas não casa com quebras de linhas. Essa exceção existe por motivos históricos.

As primeiras ferramentas a utilizar as expressões regulares foram baseadas em linhas, lendo uma por uma de um arquivo e aplicando a expressão regular. Sabendo disso, não havia a necessidade do metacaractere casar com as quebras de linhas já que seria impossível haver uma em uma linha.

> Esse metacaractere vira um literal quando utilizado em uma classe de caracteres. Não se preocupe, veremos mais a frente, mas fique sabendo desde já!

### Quantifiers
Os quantificadores fazem com que o seu precedente se repita em alguma quantidade.

Os simbolos `?`, `*`, `+` e `{n,m}` são usados para representar os quantificadores.

Os quantificadores que eu citei acima são chamados de **quantificadores gulosos**, os **não gulosos** utilizam os mesmos simbolos mas sufixados com um `?`.

> Veremos mais a fundo sobre os quantificadores.

### Whitespaces
O metacaractere `\s` é **uma classe de caracteres** que pode ser representado por `[\r\n\t\f\v ]`.

`\r` (Carriage Return), `\n` (New line/Line feed), `\t` (Horizontal tabulation), `\f` (Formfeed) e `\v` (Vertical tabulation) e `\0` (Null character) também são metacaracteres.

### Meta sequences
`\d` representa qualquer digito, pode ser entendido como `[0-9]`.

`\s` representa qualquer espaço em branco (tópico acima).

`\w` representa qualquer letra do alfabeto, numeros de 0 a 9 e o *underline* (`_`), pode ser entendido como `[a-zA-Z0-9_]`.
