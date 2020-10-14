## Introducción

Este manual describe al lenguaje Mini.

  

## Convenciones léxicas

Un programa consiste en una unidad de traducción almancenada en un archivo.

  

### Componentes léxicos (tokens)

Existen varios componentes léxicos: identificadores, palabras reservadas, constantes y operadores. Los espacios, tabuladores, nueva linea, y comentarios, como se describen adelante (en su conjunto llamados "espacios en blanco") son ignorados, excepto los que separan componentes. Se requiere de algún espacio en blanco para separar identificadores de otra manera adyacentes, palabras reservadas, y constantes.

  

### Comentarios

Los caracteres **##** inician un comentario y terminan con nueva línea. Los comentarios serán posteriormentes eliminados por el escaner.

### Identificadores

Un identificador es una secuencia de letras y dígitos. El primer caracter debe ser una letra (minúscula o mayúscula, no importa) y luego pueden seguir con letras o dígitos decimales.

  

*identificador*:

  

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*letra*

  

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*identificador letra*

  

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*identificador digito*

  



### Palabras reservadas

Los siguientes identificadores son palabras reservadas y no se pueden utilizar de otra manera.

  

*palabra-reservada*: uno de

  

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**programa &nbsp; &nbsp;&nbsp; declarar &nbsp; &nbsp;&nbsp; fin-prog**

  

### Constantes

Hay una sola clase de consantes, y esta es la constante entera.

  

*constante*:

  

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*constante-entera*

  

Una constante entera es una secuencia de dígitos.

  

*constante-entera*:

  

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*digito*

  

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*constante-entera digito*


### Operadores

Operadores de multiplicación, división, suma, resta y asignación.

*operador*: uno de

  

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\*&nbsp; &nbsp;&nbsp; /&nbsp; &nbsp;&nbsp; +&nbsp; &nbsp;&nbsp; -**



*operador-asignacion*: uno de

  

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**<-**


### Caracteres Puntuacion

*caracter-puntuacion*: uno de

  

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**;&nbsp; &nbsp;&nbsp; ,&nbsp; &nbsp;&nbsp; (&nbsp; &nbsp;&nbsp; )**


### Otros

*letra*: uno de

  

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**a b c d e f g h i j k l m n o p q r s t u v w x y z**

  

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**A B C D E F G H I J K L M N O P Q R S T U V W X Y Z**

  

*digito*: uno de

  

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**0 1 2 3 4 5 6 7 8 9**

  



## Expresiones

  

### Expresiones primarias

Las expresiones primarias son identificadores, constantes o expresiones entre paréntesis.

  

*expresion-primaria*:

  

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*identificador*

  

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*constante*

  

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**(**  *expresion-aditiva*  **)**

  

### Expresiones unarias

Las expresiones con operadores unarios se agrupan de derecha a izquierda.

  

*expresion-unaria*:

  

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*expresion-primaria*

  

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*operador-unario expresion-unaria*

  

*operador-unario*: uno de

  

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**-**

  

El operador unario **-** invierte el signo del operando que esté a su derecha.

  

### Expresiones multiplicativas

Los operadores multiplicativos **\*** y **/** se agrupan de izquierda a derecha.

  

*expresion-multiplicativa*:

  

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*expresion-unaria*

  

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*expresion-multiplicativa **\*** expresion-unaria*

  

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*expresion-multiplicativa **/** expresion-unaria*

  

El operador binario **\*** denota multiplicación.

  

El operador binario **/** produce el cociente.

  
  

### Expresiones aditivas

Los operadores aditivos **+** y **-** se agrupan de izquierda a derecha.

  

*expresion-aditiva*:

  

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*expresion-multiplicativa*

  

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*expresion-aditiva **+** expresion-multiplicativa*

  

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*expresion-aditiva **-** expresion-multiplicativa*

  

El resultado del operador **+** es la suma de los operandos.

  

El resultado del operador **-** es la resta de los operandos.