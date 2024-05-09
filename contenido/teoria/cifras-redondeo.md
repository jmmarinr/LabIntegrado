---
jupytext:
  text_representation:
    extension: .md
    format_name: myst
    format_version: 0.13
    jupytext_version: 1.14.0
kernelspec:
  display_name: Python 3 (ipykernel)
  language: python
  name: python3
---

:::{card} <span style="color:red"> Tomado de Notas de Física Experimental </span>
:link: https://srco.org.co/NotasFExp/docs/part1/cifras-significativas.html
:::

Tomado de [Notas de Física Experiemntal](https://srco.org.co/NotasFExp/intro.html) por Edgar Rueda.
# Cifras significativas y redondeo de cifras

La palabra "cifras" no debería generar ninguna duda en el contexto de este libro: dada una cantidad física cualquiera, las cifras de dicha cantidad corresponden al valor numérico de las unidades, decenas, centenas, miles, etc. Por ejemplo, sea la cantidad $1 \ 978$, se puede identificar que está compuesta de cuatro cifras, $8$ en las unidades, $7$ en las decenas, $9$ en las centenas, y $1$ en los miles. Por otro lado, la palabra "significativas" es muy posible que no se entienda, en un primer momento, en el contexto de este libro. Así que comenzaremos con un ejemplo: suponga que usted en el bolsillo tiene un billete de $\$50 \ 000$ pesos, uno de $\$2 \ 000$ pesos, una moneda de $\$100$ pesos, y una moneda de $\$50$ pesos, para un total de $\$52 \ 150$ pesos. Si un amigo le preguntara cuanto dinero tiene para ver si pueden ir a cine, muy probablemente usted le diga a su amigo que tiene $\$52 \ 000$ pesos, porque para poder pagar la boleta del cine los $\$150$ no aportan realmente nada, ni suman, ni restan, no son significativos, es decir, las cifras significativas son los $5$ diez miles, y los $2$ miles. Otro ejemplo, muy típico con el uso de calculadoras y computadoras, sería que le dijeran que debe dar $\$30 \ 000$ pesos para el total de $\$83 \ 000$ pesos que vale el ingreso de todos al cine. Usted por curiosidad decide calcular a que porcentaje equivale lo que debe de aportar y la calculadora le entrega el valor $36.144 \ 578 \ 31 \ \%$. Muy probablemente usted le informe a los demás que le ha tocado pagar el $36 \ \%$ del valor total, porque ninguno de los números decimales tiene alguna relevancia en este contexto, no son significativos.

+++

(subsec-cifras)=
## Cifras significativas

Se llamará **cifras significativas** a los números de una cantidad física que realmente tienen una relevancia (significado) en el contexto de la situación en la que se presenta. Para identificar el número de cifras significativas que tiene una cantidad física reportada se siguen las siguientes reglas:
1. Todos las cifras diferentes de cero son significativas: $1 \ 978$ tiene cuatro cifras significativas.
2. Todas las cifras iguales a cero que estén entre cifras diferentes de cero serán significativas: $1 \ 078$ tiene cuatro cifras significativas.
3. Todos las cifras iguales a cero que estén a la izquierda de la primer cifra diferente de cero NO son significativas: $0.019 \ 78$ y $0.010 \ 78$ tienen cuatro cifras significativas.
4. Todas las cifras iguales a cero, que sean decimales, y estén en el extremo derecho son significativas: $0.019 \ 0$ y $1.070$ tienen tres y cuatro cifras significativas, respectivamente.
5. Para indicar que una cantidad sin decimales con un cero en el extremo derecho es significativo se debe usar el punto decimal: $1 \ 970.$ tiene cuatro cifras significativas, mientras que $1 \ 970$ tiene tres cifras significativas.

Cuando existan dudas del número de cifras significativas la mejor opción es escribir la cantidad en notación científica, procurando que el único número no decimal sea diferente de cero. Para los ejemplos anteriores se tiene:
1. $1 \ 978 =1.978\times 10^{3}$.
2. $1 \ 078 = 1.078\times 10^{3}$.
3. $0.019 \ 78 = 1.978\times 10^{-2}$ $~~$ y $~~$  $0.010 \ 78 = 1.078\times 10^{-2}$.
4. $0.019 \ 0 = 1.90\times 10^{-2}$ $~~$ y $~~$  $1.070 = 1.070\times 10^{0}$.
5. $1 \ 970. = 1.970\times 10^{3}$ $~~$ y $~~$ $1.97\times 10^{3}$.

+++

(subsec-redondeo)=
## Redondeo

Recordando el porcentaje $36.144 \ 578 \ 31 \ \%$ calculado en la introducción de la {numref}`sec-cifras`, allí se tomó la decisión de solo presentar dos cifras significativas, es decir, que solo se reportarían las cifras hasta las unidades, $36 \ \%$. Es claro que al tomar la decisión de eliminar el resto de cifras se puede estar perdiendo información, y por lo tanto se debe tomar una decisión sobre aumentar o no la última cifra correspondiente a la unidad (en este caso el número $6$). Este proceso se conoce como redondeado y sigue las siguientes reglas:

1. La última cifra que se mantiene no se modifica si la siguiente cifra es menor que $5$: $36.144$ con dos cifras significativas queda $36$.
2. La última cifra que se mantiene se aumenta en una unidad si la siguiente cifra es mayor que $5$: $36.844$ con dos cifras significativas queda $37$.
3. La última cifra que se mantiene no se modifica si es par y la siguiente cifra es $5$: $36.544$ con dos cifras significativas queda $36$.
4. La última cifra que se mantiene se aumenta en una unidad si es impar y la siguiente cifra es $5$: $37.544$ con dos cifras significativas queda $38$.

```{note}
Si se considera el caso del redondeo como la decisión de aumentar o no en una unida una determinada cifra en virtud de la cifra que está a su derecha y que no será reportada, y recordando que solo se tienen dos opciones, sumar cero o sumar uno. Cuando la cifra que está a la derecha está entre $0$ y $4$ se puede decir que está más cerca del extremo inferior, por lo que se suma cero y la cifra que permanece no se modifica. Cuando la cifra que está a la derecha está entre $6$ y $9$ se puede decir que está más cerca del extremo superior, por lo que se suma uno y la cifra que permanece se modifica en una unidad. Por otro lado, cuando la cifra que está a la derecha es $5$ no es claro que hacer porque está a la misma distancia de ambos extremos. Si siempre se suma uno o siempre se suma cero, se puede estar generando un error sistemático en los datos a través de un sesgo (bias). Es por esto que se opta por sumar cero o uno dependiendo de si la cifra que permanece es par o impar. Así, se espera que la mitad de las veces sume uno y la otra mitad de las veces sume cero, tal que para una gran cantidad de datos el posible sesgo tienda a cero.
````

+++

(subsec-cifras-opera)=

## Operación con cantidades de diferente número de cifras significativas

Cuando se hacen operaciones con cantidades de diferente número de cifras significativas la regla general es que el resultado tendrá el mismo número de cifras significativas de la cantidad con menor número de cifras significativas. Por ejemplo, sean las cantidades $23$ y $40$ con dos y una cifra significativa respectivamente, la suma de dichas cantidades dará $63$, pero como $40$ es la cifra con menor número de cifras significativas, una en este caso, la respuesta será $60$. Esto porque al tener $40$ solo una cifra significativa no sabemos si realmente es $41$, $42$, o $39$, por ejemplo, que nos darían como resultado $64$, $65$, o $62$, respectivamente. Luego lo más correcto es mantener el menor número de cifras significativas, $60$, puesto que solo tenemos certeza de las $6$ decenas.

Por último, la recomendación es que se realicen todas las operaciones con todas las cifras disponibles y solo en el resultado se aplique la regla de la cifra con el menor número de cifras significativas.

```{warning}
Cuando se trabaje con cantidades que tienen incertidumbre será dicha incertidumbre la que defina el número de cifras significativas de la cantidad física.
````

