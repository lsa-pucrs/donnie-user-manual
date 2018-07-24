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



Seção 1: sair do terminal de programação
*********************************************

**Comando**

SAIR


**Argumentos**

Nenhum


**Explicação**

Fecha o ambiente de programação. Só pode ser usado no terminal.


**Exemplo**

SAIR



Seção 2: declaração de variáveis
************************************
**Variável** é um objeto que guarda um valor. Essa variável só poderá receber valores inteiros.

**Comando**

CRIAR x


**Argumentos**

x é a variável que será criada. Essa variável recebe valores inteiros.


**Explicação**

| Existem 5 formas de criar uma variável:
| 1. criar uma variável.
| 2. criar uma variável e atribui um valor inicial.
| 3. criar uma variável que recebe uma expressão.
| 4. criar uma variável dentro do comando de repetição PARA.
| 5. criar uma variável que receberá o valor de outro comando, como: COR (será visto na seção 8), DISTÂNCIA (será visto na seção 8) e POS (será visto na seção 8).

| As variáveis guardam somente os últimos valores recebidos.
 As variáveis guardam somente valores inteiros. Desta forma, se houver um resultado com vírgula, esse será descartado e somente a parte inteira será armazenada na variável.

| Existem regras para o nome das variáveis:
| - Não há diferença entre letras maiúsculas e minúsculas. Desta forma, CRIAR A (maiúsculo) será o mesmo que CRIAR a (minúsculo).
| - Não podem ter caracteres especiais. Exemplo: *, @, #, +
| - Não podem iniciar com número. Exemplo: CRIAR 52abc está errado.


**Exemplo**

1. Para criar uma variável sem valor inicial, pode-se fazer: 

| CRIAR A
| Cria uma variável com o nome A.
| A = 2
Tendo sido criada a variável, pode atribuir um valor diretamente. A variável com o nome A vai armazenar o valor 2.

2. Para criar uma variável com valor inicial, pode-se fazer como a seguir: 

| CRIAR B =5
| Cria uma variável chamada B, que armazena o valor 5

3. Para criar uma variável que recebe uma expressão, pode-se fazer como a seguir: 

| CRIAR C = A + B
Cria uma variável chamada C, que recebe o valor da variável A somado ao valor da variável chamada B. O resultado da variável C é 7.

| C = 1
| Altera o valor da variável C e armazena o valor 1, perdendo o valor anterior.

4.  Para criar uma variável dentro de um comando PARA (esse comando será visto na seção X do manual), pode ser feito da seguinte forma:

| PARA CRIAR d = 0;  d < 5; d = d + 1 FAÇA 
| PF 1
| FIM PARA 

| O robô se deslocará 5 passos para frente.

5. Para criar uma variável que recebe o valor de outro comando, pode-se fazer como a seguir:

| CRIAR d = DISTÂNCIA F
| CRIAR c = COR VERDE
| CRIAR px = POS X

| A variável d armazenará o valor da distância frontal do robô em relação ao objeto.
| A variável c armazenará a quantidade de cores verdes.
| A variável px armazenará a posição atual do robô no eixo x. 
| (Os comandos Distância F, Cor e Pos x serão vistos na seção x)

| G = 5
| Retornará erro porque a variável G ainda não foi criada.



Seção 3: comandos de áudio
******************************
Comandos para manipulação e retorno de áudio.

**1.**
**Comando**

FALAR x


**Argumentos**

x é uma variável, que deve ter sido criada anteriormente.


**Explicação**

| Fala o conteúdo da variável.
 Este som é emitido pelo robô ou pelo ambiente virtual, dependendo de quem estará ativo.


**Exemplo**

| CRIAR x = 5
| FALAR x
| Será falado: 5


**2.**
**Comando**

FALAR "x"


**Argumentos**

x é uma palavra ou frase, que deve vir entre aspas duplas.


**Explicação**

Fala a palavra ou frase contida entre as aspas.  Este som é emitido pelo robô ou pelo ambiente virtual, dependendo de quem estará ativo.


**Exemplo**

| FALAR “oi”
| Será falado: oi


**3.**
**Comando**

| SOM ligado
| SOM desligado


**Argumentos**

O estado do áudio, é ligado ou desligado.


**Explicação**

Comando que liga ou desliga o áudio do recurso que estiver ativo, que poderá ser o robô ou o ambiente virtual. 


**Exemplo**

| SOM LIGADO
| SOM DESLIGADO



Seção 4: operadores
***********************
São operadores que fornecem suporte a expressões matemáticas e lógicas.

**Comando**

Operadores


**Argumentos**

| Matemáticos:
| + soma
| - subtração
| * multiplicação
| / divisão

| Comparadores: 
| <> diferente
| == igual 
| < menor
| > maior
| <= menor ou igual
| >= maior ou igual

| atribuição:
| = atribuição


**Explicação**

Operadores servem para comparar valores ou expressões.


**Exemplo**

| Para realizar uma soma. 
| Criar a = 2
| criando a variável a e atribuindo o valor de 2.
| Criar b = 1
| Criando a variável b e atribuindo o valor de 1.
| Criar soma
| Criando a variável soma
| soma = a + b 
| atribuindo a soma o valor da soma da variável a e b.
| Falar soma
| Será falado: 3

| Para realizar uma divisão. 
| Criar c = 2
| criando a variável c e atribuindo o valor de 2.
| Criar d = 2
| criando a variável d e atribuindo o valor de 2.
| Criar divisão
| Criando a variável divisão
| divisão = c / d 
| Atribuindo o valor da divisão dos conteúdos das variáveis c e d.
| Falar divisão
| Será falado: 1



Seção 5: comandos de movimentação
**************************************
São comandos que movimentam o robô no ambiente.

**1.**
**Comando**

| PF n 


**Argumentos**

| n é o número de passos. 
Este comando aceita somente números inteiros e positivos, ou variáveis que armazenam números inteiros, ou expressões matemáticas que resultem em números inteiros.


**Explicação**

Anda n passos para frente.


**Exemplo**

| PF 5

O robô andará 5 passos para frente. Supondo que o robô está na posição 0, 0 e virado para o norte, o comando PF 5 colocará o robô na posição 5, 0, mantendo a direção para o norte.

| CRIAR A = 10
| PF A
| Fará com que o robô ande 10 passos para frente.

| CRIAR A=10
| CRIAR B=20
| PF A+B
| Fará com que o robô ande 30 passos para frente.

 Se o robô colidir em algo antes de completar a quantidade de passos solicitados. Será informado ao usuário:  “Andei somente X passos para frente. Encontrei obstáculo”. 

| Se for digitado o comando com um número negativo como abaixo: 
| PF -5 
| Será informado ao usuário que o robô andou 0 passos. 


**2.**
**Comando**

| PT n


**Argumentos**

| n é o número de passos.
Este comando aceita somente números inteiros e positivos, ou variáveis que armazenam números inteiros, ou expressões matemáticas que resultem em números inteiros.


**Explicação**

Anda n passos para trás. É como se andasse de ré. 


**Exemplo**

| PT 5

O robô andará 5 passos para trás. Supondo que o robô está na posição 5, 0 e virado para o norte, o comando PT 5 colocará o robô na posição 0, 0, mantendo a direção para o norte.

| CRIAR A = 10
| PT A
| Fará com que o robô ande 10 passos para trás.

| CRIAR A=10
| CRIAR B=20
| PF A+B
| Fará com que o robô ande 30 passos para frente.

 Se o robô colidir em algo antes de completar a quantidade de passos solicitados. Será informado ao usuário:  “Andei somente X passos para trás. Encontrei obstáculo”. 

| Caso seja digitado o comando com número negativo como abaixo: 
| PT -6
| Será informado, andei 0 passos. 




manual da linguagem e eexemplos de uso.
colocar os exercicios como se fossem subsecoes.



GoDonnie Interpreter
-------------

modos de operacao, exemplos de uso


