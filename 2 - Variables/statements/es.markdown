

# Variables #

La computadora utiliza *variables* para registrar el estado actual en cada paso de la ejecución de su programa.

#### ¿Dónde se Almacenan? ####

Las variables se almacenan en la memoria de las computadoras. El programador usa nombres simbólicos para describir las variables en sus mentes, por ejemplo: "la profundidad del agua en el río" o "la cantidad de dinero en la cuenta bancaria del cliente".

Por razones de eficiencia, se hace referencia a las ubicaciones en la memoria de la computadora mediante números a menudo representados en notación hexadecimal, por ejemplo: `0xaa10bb9c`. El compilador ayuda a los programadores a administrar la relación entre las representaciones simbólicas y numéricas de las ubicaciones de las variables. Con esto se reduce la cantidad de errores que los programadores seguramente cometerían, por ejemplo, si se les exigiera referirse a cada variable que tienen en mente únicamente por su ubicación actual en la memoria de su computadora.

C++ requiere que el programador use nombres construidos únicamente a partir de letras elegidas de la ''a'' a la ''z'', de la ''A'' a la ''Z'' y números elegidos de ''0'' a ''9''. C++ considera las letras mayúsculas diferentes a las minúsculas. Los nombres de variable deben comenzar con una letra, ya sea minúscula o mayúscula.

C++ permite por ejemplo `x`, `ejeX`, `nombre`, `cliente2`, etc. como nombres de variables. `crédito de cliente` no es un nombre válido porque contiene espacios, los cuales no son permitidos en nombres de variables.

### Cómo Declarar Variables ###

Las variables se declaran como __`tipo_de_variable`__` nombre_de_variable`.

Por ejemplo si quieres declarar un número entero:

    int miEntero;

### Cómo Asignarles Valores ###

¿De qué sirven las variables si no tienen valores? Para usar una variable simplemente tienes que declararla y asignarle un valor:

    int miEntero;
    miEntero = 10;


O puedes simplemente asignarle un valor al momento de declararla:

    int miEntero = 10;


## Tipos de Variables ##

### Booleano (`bool`) ###

El tipo `bool` es un tipo de dato de 1 byte que tiene sólo dos valores posibles `true` o `false` (verdadero o falso). Ejemplo:

    bool estaNublado = false;


### Enteros (`int` y `long long`) ###

Un entero es un número que no tiene decimales, por ejemplo `1`, `2`, `3` y `4` son números enteros. Por otro lado, `3.1416` y `9.81` no son enteros. Si intentaras guardar el valor `3.1416` en un entero, éste sería truncado y almacenado como `3` en la variable.

En C++ hay dos tipos **principales** de enteros:
* `int` que es capaz de almacenar enteros en el rango de `-2147483648` a `2147483647`. Utiliza 32 bits de memoria.
* `long long` que es capaz de almacenar enteros en el rango de `-9223372036854775808` a `9223372036854775807`. Utiliza 64 bits de memoria.

Ejemplos:

    int precioDeCoche = 87500;
    long long poblacionMundial = 7700000000;



### Letras (`char`) ###

Un `char` es una especie de entero que utiliza 8 bits de memoria. Puede almacenar valores enteros entre `0` y `255`. `char` es comúnmente utilizado para almacenar texto en formato [*ASCII*](https://es.wikipedia.org/wiki/ASCII). Un `char` se puede inicializar a partir de un carácter o de un valor entero, pero en ambos casos almacenará el valor ASCII. Por ejemplo:

    char miChar='A';
    char miOtroChar=65;


Ambos `char` que acabamos de inicializar tienen exactamente el mismo valor. El número `65` es el código ASCII para la letra "A".

ASCII es un sistema que asigna un valor numérico a cada letra. Para ver una tabla de conversión completa, visite [ascii-code.com](http://ascii-code.com/)


### Números con decimales (`float`) ###

Un `float` es un número de punto flotante, lo que significa que este número puede contener decimales. Esto nos permite almacenar números como `3.1416` y `9.81`:

    float pi;
    pi = 3.1416;


Los `float` tienen un tamaño fijo en la memoria. Esto significa que un `float` posiblemente no puede almacenar con precisión todos los valores decimales en el sistema de números reales. Si bien en muchos casos no importará, es importante tener en cuenta que el tipo de dato `float` generalmente almacena solo una buena *aproximación* de un valor decimal, no un valor exacto.

Cada `float` utiliza 32 bits de memoria.


### `double` ###

Un `double` es como un `float` porque también puede almacenar números decimales. Pero `double` puede almacenar más información que un `float`.


    double miDouble;
    miDouble = 8.78832998234793243274;

Como se señaló con el tipo de datos `float`, `double` sólo almacena una aproximación de valores decimales exactos, aunque generalmente, una aproximación de precisión más alta que la de `float`.

Cada `float` utiliza 64 bits de memoria.

### Limitar el Número de Decimales ###
Cuando llamamos a `cout` para imprimir un `float` o un `double` por default se imprimen a lo más 6 dígitos decimales del número. Podemos especificar el número de dígitos decimales que queremos que se impriman. Para hacerlo debemos de incluir la cabecera `#include <iomanip>` e imprimir la variable llamando

    cout << fixed << setprecision(2) << miDouble << endl;

Veamos el siguiente ejemplo donde se imprime un `double` con los decimales por default, con 2 decimales y con 10 decimales:

    #include <iostream>
    #include <iomanip>
    using namespace std;

    int main() {
            double miDouble = 1234567890.0 / 10000000000.0;

        cout << miDouble << endl;
        cout << fixed << setprecision(2) << miDouble << endl;
        cout << fixed << setprecision(10) << miDouble << endl;

        return 0;
    }
[¡Pruébalo en línea!](https://tio.run/##nY7LCsIwEEX3@YoBN7qwJvXVYu3KH4nJKAPNNDYJCOK316rgY@HGuzrc4QzXeD89GtP3I2LTJItQURtih9rV4rNzmsnXIgXiI7B2GLw2CCHajRDEEZwmHk/gImCIbdO@QXC0e8IWVD5fLFfropSZhBko@Uomhw93ybQpQlW9rYGRbbP5uh7ojPYOAaPv0FCglsf55F9TyR/qw@0wpo5hmHjt@5NQShRlVqob "C++ (gcc) – Try It Online")

## Ejercicios ##

Vamos a escribir un programa que lea primero una letra, luego un número `int` y finalmente un número `float`. El programa imprimirá los mismos datos que leyó pero en el orden inverso, es decir, primero el `float`, luego el `int` y finalmente la letra:


    #include <iostream>
    using namespace std;

    int main() {
        char miChar;
        int miEntero;
        float miFloat;

        cin >> miChar;
        cin >> miEntero;
        cin >> miFloat;

        cout << miFloat << endl;
        cout << miEntero << endl;
        cout << miChar << endl;

        return 0;
    }

[¡Pruébalo en línea!](https://tio.run/##dY27DsIwDEX3fIUlFhhAdKNK1QXBf0SpAUuNU/KYEN8emhTKQ8KLrXN8bT0M67PWKS2IdR87hIasDw6VaUX0xGdgZdAPSiP40EkhiAMYRbxcwU3AWPqiHBjaj00WUDbowAGdnciptyqzY@7jjRIjhrb9Cs7oMzvDZzizSdgYoGleJo/IXS9/5HTrn83P365IhyE6hq0U95SuoqrErt7U1QM "C++ (gcc) – Try It Online")

<sub>Este texto está basado al curso de [C++ de Wikiversity](https://en.wikiversity.org/wiki/C%2B%2B) y está disponinble bajo la licencia [Creative Commons Attribution-ShareAlike](https://creativecommons.org/licenses/by-sa/3.0/).</sub>
