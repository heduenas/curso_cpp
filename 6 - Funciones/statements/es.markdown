
# Funciones #

Esta lección tratará sobre el uso de funciones y recursividad para mejorar la legibilidad y la eficiencia de tu código.

En pocas palabras, una función es un segmento de código que está aislado del segmento de código principal. Una función se *llama* desde una sección de código, la función `main`, otra función, o la misma función. Cuando se ha terminado de ejecutar el código de la función, se *regresa* al código que hizo la llamada a la función. La forma general de una función es:


    tipo_de_dato nombre_de_la_funcion(tipo_argumento1 argumento1, tipo_argumento2 argumento2, ...) {
        // Bloque de código de la función.
    }


A continuación un ejemplo concreto de una función:


    int suma(int arg1, int arg2) {
       int sum = arg1 + arg2;
       return sum;
    }


Explicación parte por parte de la función `suma`.
* El `int` al inicio es el *tipo de retorno* de la función.
* `suma` es el nombre o *identificador* de la función. Será usado para llamar a la función.
* `int arg1` e `int arg2` son los llamados *parámetros* de la función. Son definidos con el formato `tipo_de_dato identificador`. Se explicará más sobre ellos después.
* El código de la función está encerrado en llaves `{`...`}`.
* Toda función debe de tener un comando `return` (excepto si el tipo de retorno es `void`). El valor especificado junto a `return` (`sum` en nuestro ejemplo) será enviado de regreso al código que llamó a la función.

#### Cómo Llamar a las Funciones ####
Para poder llamar a una función, ésta debe de estar declarada en cualquier línea anterior a la línea que la llama. Por ejemplo:


    #include <iostream>
    using namespace std;

    void funcion1() {
       cout << "Esta es la función 1!" << endl;
    }

    int funcionSuma(int num1, int num2) {
       return num1 + num2;
    }

    int main() {
       int suma;

       funcion1();
       suma = funcionSuma(2,3);
       cout << suma << endl;

       return 0;
    }

[Pruébalo en línea!](https://tio.run/##bU9BDsIgELz7irVeaqyJrcdWb77AFxDAhqQsTQEvxlf5BB@GhRbbGvcAy8xkmKFtu68pdQ762QikjWUcKqG06TiR55XHrRZYAxLJdUsoB21YGYhw3JVgcLNIhcI83cIjoP1QZQ1UFSQXbQhwDQ0ZdO8XQr5OPMeRNYPXc3IUaKLh1UqS@jdamWcwbsXsl44b22HgYRfIv36SCJyH85juzcsIxHtq8qW8Dk6LSEV2nPhYNOgWpX5CHsZozn0A "C++ (gcc) – Try It Online")

Observa como las funciones `funcion1` y `funcionSuma` preceden la declaración de `main`. Esto es lo que permite que dichas funciones puedan ser utilizadas desde `main`.

Ahora, nota que para llamar a `funcion1`, todo lo que tuvimos que escribir fue `funcion1();`. Como no requiere de ningún parámetro y su tipo de retorno es `void`, es suficiente llamarlo así. Por otro lado, en la función `suma`, vemos que ésta requiere de dos parámetros y su tipo de retorno es `int`. Para pasarle datos al a función, simplemente listamos los datos en el orden descrito por la definición de la función. Para capturar el valor retornado por la función, utilizamos el operador de asignación `=` y asignamos el valor retornado a una variable `sum`.

También vale la pena notar que, las funciones con tipo de retorno `void` (como `funcion1` por ejemplo), no requieren del uso del comando `return` porque no retornan nada.

#### Parámetros ####

Los *parámetros* son usados para pasar datos entre funciones. Arriba aprendimos que se deben de enumerar los datos que se desea pasar a una función en la llamada entre `(` y `)`. El orden en el cual se deben de pasar los parámetros está determinado por la definición de la función. El primer parámetro se asignará a la primera variable listada en la definición de la función, el segundo parámetro se asignará a la segunda variable, etc. Además, la lista de parámetros debe tener el número correcto de parámetros y el tipo de datos especificado en la definición de función, de lo contrario el programa no compilará.

Por ejemplo, consideremos la siguiente función:

    double multiplicacion(long long x, float y, int z) {
       return x * y * z;
    }


Para llamar a esta función se **tiene** que pasar exactamente 3 parámetros:
* El primer parámetro tiene que ser un `long long`.
* El segundo parámetro tiene que ser un `float`.
* El tercer parámetro tiene que ser un `int`.

Por ejemplo, `multiplicacion(4114, 2.0f, 2)` es una forma correcta de llamar a la función. Por otro lado `mutliplicacion(4114.0f, 2.0f, 2.0f)` es una forma incorrecta ya que se están pasando 3 valores de tipo `float`.

## Recursión ##
Una función también puede hacer llamadas a otras funciones, o incluso a sí misma. Cuando una función se llama a sí misma llamamos a esto una llamada *recursiva*. Vemos un ejemplo de una función *recursiva*:


    int factorial(int n) {
       if(n <= 1) {
          return 1;
       } else {
          return (n * factorial(n - 1));
       }
    }


Esta es una aplicación clásica de recursión. Esta función calcula el [factorial](https://es.wikipedia.org/wiki/Factorial) de un número. El factorial de `n`, escrito `n!`, es el producto de cada número del `1` al `n`. Por ejemplo `4! = 4 × 3 × 2 × 1 = 24`. Veamos qué sucede en nuestra función cuando llamamos a `num = factorial (4)`.

* `factorial(4)` es llamado.
* Como `n == 4`, nos vamos al `else` de la función `factorial`. Entonces retornamos `4 * factorial(3)`.
  * `factorial(3)` es llamado.
  * Como `n == 3`, nos vamos al `else` de la función `factorial`. Entonces retornamos `3 * factorial(2)`.
    * `factorial(2)` es llamado.
    * Como `n == 2`, nos vamos al `else` de la función `factorial`. Entonces retornamos `2 * factorial(1)`.
      * Como `n == 1`, entramos al `if` de la función `factorial`. Entonces retornamos `1` a la llamada anterior.
    * `factorial(1)` retorna `1`, entonces `factorial(2)` retorna `2 * 1`.
  * `factorial(2)` retorna `2`, entonces `factorial(3)` retorna `3 * 2`.
* `factorial(3)` retorna `6`, entonces `factorial(4)` retorna `4 * 6`.

Muchas veces, una solución recursiva para un problema es un programa muy simple. La desventaja es que las soluciones recursivas generalmente tienen un costo extra de tiempo de ejecución y memoria utilizada. Cada vez que se llama a una función, está es colocada en memoria. Como no nos salimos de la función `factorial` hasta que `n` alcanza `1`, `n` funciones permanecerán en memoria. Esto no es un problema para casos pequeños como `factorial(4)`, pero para casos más grandes puede implicar un gasto grande de memoria.

## Ejercicios ##

#### Elevar un número a una potencia ####

Vamos a pedir un número y una potencia al usuario y vamos a calcular el valor del número elevado a la potencia dada:

    #include <iostream>
    using namespace std;

    long long elevar(long long base, int potencia) {
       long long respuesta = 1;
        for (int i = 0; i < potencia; i ++) {
          respuesta *= base;
        }
        return respuesta;
    }

    int main() {
        long long numero;
        int potencia;

        cin >> numero;
        cin >> potencia;

        cout << elevar(numero, potencia) << endl;

        return 0;
    }

[Pruébalo en línea!](https://tio.run/##fVFJDsIwDLz3FZa4FCgScELq8peQmipS61RZuCDeXpKwOAiJHJxkxjOOHTnPu0HKZYGwVork6HuERmnrDIqpKyLuraIBSExoZyERrOvrRKQw6kCmgCNehSkZOAuLFShyMGuHJJVYwy2JvnQm@Hq0TkALh/rNw0UbKKNYBXxfh635@MTbdpu5hcU2mzaVZqt7wUnOG@LcZ86d24kFJ6GozM35reQnNJqd8@YY/RykIui6H9UL/ifU3kHTvGf6NKiyOUaO@jH7iKy9/autZTnC6QE "C++ (gcc) – Try It Online")

#### Sucesión de Fibonacci ####

Vamos a escribir una función recursiva que calcule e imprima los primeros 30 elementos de la [sucesión de Fibonacci](https://es.wikipedia.org/wiki/Sucesi%C3%B3n_de_Fibonacci). Cada elemento de la sucesión de Fibonacci es calculado como la suma de los dos elementos inmediatos anteriores a él, y los primeros dos elementos de la sucesión se definen iguales a 1. Los primeros elementos de Fibonacci son 0, 1, 1, 2, 3, 5, 8, 13, 21, 34, ...

    #include <iostream>
    using namespace std;

    long long fibonacci(int indice) {
       long long respuesta;
       if (indice <= 1) {
          respuesta = 1;
        } else {
          respuesta = fibonacci(indice - 1) + fibonacci(indice - 2);
        }
        return respuesta;
    }

    int main() {
        for (int i = 1; i < 30; i ++) {
           cout << fibonacci(i) << " ";
        }

        return 0;
    }

[Pruébalo en línea!](https://tio.run/##bY9JDoMwDEXX5BRWuwEhpA5L0t4lNQZZggRlWFWcnSbpxIIsbPnrxf8b57kZENf1yBrH0BFINs5bUtNdBMd6AK0mcrNCAue7VojRRDGXnh9GK0QuWXtg3TFSBU9R/BEbvwZyXrWi4B7KNwTyBudEQnzFj4GotllbgEZHe8DWM69q0qZ6T79Un2W5WvLB6m2gRYiUe1Ksy2@Y3lh4X5PDxCbhekq9rvNpCUITPEi59azSfIDD13FreYpW6/oC "C++ (gcc)")

<sub>Este texto está basado al curso de [C++ de Wikiversity](https://en.wikiversity.org/wiki/C%2B%2B) y está disponinble bajo la licencia [Creative Commons Attribution-ShareAlike](https://creativecommons.org/licenses/by-sa/3.0/).</sub>
