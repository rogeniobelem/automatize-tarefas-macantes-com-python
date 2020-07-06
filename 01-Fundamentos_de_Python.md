# Fundamentos de Python

- [Fundamentos de Python](#fundamentos-de-python)
  - [Inserindo expressões no shell interativo](#inserindo-expressões-no-shell-interativo)
  - [Os tipos de dados Inteiro, Ponto flutuante e String](#os-tipos-de-dados-inteiro-ponto-flutuante-e-string)
  - [Concatenação e replicação de strings](#concatenação-e-replicação-de-strings)

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

Você sempre pode testar para ver se uma instrução funciona inserindo-a no shell interativo. Não se preocupe em quebrar o computador: o pior que pode acontecer é que o Python responda com uma mensagem de erro. Desenvolvedores de software profissionais sempre recebem mensagens de erro enquanto escrevem código.

## Os tipos de dados Inteiro, Ponto flutuante e String

Lembre-se de que expressões são apenas valores combinados com operadores e sempre são avaliadas em um único valor. Um *tipo de dados* é uma categoria para valores e todo valor pertence a exatamente um tipo de dados. Os tipos de dados mais comuns no Python estão listados na Tabela 1-2. Os valores -2 e 30 , por exemplo, são considerados valores *inteiros*. O tipo de dados inteiro (ou *int*) indica valores que são números inteiros. Os números com um ponto decimal (como *3.14*) são chamados de *números de ponto flutuante* (ou *floats*). Observe que, embora o valor 42 seja um número inteiro, o valor 42.0 seria um número de ponto flutuante.

**Tabela 1-2**: *Tipos de dados comuns*
| Tipo de dados | Exemplos |
| :---: | :---: |
| Inteiros|-2 , -1 , 0 , 1 , 2 , 3 , 4 , 5|
| Números de ponto flutuante | -1.25, -1.0, -0.5, 0.0, 0.5, 1.0, 1.25 |
| Cordas | 'a' , 'aa' , 'aaa' , 'Olá!' , '11 gatos ' |

Os programas Python também podem ter valores de texto chamados *strings*, ou *strs* (pronuncia-se "stirs"). Sempre coloque sua string entre caracteres de aspas simples (') (como em 'Hello' ou 'Goodbye cruel world!'), Para que o Python saiba onde a string começa e termina. Você pode até ter uma string sem caracteres '' , chamada *string em branco* ou *string vazia*. As strings são explicadas em mais detalhes no Capítulo 4.

Se você vir a mensagem de erro ```SyntaxError: EOL while scanning string literal```, provavelmente esqueceu o caractere de aspas simples no final da string, como neste exemplo:

```pycon
>>> 'Olá, mundo!
SyntaxError: EOL while scanning string literal
```

## Concatenação e replicação de strings

O significado de um operador pode mudar com base nos tipos de dados dos valores próximos a ele. Por exemplo, + é o operador de adição quando opera em dois números inteiros ou em valores de ponto flutuante. No entanto, quando + é usado em dois valores de cadeia, ele une as cadeias como o operador de *concatenação de cadeias*. Digite o seguinte no shell interativo:

```pycon
>>> 'Alice' + 'Bob'
'AliceBob'
```

A expressão é avaliada em uma única e nova string cujo valor é a combinação do texto das duas iniciais. No entanto, se você tentar usar o operador + em uma string e um valor inteiro, o Python não saberá como lidar com isso e exibirá uma mensagem de erro.

```pycon
>>> 'Alice' + 42
Traceback (most recent call last):
  File "<pyshell#0>", line 1, in <module>
    'Alice' + 42
TypeError: can only concatenate str (not "int") to str
```

A mensagem de erro ```can only concatenate str (not "int") to str``` significa que o Python pensou que você estava tentando concatenar um número inteiro para a string ```'Alice'```. Seu código precisará converter explicitamente o número inteiro em uma string, porque o Python não pode fazer isso automaticamente. (A conversão de tipos de dados será explicada em “ Dissecando o seu programa ” na página 13 quando falamos sobre as funções ```str()```, ```int()``` e ```float()```).

O operador \* multiplica dois valores inteiros ou de ponto flutuante. Mas quando o operador \* é usado em um valor de string e um valor inteiro, ele se torna o operador de *replicação de string*. Digite uma sequência multiplicada por um número no shell interativo para ver isso em ação.

```pycon
>>> 'Alice' * 5
'AliceAliceAliceAliceAlice'
```

A expressão é avaliada em uma única string que repete a string original um número de vezes igual ao valor inteiro. A replicação de string é um truque útil, mas não é usada com tanta frequência como concatenação de cadeias.

O operador \* pode ser usado com apenas dois valores numéricos (para multiplicação) ou um valor de string e um valor inteiro (para replicação de string). Caso contrário, o Python exibirá apenas uma mensagem de erro, como a seguinte:

```pycon
>>> 'Alice' * 'Bob'
Traceback (most recent call last):
  File "<pyshell#32>", line 1, in <module>
    'Alice' * 'Bob'
TypeError: can't multiply sequence by non-int of type 'str'
>>> 'Alice' * 5.0
Traceback (most recent call last):
  File "<pyshell#33>", line 1, in <module>
    'Alice' * 5.0
TypeError: can't multiply sequence by non-int of type 'float'
```

Faz sentido que o Python não entenda essas expressões: você não pode multiplicar duas palavras e é difícil replicar uma string arbitrária um número fracionário de vezes.
