# Fundamentos de Python

- [Fundamentos de Python](#fundamentos-de-python)
  - [Inserindo expressões no shell interativo](#inserindo-expressões-no-shell-interativo)

![Fundamentos de Python](img/000143.jpg)

A linguagem de programação Python possui uma ampla variedade de construções sintáticas, funções padrão da biblioteca e recursos do ambiente de desenvolvimento interativo. Felizmente, você pode ignorar a maior parte disso; você só precisa aprender o suficiente para escrever alguns programas úteis.

Você terá, no entanto, que aprender alguns conceitos básicos de programação antes de poder fazer qualquer coisa. Como um assistente em treinamento, você pode pensar que esses conceitos parecem misteriosos e tediosos, mas com algum conhecimento e prática, você poderá comandar seu computador como uma varinha mágica e realizar feitos incríveis.

Este capítulo tem alguns exemplos que o incentivam a digitar no *shell interativo*, também chamado de *REPL* (*Read-Evaluate-Print Loop*), que permite rodar (ou *executar*) instruções Python, uma de cada vez, e mostra instantaneamente os resultados. O uso do shell interativo é ótimo para aprender o que as instruções básicas do Python fazem, então experimente enquanto você o acompanha. Você se lembrará muito mais das coisas que faz do que das que apenas lê.

## Inserindo expressões no shell interativo

Você pode executar o shell interativo iniciando o editor Mu, que você deve ter baixado ao seguir as instruções de configuração no Prefácio. No Windows, abra o menu Iniciar, digite "Mu" e abra o aplicativo Mu. No macOS, abra a pasta Aplicativos e clique duas vezes em **Mu**. Clique no botão **Novo** e salve um arquivo vazio como *blank.py*. Quando você executar esse arquivo vazio, clicando no botão **Executar** ou pressionando ```F5```, ele abre o shell interativo, que será aberto como um novo painel que se abre na parte inferior da janela do editor de Mu. Você deve ver um prompt *>>>* no shell interativo.

```pycon
>>> 2 + 2
4
>>>
```

No Python, ```2 + 2``` é chamado de *expressão*, que é o tipo mais básico de instrução de programação na linguagem. Expressões consistem em valores (como 2) e operadores (como +) e sempre podem avaliar (ou seja, reduzir) até um único valor. Isso significa que você pode usar expressões em qualquer lugar do código Python que também possa usar um valor.

No exemplo anterior, ```2 + 2``` é avaliado em um único valor, 4. Um valor único sem operadores também é considerado uma expressão, embora seja avaliado apenas para si mesmo, conforme mostrado aqui:

```pycon
>>> 2
2
```

>**TUDO BEM HAVER ERROS!**
>Os programas travam se contiverem código que o computador não entende, o que fará com que o Python mostre uma mensagem de erro. Uma mensagem de erro não interromperá o computador, portanto, não tenha medo de cometer erros. Uma *falha* significa que o programa parou de funcionar inesperadamente.
>Se você quiser saber mais sobre um erro, procure o texto exato da mensagem de erro online para obter mais informações. Você também pode conferir os recursos em *<https://nostarch.com/automatestuff2/>* para ver uma lista de mensagens de erro comuns do Python e seus significados.

Você também pode usar muitos outros operadores nas expressões Python. Por exemplo, a Tabela 1-1 lista todos os operadores matemáticos no Python.

Tabela 1-1: Operadores matemáticos da maior para a menor precedência  
| Operador | Operação | Exemplo | Avalia como. . . |
| :---: | :---: | :---: | :---: |
| \*\* | Expoente | 2 \*\* 3 | 8 |
| % | Módulo / restante | 22 % 8 | 6 |
| // | Divisão inteira / quociente com piso | 22 // 8 | 2 |
| / | Divisão | 22/8 | 2.75 |
| \* | Multiplicação | 3 \* 5 | 15 |
| - | Subtração | 5 - 2 | 3 |
| + | Adição | 2 + 2 | 4 |

A *ordem das operações* (também chamada *precedência*) dos operadores matemáticos do Python é semelhante à da matemática. O operador ```**``` é avaliado primeiro; os operadores ```*```, ```/```, ```//``` e ```%``` são avaliados a seguir, da esquerda para a direita; e os operadores ```+``` e ```-``` são avaliados por último (também da esquerda para a direita). Você pode usar parênteses para substituir a precedência usual, se necessário. O espaço em branco entre os operadores e os valores não importa para o Python (exceto o recuo no início da linha), mas um único espaço é uma convenção. Digite as seguintes expressões no shell interativo:

```pycon
>>> 2 + 3 * 6
20
>>> (2 + 3) * 6
30
>>> 48565878 * 578453
28093077826734
>>> 2 ** 8
256
>>> 23 / 7
3.2857142857142856
>>> 23 // 7
3
>>> 23 % 7
2
>>> 2      +           2
4
>>> (5 - 1) * ((7 + 1) / (3 - 1))
16.0
```

Em cada caso, você como programador deve inserir a expressão, mas o Python faz a parte mais difícil de avaliá-la em um único valor. O Python continuará avaliando partes da expressão até que ela se torne um valor único, como mostrado aqui:

![Expressão](img/000066.jpg)

Essas regras para reunir operadores e valores para formar expressões são uma parte fundamental do Python como linguagem de programação, assim como as regras gramaticais que nos ajudam a nos comunicar. Aqui está um exemplo:

- **Esta é uma frase em português gramaticalmente correta.**

- **Isto é gramaticalmente, não está em português correto a.**

A segunda linha é difícil de analisar porque não segue as regras do português. Da mesma forma, se você digitar uma instrução Python incorreta, o Python não será capaz de entendê-la e exibirá uma mensagem de erro ```SyntaxError```, conforme mostrado aqui:

```pycon
>>> 5 +
  File "<stdin>", line 1
    5 +
      ^
SyntaxError: invalid syntax
>>> 42 + 5 + * 2
  File "<stdin>", line 1
    42 + 5 + * 2
             ^
SyntaxError: invalid syntax
```

Você sempre pode testar para ver se uma instrução funciona inserindo-a no shell interativo. Não se preocupe em quebrar o computador: o pior que pode acontecer é que o Python responda com uma mensagem de erro. Desenvolvedores de software profissionais recebem mensagens de erro enquanto escrevem código o tempo todo.
