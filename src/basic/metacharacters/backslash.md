# 3.4 Backslash
A barra invertida é um metacaractere representado pela `\`. Esse metacaractere é comunmente chamado de **caractere de escape** (por escapar metacaracteres - transforma-lós em literais) e/ou **sequência de escape** (por conseguir representar um caractere ASCII em hexadecimal por exemplo).

## Escapando metacaracteres
Para escapar um metacaractere basta prefixa-lo com o `\`.

```
RegExp      -> a\{.*}
Caso válido -> a{becedário}
```

Note que na expressão o escape acontece apenas no `{` e o seu par do outro lado também sofre as consequências. Esse comportamento funciona juntamente com a definição de uma classe de caractere:

```
RegExp      -> a\[.*]
Caso válido -> a[becedário]
```

Fulano: Que bacana! Mas... só por curiosidade, e se for parenteses?<br>
Irá retornar um erro de sintaxe. O motivo disso acontecer eu não sei, segue o roteiro...

Brincadeira, isso acontece porque os parenteses fazem coisas demais e é muito utilizado, não só por isso, eles tem comportamentos beeem diferentes, enquanto os outros são únicos, os parenteses vão decidir o que vai acontecer com o que estiver dentro deles.

```
RegExp      -> (?:[Ee]u sou o ([Nn]ium)!?)
Caso válido -> Eu sou o Nium!
```

Temos a expressão `[Ee]u sou o ([Nn]ium)!?` (se única coisa que você não entenda sejam os parenteses, parabéns! caso contrário, você não conseguiu entender os tópicos anteriores, volte e tente criar algumas expressões para você entender melhor!) e dentro dela temos `[Nn]ium` que também está dentro de parenteses, isso significa que é o que queremos como saída, mas note uma coisa, toda a expressão está dentro de `(?:)`, se escaparmos o parenteses do nosso grupo de captura (`\([Nn]ium)`), faremos com que o parenteses pararelho ao grupo de não-captura (`(?:)`) olhe para o do grupo de captura.

<pre align="center"><code>Expressão válida
(?:[Ee]u sou o ([Nn]ium)!?)
│              └-------┘  │
└-------------------------┘

Expressão com erro de sintaxe
(?:[Ee]u sou o \([Nn]ium)!?)
└-----------------------┘  │
        Sem parelho (erro) ┘
</code></pre>

Ou seja, como o conteúdo dentro dos colchetes e chaves não são expressões tão "poderosas", eles não tem o mesmo comportamento de escape que os parenteses.

> Eu ainda não expliquei como funciona os parenteses porque é bem extenso e complexo, mas na expressão anterior eu usei e expliquei o que estava fazendo.<br><br>
> É de extrema importância que você tente criar outras expressões regulares que nem no exemplo para que você possa se acostumar e conseguir se familiarizar um pouco.<br><br>
> Se você não por em prática e testar as coisas, você não vai aprender, o que eu quero dizer é, atualmente, você conseguiria criar uma expressão regular que casasse com `\s`?<br><br>
> Se você disse que não, sinto muito, mas você não conseguiu entender a primeira linha deste tópico.

## Slash
Eu decidi escrever esta "nota" porque o caractere `/` é um "literal e um metacatere" que acaba gerando muitas dúvidas e problemas.

Sim, eu sei que a frase entre aspas é contraditória, mas foi apenas para te assustar, a barra é considerada um literal, mas na análise léxica do JavaScript, ECMAScript e PHP por exemplo, o `/` é usado para determinar que o quê vier após ele será uma expressão regular, então, ele acaba se tornando um "metacaractere".

> Não é má prática utilizar `\/` para escapar o `/` mesmo se a linguagem já entender como um literal, é até comum, pois a expressão poderá ser usada em diversas linguagens.
