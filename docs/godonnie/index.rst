.. _godonnie:

===============
Donnie Programming Environment 
===============

Introduction
-------------

.. image:: ./images/donnie.png
    :align: center
    :alt: sempre use alt para descreve a imagem p um deficiente visual

explica brevemente, cita o artigo, mostra algum exemplo pronto.

GoDonnie Programming Language
-------------

***************************
Manual da Linguagem Donnie
***************************

1.Contexto da GoDonnie
#######################

A GoDonnie é uma linguagem de programação, que comanda um robô chamado Donnie
por um cenário. Este robô funciona em um ambiente próprio. Para tal, estando em um
terminal Linux, é necessário digitar donnie_player e pressionar a tecla ENTER.

Para comando o robô, o usuário pode utilizar o modo linha de comando ou arquivo. Para
utilizar, o modo de linha de comando, deve ser digitado godonnie -t. Para entrar no
modo arquivo, deve ser digitado godonnie -f. Essas expressões podem ser digitadas em
minúsculo ou maiúsculo.

No modo de linha de comando, após ter sido digitado godonnie -t, o usuário digita os
comandos desejados. Pode ser digitado um comando por linha ou vários comandos em
uma mesma linha. Após cada linha, o usuário deve pressionar a tecla ENTER. Para que o
robô execute os comandos, é preciso pressionar a tecla ESC. Desta forma, o usuário
pode digitar uma comando e pressionar ENTER e ESC, ou escrever um comando por
linha, pressionando a tecla ENTER para mudar de linha, e somente pressionar a tecla
ESC quando desejar executar os comandos.

O usuário também pode criar um arquivo de texto, que contenha vários comandos.
Desta forma, pode executar esse arquivo ao invés de ter que digitar repetidamente
blocos de comando, por exemplo. Para executar um arquivo, o usuário deve digitar
godonnie -f acompanhado do nome do arquivo, e pressionar a tecla ENTER. Esse arquivo já deve ter sido criado
com a extensão .txt ou .GD. Um arquivo .GD é um arquivo de texto salvo com essa
extensão. Este arquivo deve ter sido salvo na mesma pasta onde está o programa da
GoDonnie.

A GoDonnie não diferencia letras minúsculas de maiúsculas.
O robô sempre parte da posição 0,0 virado para o norte. Esta posição fica no canto
inferior à esquerda.


+-------------------------------------------------------------------------------------+
|                     **Seção 1: Sair do terminal de programação**                    |
+===================+=====================+=====================+=====================+
|    **Comando**    |   **Argumentos**    |   **Explicação**    |    **Eventos**      |
+-------------------+---------------------+---------------------+---------------------+
|                   |                     |Fecha o ambiente de  |                     |
|     **SAIR**      |       nenhum        |programação. Só pode |        SAIR         |
|                   |                     |ser usado no terminal|                     |
+-------------------+---------------------+---------------------+---------------------+


+-------------------------------------------------------------------------------------+
|                     ** Seção 2: Declaração de variáveis**                           |
|**Variável** é um objeto que guarda um valor. Essa variável só poderá receber valores|
|inteiros.                                                                            |
+===================+=====================+=====================+=====================+
|   **Comando**     |   **Argumentos**    |   **Explicação**    |     **Eventos**     |
+-------------------+---------------------+---------------------+---------------------+
|    **CRIAR** x    |x é a variável que se| Existem 5 formas de |1)Para criar uma vari|
|                   |rá criada. Essa variá|criar uma variável:  |ável sem valor inicia|
|                   |vel recebe valores in|1)Criar uma variável;|l, pode-se fazer:    |
|                   |teiros.              |2)Criar uma variável |CRIAR A              |
|                   |                     |e atribuir um valor i|Cria uma variável com|
|                   |                     |nicial;              | o nome A.           |
|                   |                     |3)Criar uma variável |A = 2                |
|                   |                     |que recebe uma expres|Tendo sido criada a v|
|                   |                     |são;                 |ariável, pode atribui|
|                   |                     |4)Criar uma variável |r um valor diretament|
|                   |                     |dentro do comando de |e. A variável com nom|
|                   |                     |repetição PARA;      |e A vai armazenar o v|
|                   |                     |5)Criar uma variável |alor 2.              |
|                   |                     |que receberá o valor |                     |
|                   |                     |de outro comando, com|2)Para criar uma vari|
|                   |                     |o: COR, DISTANCIA e P|ável com valor inicia|
|                   |                     |OS;                  |l, pode-se fazer como|
|                   |                     |                     | a seguir:           |
|                   |                     |As variáveis guardam |CRIAR B = 5          |
|                   |                     |somente os últimos va|Cria uma variável cha|
|                   |                     |lores recebidos.     |mada B que armazena o|
|                   |                     |As variáveis guardam |valor 5.             |
|                   |                     |somente valores intei|                     |
|                   |                     |ros. Desta forma se h|3)Para criar uma vari|
|                   |                     |ouver um resultado co|ável que recebe uma e|
|                   |                     |m vírgula, esse será |xpressão, pode-se faz|
|                   |                     |descartado e somente |er como a seguir:    |
|                   |                     |a parte inteira será |CRIAR C = A + B      |
|                   |                     |armazenada na variáve|Cria uma variável cha|
|                   |                     |l.                   |mada C, que recebe o |
|                   |                     |                     |valor da variável A s|
|                   |                     |Existem regras para o|omado ao valor da var|
|                   |                     |nome das variáveis:  |iável chamada B. O re|
|                   |                     |- não há diferença en|sultado da variável C|
|                   |                     |tre letras maiúsculas| é 7.                |
|                   |                     | e minúsculas. Desta |                     |
|                   |                     |forma, CRIAR A(maiúsc|C = 1                |
|                   |                     |ulo) será o mesmo que|Altera o valor da var|
|                   |                     | CRIAR a(minúsculo). |iável C e armazena o |
|                   |                     |- não podem ter carac|valor 1, perdendo o v|
|                   |                     |teres especiais. Exem|alor anterior.       |
|                   |                     |plo:*, @, #, +       |                     |
|                   |                     |- não podem iniciar c|4)Para criar uma vari|
|                   |                     |om número. Exemplo: C|ável dentro de um com|
|                   |                     |RIAR 53abc está errad|ando PARA, pode ser f|
|                   |                     |o.                   |eito da seguinte form|
|                   |                     |                     |a:                   |
|                   |                     |                     |PARA CRIAR d = 0; d >|
|                   |                     |                     | 5; d = d + 1 FAÇA   |
|                   |                     |                     |PF 1                 |
|                   |                     |                     |FIM PARA             |
|                   |                     |                     |O robô se deslocará 5|
|                   |                     |                     | passos para a frente|
|                   |                     |                     |                     |
|                   |                     |                     |5)Para criar uma vari|
|                   |                     |                     |ável que recebe o val|
|                   |                     |                     |or de outro comando, |
|                   |                     |                     |pode-se fazer como a |
|                   |                     |                     |seguir:              |
|                   |                     |                     |CRIAR d = DISTANCIA F|
|                   |                     |                     |CRIAR c = COR VERDE  |
|                   |                     |                     |CRIAR px = POS X     |
+-------------------+---------------------+---------------------+---------------------+


manual da linguagem e eexemplos de uso.
colocar os exercicios como se fossem subsecoes.



GoDonnie Interpreter
-------------

modos de operacao, exemplos de uso


