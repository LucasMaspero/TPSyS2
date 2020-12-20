## Introducción

Este manual describe al lenguaje mini.

  

## Convenciones léxicas

Un programa consiste en una unidad de traducción almancenada en un archivo.

  

### Componentes léxicos (tokens)

Existen varios componentes léxicos: palabras reservadas, identificadores, constantes, operadores, operador de asignacion y caracteres de puntuación. Los espacios, tabuladores, nueva linea, y comentarios, como se describen adelante (en su conjunto llamados "espacios en blanco") son ignorados, excepto los que separan componentes. Se requiere de algún espacio en blanco para separar identificadores de otra manera adyacentes, palabras reservadas, y constantes.

En conclusión, se define token formalmente de la siguiente manera:

  
<br />
*token*: uno de

  

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**palabra-reservada &nbsp; &nbsp;&nbsp; identificador &nbsp; &nbsp;&nbsp; constante &nbsp; &nbsp;&nbsp; operador &nbsp; &nbsp;&nbsp; operador-asignacion &nbsp; &nbsp;&nbsp; caracter-puntuacion**

  


<br />
### Palabras reservadas

Los siguientes identificadores son palabras reservadas y no se pueden utilizar de otra manera.

  
<br />
*palabra-reservada*: uno de

  

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**programa &nbsp; &nbsp;&nbsp; declarar &nbsp; &nbsp;&nbsp; leer &nbsp; &nbsp;&nbsp; escribir &nbsp; &nbsp;&nbsp; fin-prog**

  


<br />
### Identificadores

Un identificador es una secuencia de letras y dígitos. El primer caracter debe ser una letra (minúscula o mayúscula, no importa) y luego pueden seguir con letras o dígitos decimales.

  
<br />
*identificador*:

  

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*letra*

  

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*identificador letra*

  

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*identificador digito*

  


<br />
### Constantes

Hay una sola clase de consantes, y esta es la constante entera.

  
<br />
*constante*:

  

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*constante-entera*

  

Una constante entera es una secuencia de dígitos.

  
<br />
*constante-entera*:

  

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*digito*

  

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*constante-entera digito*

<br />
### Operadores

Operadores de multiplicación, división, suma, resta.

<br />
*operador*: uno de

  

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\*&nbsp; &nbsp;&nbsp; /&nbsp; &nbsp;&nbsp; +&nbsp; &nbsp;&nbsp; -**

<br />
<br />
### Operador de Asignacion

*operador-asignacion*: uno de

  

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**<-**

<br />
### Caracteres Puntuacion

*caracter-puntuacion*: uno de

  

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**;&nbsp; &nbsp;&nbsp; ,&nbsp; &nbsp;&nbsp; (&nbsp; &nbsp;&nbsp; )**

<br />
### Otros

*letra*: uno de

  

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**a b c d e f g h i j k l m n o p q r s t u v w x y z**

  

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**A B C D E F G H I J K L M N O P Q R S T U V W X Y Z**

  
<br />
*digito*: uno de

  

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**0 1 2 3 4 5 6 7 8 9**

  

<br />
### Comentarios

Los caracteres **##** inician un comentario y terminan con nueva línea. Los comentarios serán posteriormentes eliminados por el escaner.


<br />
## Programa

Un programa correcto en lenguaje mini comienza con la palabra reservada **programa** y termina con la palabra reservada **fin-prog**. En medio debe haber una lista, eventualmente vacía de sentencias.


  
<br />
*programa*:

  

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**programa** **fin-prog**



&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**programa** *lista-sentencias* **fin-prog**

  
<br />
*lista-sentencias*:

  

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*sentencia*



&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*lista-sentencias* *sentencia*

<br />
## Sentencias

Consideraremos que las declaraciones son un tipo de sentencia. Todas las sentencias y declaraciones finalizan con **;**. La declaración comienza con la palabra reservada **declarar** seguida del identificador y finaliza con **;**. Las variables son todas, implícitamente, enteras. Además de la declaración, tenemos tres tipos de sentencias mas: **leer**, **escribir** y asignación cuyo símbolo es **<-**.

<br />
*sentencia*:



&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**declarar** *identificador* **;**



&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**leer** **(** *lista-identificadores* **)** **;**



&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**escribir** **(** *lista-expresiones* **)** **;**



&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*identificador* **<-** *expresion* **;**


<br />
*lista-identificadores*



&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*identificador*



&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*lista-identificadores* **,** *identificador*


<br />
<br />
<br />
<br />
*lista-expresiones*



&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*expresion*



&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*lista-expresiones* **,** *expresion*

<br />
## Expresiones

### Expresion

Una expresion es un termino o bien una expresion "combinada" con un termino utilizando algun operador de suma **+** o resta **-**.

<br />

*expresion*:

  

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*termino*

  

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*expresion* **+** *termino*

  

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*expresion* **-** *termino*


<br />
<br />
El resultado del operador **+** es la suma de los operandos.

  

El resultado del operador **-** es la resta de los operandos.


<br />
### Termino

Un termino es un valor o bien un termino "combinado" con un valor utilizando algun operador de multiplicacion **\*** o division **/**.

<br />

*termino*:

  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*valor*

  

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*termino* **\*** *valor*

  

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*termino* **/** *valor*

<br />
<br />
El operador binario **\*** denota multiplicación.

  

El operador binario **/** produce el cociente.

<br />
### Valor

Un valor puede ser un identificador, una constante, una expresion encerrada entre parentesis o bien un operador unario **-** seguido de un valor.

<br />

*valor*:

  

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*identificador*

  

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*constante*

  

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**(** *expresion* **)**

  

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**-** *valor*
  
<br />
<br />

El operador unario **-** invierte el signo del operando que esté a su derecha.