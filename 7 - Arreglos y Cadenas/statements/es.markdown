
# Arreglos y Cadenas #

## Arreglos ##
Hasta ahora hemos usado variables para almacenar valores en memoria. Ahora explicaremos un medio para almacenar *multiples* valores juntos en una sola unidad, el *arreglo*.

Un arreglo es una secuencia de tamaño fijo de elementos del mismo tipo almacenados en un pedazo secuencial de memoria. Entonces, un *arreglo de enteros* almacena un número de valores de tipo `int`, un *arreglo de carácteres* almacena un número de valores de tipo `char`, etc. Nos referimos al tamaño del arreglo como su *dimensión*. Para declarar un arreglo en C++, escribimos lo siguiente:

`tipo_de_dato `**`nombreDelArreglo`**`[dimension];`

Por ejemplo, para declarar un arreglo de 4 enteros llamado `arr`, escribimos

`int `**`arr`**`[4];`

Los elementos del arreglo pueden ser accedidos usando un *índice*. En C++ los índices de los arreglos comienzan en 0, o sea que el primer elemento del arreglo tiene índice 0. Entonces, para acceder al tercer elemento del arreglo `arr`, tenemos que escribir `arr[2];` El valor retornado por esa expresión puede ser utilizado de la misma manera que cualquier otro `int`.

### Inicialización de Arreglos ##
Igual que con las variables normales, los elementos del arreglo deben de ser inicializados antes de que puedan ser usados; de lo contrario, muy probablemente tendremos resultados inesperados en nuestro programa. Hay múltiples formas de inicializar un arreglo. Una forma es declarar el arreglo y luego inicializar algunos o todos sus elementos:


    int arr[4];

    arr[0] = 6;
    arr[1] = 0;
    arr[2] = 9;
    arr[3] = 6;


Otra forma es inicializar algunos o todos sus elementos al momento de declararlo:

    int arr[4] = {6, 0, 9, 6};

Algunas veces es más conveniente omitir el tamaño del arreglo y dejar que el compilador determine el tamaño por nosotros, basado en cuántos elementos le damos:

    int arr[] = {6, 0, 9, 6, 2, 0, 1, 1};

En este caso, el compilador creará un arreglo de enteros de dimensión 8.

El arreglo también puede ser inicializado con valores que no se conocen de antemano. Por ejemplo, vamos a leer 4 números y luego a escribirlos:

    #include<iostream>
    using namespace std;

    int main() {
        int arr[4];

        for (int i = 0; i < 4; i++) {
            cin >> arr[i];
        }

        for (int i = 0; i < 4; i++) {
            cout << " " << arr[i];
        }
        cout << endl;
    }
[¡Pruebalo en línea!](https://tio.run/##pYzBCsIwEETvfsWgl0oRqlQQGvsj4iGksSy025CkJ@m3xzTS0osnd2FnmRmeMubUKhUC4hyIVTc2WtDgvNWyr3ezPTriFix77YxUGs43VQrSIfboJXF2xDsZiymtfZTPavXW5zVYZHODcEdRRREoo@T5FjGPIkZdJxJtSNNfzGH0EAL7uFF@s5ei5qb75lMIF9xwxrUoPg "C++ (gcc) – Try It Online")

### Accesando los Elementos de un Arreglo ###
Para acceder a los elementos de un arreglo se deben de proveer un *índice*, que debe de ser un entero en el rango de 0 a n-1, donde n es la dimensión del arreglo. El índice puede ser provisto directamente, derivado de una variable o calculado a partir de una expresión. Ejemplos de formas válidas para accesar a elementos de un arreglo:


    arr[5];
    arr[i];
    arr[(2 * i) + 1];

Los arreglos también pueden ser pasados a funciones como parámetros. Cuando se declara la función, simplemente especificamos el arreglo como parámetro, sin dimensión. El arreglo puede entonces ser usado normalmente dentro de la función. Por ejemplo:

    #include<iostream>
    using namespace std;

    int suma(int arreglo[], int tamano) {
        int sum = 0;
        for (int i = 0; i < tamano; i++) {
            sum += arreglo[i];
        }
        return sum;
    }

    int main() {
        int arr[] = {1, 2, 3, 4, 5, 6, 7};
        cout << suma(arr, 7) << endll;
    }
[¡Pruebalo en línea!](https://tio.run/##XU9LDoMgEN33FJN0o5Em/Xch9iLGBUFqSAQMn5Xx7BTQqO0sYHifmQcdhlNHqfcQ6sgl7V3LMFfGakbE@xBhZ7jsQBLBzEAoA2PbMhHp4NKCcYJksSFas65XdYMSbokgUuUwJuVODRWcyxX8KA3JzhMeLrxYQ18Ue3@s6C@qdRdvtknT2mlmnZZRO7PTb2JBuMz@g4WJdRMijBcEVwQ3BHcEDwRPBK9pW0KVs4Dx/OvgCWwe30y2/bLM@y8 "C++ (gcc) – Try It Online")

La función `sum` toma un arreglo de enteros `arreglo` y un entero `tamano` y retorna la suma de todos los elementos de `arreglo`. El programa al final imprime `28`.

## Arreglos Multidimensionales ##
C++ también tiene soporte para *arreglos multidimensionales*. Para crear un arreglo *bidimensional* se escribe:

`tipo_de_dato `**`nombreDeArreglo`**`[dimension1][dimension2];`

El arreglo tendrá `dimension1 x dimension2` elementos del mismo tipo y podemos verlo como un "arreglo de arreglos". El primer índice indica cuál de los `dimension1` subarreglos accesar, y el segundo índice accesa uno de los `dimension2` elementos dentro de ese subarreglo. La inicialización y el acceso funcionan de forma similar al caso
unidimensional:

    #include<iostream>
    using namespace std;

    int main() {
        int arregloBidimensional[2][4];
        arregloBidimensional[0][0] = 6;
        arregloBidimensional[0][1] = 0;
        arregloBidimensional[0][2] = 9;
        arregloBidimensional[0][3] = 6;
        arregloBidimensional[1][0] = 2;
        arregloBidimensional[1][1] = 0;
        arregloBidimensional[1][2] = 1;
        arregloBidimensional[1][3] = 1;

        for (int i = 0; i < 2; i ++) {
            for (int j = 0; j < 4; j ++) {
                cout << arregloBidimensional[i][j] << " ";
            }
            cout << endl;
        }
        cout << endl;
    }
[¡Pruebalo en línea!](https://tio.run/##jdHdCoIwFAfw@57iYDeFBGoRhNZFryG7GHPJEd1k06vo2ddmH2YJa4hHzvnN/VHWtpuSMWPAriUKVvcFz1DqTnHanBau3WsUJQjacN1SxkF3RToMhhuKDhqKYrWG69B4NalSvKzlGQtsuNAoBa3zhOQ7kr7drImIveAIe7@LnYv8LnHu4Hfbf86Nn/kSv/srX/zMF/vd9su9Hy5Swcp9dRwOtCWz@WwJw8//MqHVg1aW7lz5pW4x2XeQZfORkOQVcdMAgnSy9baYewkXRT260fzOb8bcAQ "C++ (gcc) – Try It Online")

Un arreglo bidimensional también puede ser inicializado durante la declaración de estas dos formas:

    int arregloBidimensional[2][4] = {6, 0, 9, 6, 2, 0, 1, 1};
    int arregloBidimensional[2][4] = {{6, 0, 9, 6}, {2, 0, 1, 1}};


## Cadenas ##
Las cadenas de texto constantes como `"¡Hola mundo!"` están representadas por C++ como una secuencia de carácteres en memoria. En otras palabras, una cadena es simplemente un arreglo de `char` y puede ser manipulado como tal.

Veamos el siguiente programa:

    #include<iostream>
    using namespace std;

    int main() {
        char holaMundo[] = {'¡', 'H', 'o', 'l', 'a', ' ', 'M', 'u', 'n', 'd', 'o', '!', '\0'};

        cout << holaMundo << endl;

        return 0;
    }
[¡Pruebalo en línea!](https://tio.run/##bc3NCsIwDAfwu08R8VAFhd1XPXvZE0wPoS1boUtHP05jz15Nhe1iDj/IPyFR83wblCoFvnWypFzWRlofUzA4PQ4c52hpAMLJxBmVgZh0WwcVSwkmtHS@wFIDLjVigNE77DJp37/hDot4iisIzzgGGWA6JjPE6G3vyLwasbbb5f2Fzwmk3L9wY0i7P7vBpBwImt9oLeUD "C++ (gcc) – Try It Online")

Este programa imprime "¡Hola Mundo!" Nota que el arreglo `holaMundo` termina con un carácter especial conocido como carácter *nulo*. Este carácter es usado para indicar el final de la cadena.

Las cadenas también pueden ser inicializadas utilizando cadenas constantes. En este caso, no se necesita un carácter nulo al final, el compilador automáticamente insertará uno:


    char holaMundo[] = "¡Hola Mundo!";

Los carácteres individuales de una cadena pueden ser manipulados, ya sea directamente o usando funciones especiales de las librerías de C++. Estas pueden ser incluidas en el programa a través de la directiva `#include`.  Las siguientes librerías son de especial interés:
* `cctype`: Manejo de carácteres.
* `cstdio`: Operaciones de entrada y salida.
* `cstdlib`: Utilerías generales.
* `cstring`: Manipulación de cadenas.

### Librería `cctype` ###
Algunas de las funciones de la librería `cctype` se presentan a continuación:
* `isalpha`: Retorna `true` si el carácter dado es alfabético.
* `isupper`: Retorna `true` si el carácter dado es mayúscula.
* `ispunct`: Retorna `true` si el carácter dado es un signo de puntuación.
* `tolower`: Retorna el cáracter dado convertido a minúscula.

Un ejemplo que muestra el uso de la librería `cctype`:


    #include<iostream>
    #include<cctype>
    using namespace std;

    int main() {
        char cadenaRandom[] = "e6S0T9A6.eS.999u9na.CADENA";

        char actual = cadenaRandom[0];
        for (int i = 0; actual != '\0'; i++) {
            actual = cadenaRandom[i];
            if (isalpha(actual)) {
                if (isupper(actual)) {
                    cout << (char)(tolower(actual));
                } else {
                    cout << actual;
                }
            } else if (ispunct(actual)) {
                cout << ' ';
            }
        }

        cout << endl;
        return 0;
    }
[¡Pruebalo en línea!](https://tio.run/##fZBNa4NAEIbv@yum6UElVDwFRBOQttcemt7aHIZ1kizo7rIflFL87Vaj1iQ0nePyPs@8O1zrhwPnbXsvJK98SblQ1hnCesN@nzh3X5o2zFshDyCxJquRE1hXZowJ6aBGIcMIvhl0w49ogGNJEl9Rlqp@38EaFrTaJm9psYppG6dp6lOJ8WPx9PxSLLITN8PInceqgy4syW7I7ZWBsN8qukSSTem7NQQfSZCBWC6nKv38LROjrB@x73wWK33EcEhH54I54rUmcytyaq@8gzyHsP9GFDpVqc8zIrsAGqDK0j@WAbuC2BU@NNNecner2eQLIJhlg6g5u/yYIlmOOw05b2R3Yta07Q8 "C++ (gcc) – Try It Online")

El ciclo `for` del código anterior itera sobre cada carácter de `cadenaRandom` hasta que se encuentra al carácter nulo. En cada iteración, si el carácter actual es alfabético y mayúscula, lo convierte a minúscula y lo imprime. Si ya es minúscula, simplemente lo imprime. Si el carácter es un signo de puntuación, se imprime un espacio. Todos los demás carácteres son ignorados. La salida resultante es "esto es una cadena".

### Librería `cstring` ###
Dos de las funciones de la librería `cstring` se presentan a continuación:
* `strcpy`: Toma dos cadenas como parámetros y reemplaza el contenido de la primera con una copia de la segunda.
* `strcat`: Toma dos cadenas como parámetros y copia el contenido de la segunda al final de la primera.

Ahora un ejemplo para mostrar el uso de la librería `cstring`:

    #include<iostream>
    #include<cstring>
    using namespace std;

    int main() {
        char fragmento1[] = "¡Soy una C";
        char fragmento2[] = "adena!";
        char fragmento3[20];
        char cadenaFinal[2] = "";

        strcpy(fragmento3, fragmento1);
        strcat(cadenaFinal, fragmento3);
        strcat(cadenaFinal, fragmento2);

        cout << cadenaFinal << endl;

        return 0;
    }
[¡Pruebalo en línea!](https://tio.run/##jY/BCoJAEIbvPcVkF4WC0qPWJegFOkqHYdxsQUdZdw8RPUyv0ouZrVBrKDSHZeb/v/mZpbpe5URtC10tJFNhMpHIqtFKYLmbDWTqVMl5r5qma4GxFE2NJKDRWWwN@0jWUKJkP4CbFd5FF1RwVpiXgnW1SU@wBe/5OFZXMIyw9@IJNOxRzATjfJKK0nB9@jHJ7hwkY5GGNsRZ/zTdv6i@@t@kpXNmEA841L4T6oDRv2AYjJxAldGQJO7B71FwVozQSmijGNa9dW/bFw "C++ (gcc) – Try It Online")

Una descripción de la ejecución de este programa:

* Primero crea e inicializa dos cadenas, `fragmento1` y `fragmento2`. `fragmento3` es declarado pero no inicializado. `cadenaFinal` es parcialmente inicializada (sólo contiene el carácter nulo).
* `fragmento1` es copiado a `fragmento3` usando `strcpy`, inicializando efectivamente `fragmento3` como `"¡Soy una C"`
* `strcat` es usada para concatenar `fragmento3` con `cadenaFinal` (la función sobreescribe el carácter nulo que estaba en `cadenaFinal`), dando a `cadenaFinal` el mismo contenido que `fragmento3`
* `strcat` es usado otra vez para concatenar `fragmento2` con `cadenaFinal`.
* `cadenaFinal` es impresa, mostrando `¡Soy una cadena!`.

<sub>Este texto está basado al curso [Introduction to C++ de MIT OCW](https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-096-introduction-to-c-january-iap-2011/#) y está disponinble bajo la licencia [Creative Commons Attribution-NonCommercial-ShareAlike](https://creativecommons.org/licenses/by-nc-sa/3.0/).</sub>
