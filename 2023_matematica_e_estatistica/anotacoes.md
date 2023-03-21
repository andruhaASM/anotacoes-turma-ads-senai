# Passo a passo para resolver o desafio de montar a Criptografia
Enunciado do desafio está nesse [link](https://ava.sesisenai.org.br/pluginfile.php/575866/mod_scorm/content/1/dist/pdf/modulo1/pdf_desafio.pdf)
Frase a ser criptografada: "ESTUDAR PARA TRANSFORMAR O MUNDO!"
A frase contem 33 caracteres, sendo 28 letras, 4 espaços e 1 ponto de exclamação.
Para facilitar a criptografia acrescentou-se mais um ponto de exclamação ao final da frase.

Para criptografar a frase vamos dividir a mesma em várias matrizes-linhas de 2 elementos e codificar cada letra de acordo coma a tabela de correspondência dada no enunciado do desafio:

<a href="https://ibb.co/rZ81S2b"><img src="https://i.ibb.co/Zh4kPzH/Captura-de-tela-de-2023-03-20-18-26-41.png" alt="Captura-de-tela-de-2023-03-20-18-26-41" border="0"></a>

$$\[
 \begin{matrix}
  [5 & 19]
 \end{matrix}
\]
 \end{pmatrix}$$

$$\[
 \begin{matrix}
  [20 & 21]
 \end{matrix}
\]
 \end{pmatrix}$$

$$\[
 \begin{matrix}
  [4 & 1]
 \end{matrix}
\]
 \end{pmatrix}$$

$$\[
 \begin{matrix}
  [18 & 31]
 \end{matrix}
\]
 \end{pmatrix}$$

$$\[
 \begin{matrix}
  [16 & 1]
 \end{matrix}
\]
 \end{pmatrix}$$

$$\[
 \begin{matrix}
  [18 & 1]
 \end{matrix}
\]
 \end{pmatrix}$$

$$\[
 \begin{matrix}
  [31 & 20]
 \end{matrix}
\]
 \end{pmatrix}$$

$$\[
 \begin{matrix}
  [5 & 19]
 \end{matrix}
\]
 \end{pmatrix}$$

$$\[
 \begin{matrix}
  [18 & 1]
 \end{matrix}
\]
 \end{pmatrix}$$

$$\[
 \begin{matrix}
  [14 & 19]
 \end{matrix}
\]
 \end{pmatrix}$$

$$\[
 \begin{matrix}
  [6 & 15]
 \end{matrix}
\]
 \end{pmatrix}$$

$$\[
 \begin{matrix}
  [18 & 13]
 \end{matrix}
\]
 \end{pmatrix}$$

$$\[
 \begin{matrix}
  [1 & 18]
 \end{matrix}
\]
 \end{pmatrix}$$

$$\[
 \begin{matrix}
  [31 & 15]
 \end{matrix}
\]
 \end{pmatrix}$$

$$\[
 \begin{matrix}
  [31 & 13]
 \end{matrix}
\]
 \end{pmatrix}$$

$$\[
 \begin{matrix}
  [21 & 14]
 \end{matrix}
\]
 \end{pmatrix}$$

$$\[
 \begin{matrix}
  [4 & 15]
 \end{matrix}
\]
 \end{pmatrix}$$

$$\[
 \begin{matrix}
  [29 & 29]
 \end{matrix}
\]
 \end{pmatrix}$$

Optou-se para dividir a mensagem em pares de letras por que se a mensagem for interceptada parcialmente, fica mais difícil de decifrar.

Além disso, no mundo de comunicação por rede os dados normalmente são divididos em pacotes e enviados para o receptor junto com a instrução de montagem que recupera a mensagem ao receber todos os pacotes.

Outro motivo seria treinar a habilidade de multiplicar as matrizes de forma manual. 

Em seguida, cada uma das matrizes-linha devem ser multiplicadas pela chave:

$$\[
 \begin{bmatrix}
  4 & 1 \\
  3 & 1 \\
 \end{bmatrix}
\]
 \end{pmatrix}$$

Vamos exemplificar apenas as primeiras 3 pares de letras.
### E e S

$$\[
 \begin{matrix}
  5 & 19\\
 \end{matrix}
\]
 \end{pmatrix}  \times 
\[
 \begin{bmatrix}
  4 & 1 \\
  3 & 1 \\
 \end{bmatrix}
\]
 \end{pmatrix} =
 \begin{matrix}
  [5*4 + 19*3 & 5*1 + 19*1]\\
 \end{matrix}
\]
 \end{pmatrix}  =
 \begin{matrix}
  [77& 24]\\
 \end{matrix}
\]
 \end{pmatrix} 
$$
### T e U

$$\[
 \begin{matrix}
  20 & 21\\
 \end{matrix}
\]
 \end{pmatrix}  \times 
\[
 \begin{bmatrix}
  4 & 1 \\
  3 & 1 \\
 \end{bmatrix}
\]
 \end{pmatrix} =
 \begin{matrix}
  [20*4 + 21*3 & 20 + 21]\\
 \end{matrix}
\]
 \end{pmatrix}  =
 \begin{matrix}
  [143& 41]\\
 \end{matrix}
\]
$$

### D e A

$$\[
 \begin{matrix}
  4 & 1\\
 \end{matrix}
\]
 \end{pmatrix}  \times 
\[
 \begin{bmatrix}
  4 & 1 \\
  3 & 1 \\
 \end{bmatrix}
\]
 \end{pmatrix} =
 \begin{matrix}
  [4*4 + 1*3 & 4 + 1]\\
 \end{matrix}
\]
 \end{pmatrix}  =
 \begin{matrix}
  [19& 5]\\
 \end{matrix}
\]
 \end{pmatrix} 
$$ 

O processo se repete até o último carácter (`!`). Os cálculos completos feitos a mão podem ser encontrados em anexo.

## Mensagem criptografada

No final, a mensagem criptografada seria assim:

$$\[
 \begin{matrix}
  [77 & 24]
 \end{matrix}
\]
 \end{pmatrix}$$

$$\[
 \begin{matrix}
  [143 & 41]
 \end{matrix}
\]
 \end{pmatrix}$$

$$\[
 \begin{matrix}
  [19 & 5]
 \end{matrix}
\]
 \end{pmatrix}$$

$$\[
 \begin{matrix}
  [165 & 49]
 \end{matrix}
\]
 \end{pmatrix}$$

$$\[
 \begin{matrix}
  [67 & 17]
 \end{matrix}
\]
 \end{pmatrix}$$

$$\[
 \begin{matrix}
  [75 & 19]
 \end{matrix}
\]
 \end{pmatrix}$$

$$\[
 \begin{matrix}
  [184 & 51]
 \end{matrix}
\]
 \end{pmatrix}$$

$$\[
 \begin{matrix}
  [75 & 19]
 \end{matrix}
\]
 \end{pmatrix}$$

$$\[
 \begin{matrix}
  [113 & 33]
 \end{matrix}
\]
 \end{pmatrix}$$

$$\[
 \begin{matrix}
  [69 & 21]
 \end{matrix}
\]
 \end{pmatrix}$$

$$\[
 \begin{matrix}
  [111 & 31]
 \end{matrix}
\]
 \end{pmatrix}$$

$$\[
 \begin{matrix}
  [58 & 19]
 \end{matrix}
\]
 \end{pmatrix}$$

$$\[
 \begin{matrix}
  [169 & 46]
 \end{matrix}
\]
 \end{pmatrix}$$

$$\[
 \begin{matrix}
  [163 & 44]
 \end{matrix}
\]
 \end{pmatrix}$$

$$\[
 \begin{matrix}
  [126 & 35]
 \end{matrix}
\]
 \end{pmatrix}$$

$$\[
 \begin{matrix}
  [61 & 19]
 \end{matrix}
\]
 \end{pmatrix}$$

$$\[
 \begin{matrix}
  [203 & 58]
 \end{matrix}
\]
 \end{pmatrix}$$

## Descriptografando a mensagem
Para descriptografar a mensagem precisamos multiplicar cada parte da mensagem criptografada por inversa da matriz chave.

Para calcular a inversa da matriz chave é calculada pela formula:
$$\[
A^{-1}=\begin{bmatrix}
          a_{11} & a_{12} \\ 
          a_{21} & a_{22}
       \end{bmatrix}^{-1}
      =\frac{1}{\lvert A\rvert}
       \begin{bmatrix}
           a_{22} & -a_{12} \\ 
          -a_{21} &  a_{11}
       \end{bmatrix} \,.
\]$$


Onde:

$$
\lvert A\rvert}$$ - é determinante da matriz A calculada pela fórmula:

$$\[
\lvert A\rvert} = a_{11} * a_{22} - a_{12} *  a_{21} = 4*1 - 1*3 = 1
\]$$

A matriz
      $$\[ \begin{bmatrix}
           a_{22} & -a_{12} \\ 
          -a_{21} &  a_{11}
       \end{bmatrix} \]$$
é chamada de matriz adjunta e é calculada a partir da matriz transposta dos cofatores de acordo com a formula:

$$\[A_{ij} = (-1)^{i+j}M_{ij}\]$$

Onde

 $$\[M_{ij}\]$$ é o chamado minor da matriz obtido a partir da matriz original eliminando a linha _i_ e coluna _j_, sendo:

 $$\[M_{11}\] = a_{22}$$

 $$\[M_{12}\] = a_{21}$$

 $$\[M_{21}\] = a_{12}$$

 $$\[M_{22}\] = a_{11}$$



sendo:

$$\[A_{11}\] = (-1)^{1+1}a_{22} = a_{22}\]$$

$$\[A_{12}\] = (-1)^{1+2}a_{21} = -a_{21}\]$$

$$\[A_{21}\] = (-1)^{2+1}a_{12} = -a_{12}\]$$

$$\[A_{22}\] = (-1)^{2+2}a_{11} = a_{11}\]$$

então a matriz adjunta ficaria:

$$\[ {\begin{bmatrix}
           a_{22} & -a_{21} \\ 
          -a_{12} &  a_{11}
       \end{bmatrix}}^T =   
{\begin{bmatrix}
           a_{22} & -a_{12} \\ 
          -a_{21} &  a_{11}
       \end{bmatrix}} =  \begin{bmatrix}
           1 & -1 \\ 
          -3 &  4
       \end{bmatrix} \]$$

Sendo assim a nossa matriz inversa ficaria:

$$\[
A^{-1}=\begin{bmatrix}
          4 & 1 \\ 
          3 & 1}
       \end{bmatrix}^{-1}
      =\frac{1}{1}
       \begin{bmatrix}
           1 & -1 \\ 
          -3 &  4
       \end{bmatrix} =        \begin{bmatrix}
           1 & -1 \\ 
          -3 &  4
       \end{bmatrix}.
\]$$

Para exemplificar, descriptografa-se a seguir o primeiro par de letras `[E, S]`:

$$\[
 \begin{bmatrix}
  77 & 24
 \end{bmatrix}
\] * \begin{bmatrix}
           1 & -1 \\ 
          -3 &  4
       \end{bmatrix} = \begin{bmatrix}
  77*1 - 24*3 & -77 + 4*24
 \end{bmatrix} = \begin{bmatrix}
  5 & 19
 \end{bmatrix}$$

Que correspondem as letras _E_ e _S_ na nossa tabela de correspondência:
<a href="https://ibb.co/rZ81S2b"><img src="https://i.ibb.co/Zh4kPzH/Captura-de-tela-de-2023-03-20-18-26-41.png" alt="Captura-de-tela-de-2023-03-20-18-26-41" border="0"></a>

## Anexo
### Cálculos de criptografia feitos a mão
<a href="https://ibb.co/g6LTH58"><img src="https://i.ibb.co/4JnT96L/criptografia-1.jpg" alt="criptografia-1" border="0"></a>
<a href="https://ibb.co/L627HdQ"><img src="https://i.ibb.co/92C5SHw/criptografia-2.jpg" alt="criptografia-2" border="0"></a>


