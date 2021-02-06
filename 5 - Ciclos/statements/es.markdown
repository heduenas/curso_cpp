
# Ciclos #

Los ciclos le permiten al programador ejecutar el mismo bloque de código repetidamente. Haremos un uso intensivo de *declaraciones condicionales* (vistas en la sección anterior) en esta sección.

## El Ciclo `while` ##

La sintaxis es descrita a continuación:

    while (condicion) {
        // Este bloque de código se ejecuta repetidamente mientras condición sea true.
    }


Las declaraciones encerradas por las llaves `{`...`}` serán ejecutadas repetidamente hasta que la expresión `condicion` deje de ser igual a `true`.

El uso de las llaves `{`...`}` en ciclos `while` es esencial si se desea incluir más de un comando en el ciclo. Por ejemplo, si escribimos

    while (x == 4)
        y += x;
        x += 1;

sería equivalente a

    while (x == 4) {
        y += x;
    }
        x += 1;

Aquí habría un problema pues, aunque línea `x += 1;` está indentada, solo la primera línea (`y += x;`) corresponde al ciclo `while`. Este sería un gran problema porque la variable involucrada en la condición, `x`, no cambia, por lo que siempre se evaluará como `true`, convirtiendo a este en un *ciclo infinito*. Esto podría corregirse al contener todas las declaraciones destinadas a ser parte del cuerpo del ciclo en `{`...`}`:

    while ( x == 4 ) {
        y += x;
        x += 1;
    }


El ciclo `while` es en realidad el único tipo de ciclo necesario. El ciclo `for`, que viene a continuación, se puede reproducir usando un ciclo `while` y una declaración de variable. Con una negación simple `!`, `while` puede realizar el mismo comportamiento que un ciclo `do`-`while`.

## El Ciclo `do`-`while` ##
El ciclo `do`-`while` es casi idéntico al ciclo `while`, pero en lugar de evaluar la declaración condicional antes de que comience el ciclo, el ciclo `do`-`while` comprueba la declaración condicional al final de la primera ejecución, luego continúa con la siguiente iteración.

La sintaxis es descrita a continuación:

    do {
        // Este bloque de código se ejecuta repetidamente mientras condición sea true.
    } while (condicion);


Como puedes ver, el ciclo se va a ejecutar por lo menos una vez antes de evaluar la declaración condicional.

## El Ciclo `for` ##
El ciclo `for` es un ciclo que le permite al programador controlar exactamente cuántas veces va a iterar el ciclo.

La sintaxis es descrita a continuación:

    for (expresion_de_inicializacion; expresion_condicional; expresion_de_actualizacion) {
        // Este bloque de código se ejecuta repetidamente mientras expresion_condicional sea true.
    }

Como se puede observar, el ciclo `for` toma 3 parámetros:
* `expresion_de_inicializacion`. Es ejecutada una sola vez, esto sucede justo antes de empezar las repeticiones.
* `expresion_condicional`. Es evaluada una vez por repetición justo antes de comenzar la repetición. El ciclo se detiene a partir de que esta expresión toma valor `false`.
* `expresion_de_actualizacion`. Es evaluada una vez por repetición justo después de terminar la repetición.

A continuación un ejemplo de uso de ciclo `for`:

    for (int i = 0; i < 10; i++) {
        cout << i << endl;
    }

Este código imprime los números `0`, `1`, `2`, ..., `9`.

Es equivalente al siguiente código:

    int i = 0;
    while (i < 10) {
        cout << i << endl;
        i++;
    }

¿Qué hace este ciclo? Antes de la primera iteración, establece el valor de `i` en `0`. Luego, prueba (como un ciclo `while` normal) si `i` es menor que `10`. Si la instrucción devuelve `true`, el cuerpo del ciclo se ejecuta y el programa imprimirá el valor de `i`. Una vez finalizada la iteración, `i` se incrementa en 1, como se especifica en la declaración de actualización, y el condicional se prueba nuevamente.

Entonces, en el ejemplo anterior el ciclo se ejecuta 10 veces en total, e imprime `i` cada vez.

### Ciclos Anidados ###
También es posible *anidar* ciclos, o sea meter un ciclo dentro de otro ciclo. Por ejemplo, vamos a escribir un programa que escriba un triángulo de números como se muestra a continuación:

```
1
1 2
1 2 3
1 2 3 4
1 2 3 4 5
1 2 3 4 5 6
1 2 3 4 5 6 7
1 2 3 4 5 6 7 8
1 2 3 4 5 6 7 8 9
1 2 3 4 5 6 7 8 9 10
```
Veamos el código:

    #include <iostream>
    using namespace std;

    int main(){
        int tamanoDelTriangulo;
        cin >> tamanoDelTriangulo;

        for (int i = 1; i <= tamanoDelTriangulo; i++) {
        for (int j = 1; j <= i; j++) {
            cout << j;
            cout << " ";
        }
        cout << endl;
        }

        return 0;
    }

[Pruébalo en línea!](https://tio.run/##bU87DoMwDJ2TU1h0AaFKMBOYeoReIAopMiIOCsmEODsNIEoHPPjp/YanxvHZKbWuEO@BpIbQahBoJ@@0NA3f9DAhdUDS6GmUSsPk22o39ofkwUikNJt3fmpeGkn2pYe3Q0ldGGzFmUKCprn1OPtYB@lWRaihrCKI@i4KmOcZzJxdjf5o9FsDI54BpmzwIAT01T9LINn4wi9JUztEbeG/EU774AiKY@uyrmXxBQ "C++ (gcc) – Try It Online")

¿Qué hace este programa? Le solicita al usuario que elija un número entero, que se utiliza en la declaración condicional del primer ciclo `for`. Cada iteración del ciclo `i` hará que el ciclo `j` se ejecute, lo que hace una cuenta de `1` a `i` antes de permitir que el ciclo `i` continúe.

## Ciclos Infinitos ##

Un error de programación común es crear un *ciclo infinito*. Un ciclo infinito se refiere a un ciclo que, bajo cierta entrada válida (o al menos plausible), nunca se dejará de repetir.

Procura tener cuidado de examinar todas las entradas posibles en un ciclo para asegurarte de que para cada conjunto de entradas de este tipo, haya una *condición de salida* que eventualmente se alcanzará. Además de evitar que el programa se cicle (es decir, que nunca termine), el entendimiento de todas las posibles entradas y condiciones de salida demuestra una sólida comprensión del algoritmo que se está escribiendo.

Los compiladores, depuradores y otras herramientas de programación a veces pueden ayudar al programador a detectar ciclos infinitos. Pero en general, no es posible detectar automáticamente un ciclo infinito. Esto se conoce como [Problema de la detención](https://es.wikipedia.org/wiki/Problema_de_la_parada). Si bien el problema de detención no se puede resolver en el caso general, es posible determinar si un ciclo se detendrá en algunos casos específicos.

### Ejemplo de Ciclo Infinito ###

    #include <iostream>
    using namespace std;

    int main() {
      while(1) {
         cout << "Ciclo infinito" << endl;
      }
      return 0;
    }

[Pruébalo en línea!](https://tio.run/##JYoxCgMhEEV7TzFsmk0RyNZKmpxExslmQEfRkRRhz24M@@EV7/GxlNuOOMaFBWMPBI5z00o@PUxvLDuIT9SKR4KmwRrDopA8y3qFrwH4vDnSup0yh7krOAfLkzFmYHmxsObl30hCtPN2TCpprwJ3a44xfg "C++ (gcc)")

Este código imprimirá "Ciclo infinito" sin parar.


## Ejercicios ##

#### Imprimir números cuadrados ####

Vamos a imprimir sólo los números cuadrados entre `1` y `100`.


    #include <iostream>
    using namespace std;

    int main() {
        for (int i = 1; i * i <= 100; i++) {
            cout << i * i << endl;
        }

        return 0;
    }

[Pruébalo en línea!](https://tio.run/##NU1JCsMwDLz7FYJekoaW9Gy3fzGKGgSJbLycSt7uyoEMjKRZQBjjY0Vs7caCW10IHIdcEvn9Y2pmWUH8Tjl6JMhlscawFNg9yzDCz4DiGxIM3WV4w8vquiud3vOsapquYgeGWsC5q@SAZNnsGR/nRJbnSmUY9VXXiUpNArM1R2t/ "C++ (gcc)")

#### Imprimir números pares ####

Vamos a imprimir sólo los números pares entre `0` y `100`.


    #include <iostream>
    using namespace std;

    int main() {
        for (int i = 0; i <= 100; i += 2) {
            cout << i << endl;
        }

        return 0;
    }

[Pruébalo en línea!](https://tio.run/##NY1LCsMwDETX9SkGukkoLWm3cXoXo6hGkCjBn1XJ2V3HUC00o@Exon2/e6JSrqK05JlhZYspsFvfJkdRD3Urx90RI6Z5NEY0YXWiXY@vQZ3PFtCdqWDCMFaxE55Dc7cJrz93oS0nWHsCFqzzMrb8aJtEH55T19cX5x045aC1zxyl/AA "C++ (gcc)")

#### Pedir un número par al usuario ####

Vamos a pedir un número al usuario y si es impar lo vamos a volver a pedir hasta nos de uno que se par.

    #include <iostream>
    using namespace std;

    int main() {
        int numeroDelUsuario;
        do {
            cin >> numeroDelUsuario;
        } while (numeroDelUsuario % 2 != 0);

        cout << numeroDelUsuario << endl;

        return 0;
    }

[Pruébalo en línea!](https://tio.run/##fY9NCsIwEIX3OcWICO1CaNSNtHblFTxASIYaSCclP7iQnj2airUo@BbD8L03D0YOw7aTMiV4aq1JmqgQGm19cCj6lmUevaYOSPToByERfFD1ZExDU4BeaCpKuE/gDSn26OwZzcVH4bStZ1fZRTRLaoK2/XMxwu2qDULxHYEN7GB1gqr8hOdF2higaX56M0NSZvFFlsMQHUH1wmNKnO0Z5@zI2eEB "C++ (gcc) – Try It Online")

<sub>Este texto está basado al curso de [C++ de Wikiversity](https://en.wikiversity.org/wiki/C%2B%2B) y está disponinble bajo la licencia [Creative Commons Attribution-ShareAlike](https://creativecommons.org/licenses/by-sa/3.0/).</sub>
