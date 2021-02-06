


# Operaciones Básicas de Matemáticas #

Las operaciones básicas de matemáticas son muy simples en C++. Ten en cuenta que las operaciones matemáticas en C++ siguen un orden similar al visto en la escuela. Por ejemplo, las multiplicaciones y divisiones tienen precedencia sobre las sumas y restas. Pero puedes cambiar el orden en el que se realizan las operaciones agregando paréntesis.

## Operadores Aritméticos ##

Los operadores aritméticos en C++ se representan de la siguiente forma:

- `+` para la suma.
- `-` para la resta.
- `/` para la división.
- `*` para la multiplicación.
- `%` para módulo. Esta operación regresa el residuo de la división, por ejemplo, `4 % 5 = 4` y `6 % 5 = 1`.
- `+=` para sumar y asignar.
- `-=` para restar y asignar.
- `/=` para dividir y asignar.
- `*=` para multiplicar y asignar.
- `%=` para aplicar módulo y asignar.
- `++` equivalente a `+= 1`.

Veamos unos ejemplos en el siguiente código:


    #include <iostream>

    using namespace std;

    int main() {
        int miEntero = 100;

        miEntero = miEntero / 10; // miEntero ahora vale 10.
        miEntero = miEntero * 10; // miEntero nuevamente vale 100.
        miEntero = miEntero + 50; // miEntero vale 150.
        miEntero = miEntero - 50; // miEntero regresó a su valor inicial, 100.

        miEntero = miEntero + 100 * 2; // miEntero vale 300 porque la multiplicación tiene precedencia sobre la suma.
        miEntero = (miEntero + 100) * 2; // miEntero vale 800 porque cambiamos la precedencia por el uso de paréntesis.

        miEntero -= 10; // miEntero vale 790 porque hacer -= es equivalente a miEntero = miEntero - 10;
        miEntero = miEntero % 100; // miEntero vale 90 porque % es el operador módulo.
        miEntero++; //miEntero vale 91 porque ++ es equivalente a sumarle 1.

        cout << miEntero << endl;

        return 0;
    }

[Pruébalo en línea!](https://tio.run/##fVNLbsIwEN3nFCNVSNCUXyvUVkB3PcjgjIIlxw7@sKl6oK45Qg6WjsMnlDRk5fj5fWY8FmU5zoWo6wephQoZwUoa5y1h8ZEkwUmdg8aCXImCwPlsmSRSeyhQ6uEIvhLgr9mQn9qTNbCG@WzGpyJwtXlZThlfwnTa7uDWWIQ9KmJo0kt87BB1oD1n458z@w49hcUN/chZ3OGMOxxLuSVXHQDBhahgLJcvhUT1dPS/E4BxruL5nxQvjJTG7gKBQiiC8rJUUqCQ1UGDl6QJSkuCMtLsBc5sbHPUhQI7@Yd/PUc9pm@tqcBiI7EwLmpeGzEOpCA4AzwbJdrqhxWcdLeFjted62lMXt8vJlseIRsPkgPaBRnxeHfY03vW623moJmyrl3rNmhsFJiSLGZcRlEdsqDM326laRS50ZifNdK0mzV23MbBOXVAmOBhtWpz8Jp0po7ZhdSTnPxwdHoRlnywGriy77r@BQ "C++ (gcc)")

## Operadores Lógicos ##
Un operador lógico funciona de forma similar a los operadores arímeticos, sólo que en vez de funcionar con variables númericas, funciona con variables booleanas.

C++ cuenta con los siguientes operadores lógicos:
* Operador  `||` (OR): La expresión `a || b` retorna `true` si `a` o `b` (o ambos) son iguales a `true`, sino retorna `false`.
* Operador `&&` (AND): La expresión `a && b` retorna `true` si `a` y `b` son ambos iguales a `true`, sino retorna `false`.
* Operador `!` (NOT): La expresión `!a` retorna `true` si `a` es igual a `false`; y retorna `false` si `a` es igual a `true`.

Veamos unos ejemplos de uso de operadores lógicos en el siguiente código:

    #include <iostream>

    using namespace std;

    int main() {
        bool esDeNoche = false;
        bool estaSoleado = true;
        bool estaNublado = false;
        bool voyASalir = true;
        int temperaturaAmbiente = 13;

        bool necesitoCargarParaguas = voyASalir && estaNublado;
        bool necesitoUsarBloqueadorSolar = voyASalir && estaSoleado;
        bool haceFrio = temperaturaAmbiente <= 17;
        bool necesitoCargarSueter = voyASalir && haceFrio;
        bool necesitoLlevarMochila = necesitoCargarParaguas || necesitoCargarSueter;

        if (necesitoCargarParaguas) {
            cout << "Necesito cargar paraguas porque voy a salir y esta nublado" << endl;
        }
        if (necesitoUsarBloqueadorSolar) {
            cout << "Necesito usar bloqueador solar porque voy a salir y esta soleado" << endl;
        }
        if (necesitoCargarSueter) {
            cout << "Necesito cargar sueter porque voy a salir y hace frio" << endl;
        }
        if (necesitoLlevarMochila) {
            cout << "Necesito llevar mochila porque necesito cargar mochila y/o paraguas" << endl;
        }

        return 0;
    }
[¡Pruébalo en línea!](https://tio.run/##jZLLTgMxDEXX9CusIlVlgQCxYDEDUgGxggqp4gPcjDuNlEmGPCpVtN9eknT6Th9ZZJFc28e@ZnV9WzK2WIA/11wy4QqCnCtjNWH10grv8XKGyxIkVmRqZATGFtnml0sLFXLZvYG/@BDOUCkBZN6pr9iY4BlGKAxl@/8WB0oQFsorrHYpQd8NxVKQSjFR094ABdcHCQKWpaomjdZp7FVDTtIGlIfHrLWbRRIjw616Q12i/kaNpUPjpZv0nc42TZaO/zGoX4X6daEl7VtDnUrS9LyXZOxH@6F5HEWCO/fgT9kp7oEjSwcFV2mPhH4KmqD@8i5xgT72yChms2SxrTWIMx9BN50g7MbVFVPOQp5Du9@IgEUV1Ks6tdJ@eqEDQDCxhynUjvxmCqEmpNshnmQhNv3Mk/UTXkSIlfaQxfkIGK5DwET/kkTBRZDLXbiYaHtwZ1CasZilo0mE4CuMvLEX19@x@gyAiFqomr1oCOQe3@p7eqfWFp7E2dkWTX7BJdwvhfPF4h8 "C++ (gcc)")

## Librería `cmath` ##

La librería de matemáticas `cmath` de C++ es fácil de usar y puedes disponer de ella incluyendola en tu código:


    #include <cmath>


### Funciones de `cmath` ###

Ahora que incluimos la librería `cmath`, usemos algunas de sus funciones.

#### Raíz Cuadrada: `sqrt()` ####
Vamos a escribir un programa que lee un número (de tipo `float`), y luego cálcula y escribe la raíz cuadrada de ese número.

    #include <iostream>
    #include <cmath>

    using namespace std;

    int main() {
        float miFloat = 0.0f; // Por default cuando asignamos un decimal a una variable, el compilador
                              // lo interpreta como un número de 64 bits pero los float son de 32 bits.
                              // Para solucionar esto agregamos la letra f.

        cin >> miFloat;

        float raiz = sqrt(miFloat);
        cout << raiz << endl;

        return 0;
    }

[Pruébalo en línea!](https://tio.run/##hVDLTsNADLz3KyxxaSVIw0NcEnrk3F9wN06w5N1N98EBxI9x5cOCN4FWICTmsCvP2B7bZhyvBmOmCRQX7IzkjqBlH1MgtLvVT95YTE8LOT85shvAoaU4oiGIqWvOKrsEFtmtN/A6EwW9eFSaH@f/Aeqq7hvYbmHvA3TUY5YEJqPrPGDkQZv7CNmpZtiiAGqA8IyB8SB0CSRgvB1ZsPPhZPM31EZ8mYvCGChhqfSluft4txS8msD9HRw4RRhLLOq9TBx9GQFub2a1@t9ojwG1SrJh7zAAxaQbDYGGeSNBEEqa0lfnixUYdrDbfV@oOfG/LhiQX/R88RjS@it3c042Pido2yVLf3KdNKuTrLvn4KBeCt6m6br@BA "C++ (gcc) – Try It Online")

#### Potencias: `pow()` ####
Vamos a escribir un programa que lee un número (de tipo `float`) y luego cácula e imprime las potencias `2`, `3` y `0.5` de ese número.

    #include <iostream>
    #include <cmath>

    using namespace std;

    int main(){
        float miFloat = 0.0f;

        cin >> miFloat;
        cout << pow(miFloat, 2) << endl;
        cout << pow(miFloat, 3) << endl;
        cout << pow(miFloat, 0.5) << endl;

        return 0;
    }

[Pruébalo en línea!](https://tio.run/##jYrNDoIwDIDvPEUTL5AoWTCeQI6@x1IGNmHdwrZ4MD775EchetEe2vT7PrT20CHGCOPsiLEPjYKKjPODkrpOPjlq6a8LnFdwxB2w1MpZiQqcb8rNEnvQkjjN7vM/TdsbOVK6zPcMIhdtmawaiaGu377cuAkeqgqsuaUvuYcim5Dipv8RHv8NRX76Std@UD4MDGLBjxiLJw "C++ (gcc) – Try It Online")

#### Funciones Trigonométricas `sin()`, `cos()`, `tan()` ####

En la librería `cmath` las funciones trigonométricas reciben **radianes** (un número entre 0 y 2$\pi$) como parámetro. Escribamos un programa que cácula el seno, coseno y tangente de un número:

    #include <iostream>
    #include <cmath>

    using namespace std;

    int main() {
        float miFloat;

        cin >> miFloat;
        cout << sin(miFloat) << endl;
        cout << cos(miFloat) << endl;
        cout << tan(miFloat) << endl;

        return 0;
    }

[Pruébalo en línea!](https://tio.run/##jY0xDsIwDEV3TmGJpR2QYCbKyD0sNxRLjVM1zoQ4e5q0CKhg4A@2/P63TeN46IlyhqI9Cw2pc2A4RJ0cervbcvKotxUuJUWWHgS9iyOSg6jd@e2yKHhkaVq4L6DqOgQsmC@1f4SriAWs3ZoLD0nBGCjfmqfZ1tlJN3ynKMQ/Uoq/br1ik9M0CRzXxUfOpxk "C++ (gcc) – Try It Online")

#### Manipulación de Decimales en Flotantes `round()`, `trunc()`, `floor()`, `ceil()` ####

La librería `cmath` cuenta con las funciones para manipular los decimales de los valores de los tipos `float` y `double`:

* Función `round()`: Redondea al valor entero más próximo (por ejemplo `round(2.7)` retorna `3` y `round(2.1)` retorna `2`).
* Función `floor()`: Redondea el valor hacia abajo (por ejemplo `floor(2.9)` retorna `2` y `floor(-3.1)` retorna `-4`.
* Función `ceil()`: Redondea el valor hacia arriba (por ejemplo `floor(4.2)` retorna `5` y `floor(-3.1)` retorna `-3`.
* Función `trunc()`: Trunca el valor. Es decir elimina todos los dígitos después del punto decimal (por ejemplo `trunc(43.2398)` retorna `43`.

Veamos un ejemplo de uso de estas funciones:

    #include <iostream>
    #include <cmath>

    using namespace std;

    int main() {
        double miFloat = -2.91234;

    cout << miFloat << endl;
    cout << round(miFloat) << endl;
    cout << floor(miFloat) << endl;
    cout << ceil(miFloat) << endl;
    cout << trunc(miFloat) << endl;

        return 0;
    }

[¡Pruébalo en línea!](https://tio.run/##fY9BDoIwEEXXcopJ3MBCI@jGgC69R51WbNJOSTtdGc9eEQzEhPAXk8l7f/Ox63YtYkrQZ6sJTZQKGu0CeyXsNfvnaAU/RzicGDS1QMKq0AlUEFjWs9XEYIWmvIDXAL6RLt6NAqtvxgmGC@yq/bmsjqc6yzboIkPTTLZ/FUlTz8a7SDL/@WKh8DDO@bUCKm3WPPtIuFCYFnjF0RMcxqXvlMoP "C++ (gcc) – Try It Online")

## Ejercicio ##
#### Tiro Parabólico ####
Un portero saca el balón desde el césped a una velocidad de `v0` m/s. Si la pelota sale del suelo con un ángulo de `rad` radianes y cae sobre el campo sin que antes lo toque ningún jugador. Escribe un programa que lea los valores `v0` y `rad` y calcule la altura máxima del balón.

La altura máxima de un tiro parábolico está dado por la siguiente fórmula:
$$y_{max} = \frac{v_0^2 \cdot \sin^2(rad)}{2g}$$
donde $g = 9.81$ es la constante de gravedad y $sin^2(rad)$ es el cuadrado de la función seno aplicada al ángulo $rad$.


    #include <iostream>
    #include <cmath>

    using namespace std;

    int main() {
        double v0;
        double rad;
        double g = 9.81;
        double alturaMaxima;

        cin >> v0;
        cin >> rad;

        alturaMaxima = (pow(v0, 2) * pow(sin(rad), 2)) / (2.0 * g);
        cout << alturaMaxima << endl;

        return 0;
    }

[¡Pruebalo en línea!](https://tio.run/##ZY9dCsIwEITfPcWAL4lobQVBsfYGHmJNQg00aWkTFcSz11RF@zMPgf0mmdmIqlrlQrQtgubaisJLhVSXjasVmWw25MKQu3zg@/CNtjksGdVUJBQaJw9/V1sHQ9oyjscbdJKlPxcK1/gwRjXJCctxxD7aJRODCudrOtFdG@pVdhLaIssGDV/0a/gZ/ZhQxaryxq7xEhuOBbohfJCFZ7xDHGuwTRQHK@e98NI7pOkwK8zKymJUV6twxeK72bNtk3iWRNsX "C++ (gcc) – Try It Online")

<sub>Este texto está basado al curso de [C++ de Wikiversity](https://en.wikiversity.org/wiki/C%2B%2B) y está disponinble bajo la licencia [Creative Commons Attribution-ShareAlike](https://creativecommons.org/licenses/by-sa/3.0/).</sub>
