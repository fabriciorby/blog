---
layout: post
title:  "A Criptografia Clássica"
date:   2018-02-24 00:51:13 +0800
categories: curiosidades
tags: criptografia
---

# Criptografia Clássica

A origem da palavra criptografia vem do grego, _kryptós_ (escondido) e _gráphein_ (escrita).

Apesar de ser muito utilizada nos dias de hoje na área de tecnologia, sua origem é antiga e estima-se que deu-se início há 4500 anos atrás, em hieróglifos esculpitos no Antigo Egito.

Com o desenvolvimento da criptografia, houve também o desenvolvimento da _criptoanálise_, que é o estudo que procura decifrar códigos gerados a partir de técnicas de criptografia.

Da fusão da criptografia com a criptoanálise forma-se a _criptologia_.

As cifras clássicas podem ser divididas em técnicas de:
* Substituição
  * Monoalfabética
  * Polialfabética
* Transposição

Finalmente, o assunto aqui não será um grande estudo sobre a criptologia em si, mas sim, apresentar de forma clara e sucinta as principais formas de criptografia clássica.

## Técnica de Substituição

É uma técnica que consiste em trocar as letras de uma mensagem por outra.

### Monoalfabética

É a forma mais básica de criptografia.

A encriptação simplesmente consiste em utilizar uma tabela com símbolos e substituir cada letra da mensagem por seu símbolo correspondente.

#### A Cifra de César

O mais famigerado exemplo de cifra de substituição é a cifra de César.

Segue abaixo a tabela de associação, onde o alfabeto é rotacionado à esquerda de três posições, neste caso, _três_ é a _chave_:

A | B | C | D | E | F | G | H | I | J | K | L | M | N | O | P | Q | R | S | T | U | V | W | X | Y | Z 
- | - | - | - | - | - | - | - | - | - | - | - | - | - | - | - | - | - | - | - | - | - | - | - | - | - 
D | E | F | G | H | I | J | K | L | M | N | O | P | Q | R | S | T | U | V | W | X | Y | Z | A | B | C |

Ao substituirmos as letras a partir da _chave_ obtemos a versão encriptada da mensagem, e se quisermos decriptar é só fazermos o processo inverso.

```
Chave:      3
Normal:     A LIGEIRA RAPOSA MARROM SALTOU SOBRE O CACHORRO CANSADO
Encriptado: D OLJHLUD UDSRVD PDUURP VDOWRX VREUH R FDFKRUUR FDQVDGR
```

### Polialfabética

### Cifra de Vigenère

A cifra de Vigenère nada mais é do que 26 cifras de César, com base em uma sequência de letras pré-definidas que forma uma chave.

```
  | A B C D E F G H I J K L M N O P Q R S T U V W X Y Z
  | - - - - - - - - - - - - - - - - - - - - - - - - - -
A | a b c d e f g h i j k l m n o p q r s t u v w x y z
B | b c d e f g h i j k l m n o p q r s t u v w x y z a
C | c d e f g h i j k l m n o p q r s t u v w x y z a b
D | d e f g h i j k l m n o p q r s t u v w x y z a b c
E | e f g h i j k l m n o p q r s t u v w x y z a b c d
F | f g h i j k l m n o p q r s t u v w x y z a b c d e
G | g h i j k l m n o p q r s t u v w x y z a b c d e f
H | h i j k l m n o p q r s t u v w x y z a b c d e f g
I | i j k l m n o p q r s t u v w x y z a b c d e f g h
J | j k l m n o p q r s t u v w x y z a b c d e f g h i
K | k l m n o p q r s t u v w x y z a b c d e f g h i j
L | l m n o p q r s t u v w x y z a b c d e f g h i j k
M | m n o p q r s t u v w x y z a b c d e f g h i j k l
N | n o p q r s t u v w x y z a b c d e f g h i j k l m
O | o p q r s t u v w x y z a b c d e f g h i j k l m n
P | p q r s t u v w x y z a b c d e f g h i j k l m n o
Q | q r s t u v w x y z a b c d e f g h i j k l m n o p
R | r s t u v w x y z a b c d e f g h i j k l m n o p q
S | s t u v w x y z a b c d e f g h i j k l m n o p q r
T | t u v w x y z a b c d e f g h i j k l m n o p q r s
U | u v w x y z a b c d e f g h i j k l m n o p q r s t
V | v w x y z a b c d e f g h i j k l m n o p q r s t u
W | w x y z a b c d e f g h i j k l m n o p q r s t u v
X | x y z a b c d e f g h i j k l m n o p q r s t u v w
Y | y z a b c d e f g h i j k l m n o p q r s t u v w x
Z | z a b c d e f g h i j k l m n o p q r s t u v w x y

Texto:	        ATACAR BAS ESUL
Chave:	        LIMAOL IMA OLIM
Texto cifrado:	LBMCOC JMS SDCX
```

Para cada letra do texto, se deve procurar na tabela a letra correspondente da chave.

No caso, a chave é LIMAO, que se repete até quando necessário para que se cifre o texto.

Podemos ver na tabela, ao buscar o 'A' do texto em relação ao 'L' da chave, obtemos 'L'. E assim sucessivamente.

## Técnica de Transposição

É uma técnica que consiste em trocar os caracteres da mensagem de lugar.

### Cifra das Colunas

A cifra das colunas é bastante rudimentar, tudo que precisamos é de uma mensagem a ser decifrada e uma chave, que é o número de linhas que a matriz terá.

```
F A O S M D C E O P
U M D F O E O R S D
J T O O S S B T X Q

Chave: 3
Texto: FUJAM TODOS FOMOS DESCOBERTOS
Cifra: FAOSMDCEOP UMDFOEORSD JTOOSSBTXQ
```
Sabendo a chave, é só dividir a cifra recebida pela quantidade correta de linhas, e então poderemos ver a mensagem escrita lendo-a através das colunas.

Note que podem haver caracteres aleatórios para preencher espaço após o final da mensagem.

### Transposição de Colunas

```
L I M A O
- - - - -
F U J A M
T O D O S
F O M O S
D E S C O
B E R T O
S J Q L A

Chave: LIMAO
Texto: FUJAM TODOS FOMOS DESCOBERTOS
Cifra: AOOCTL UOOEEJ FTFDBS JDMSRQ MSSOOA
```
A cifra é enviada na ordem alfabética a partir da chave. Para conseguir desencriptar a mensagem, é necessário reescrevê-la em forma de colunas na ordem correta.

Se a chave for LIMAO, dividimos a quantidade de caracteres recebidos pelo número de caracteres da chave, que no caso é 5, e então as ordenamos.

Sabendo que nos foi enviado na ordem alfabética AILMO, basta ordenar as colunas na ordem LIMAO que a mensagem estará revelada.

Note que podem haver caracteres aleatórios para preencher espaço após o final da mensagem.

### Observação

Se utilizadas isoladamente, as cifras de transposição apresentam as mesmas vulnerabilidades das cifras de substituição. Entretanto, quando usadas em conjunto, podem gerar uma cifra fortalecida, e que croptoanalistas não quebrariam tão facilmente.

