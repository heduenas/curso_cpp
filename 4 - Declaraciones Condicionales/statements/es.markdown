
# Declaraciones Condicionales #
Como su nombre lo indica, las *declaraciones condicionales* especifican si se debe ejecutar o no cierto bloque de código. Los dos tipos generales son `if`-`else` y `switch`-`case`.

## Operadores de Comparación ##
Las *condiciones* de las declaraciones condicionales se especifican utilizando *operadores de comparación*. Estos operadores hacen que la declaración en la que están contenidos retornen un valor booleano `true` o `false`.

Estos son algunos de los operadores de comparación disponibles en C++:
* **Operador de igualdad**: `==`.
* **Operador de desigualdad**: `!=`.
* **Operador mayor que**: `>`.
* **Operador mayor o igual que**: `>=`.
* **Operador menor que**: `<`.
* **Operador menor o igual que**: `<=`.

Estos son *operadores binarios*, lo que significa que toman dos parámetros para compararlos entre ellos. También existe el siguiente *operador unario*:
* **Operador de negación**: `!`. Este operador toma un valor booleano y regresa el valor inverso (convierte `true` a `false` y `false` a `true`).

Ejemplos:
* `5 == 5` regresa `true`.
* `7 != 5` regresa `true`.
* `'a' == 'b'` regresa `false`.
* `6 > 9` regresa `false`.
* `4 <= 4` regresa `true`.
* `!true` regresa `false`.
* `!false` regresa `true`.

## El Comando Condicional `if`-`else` ##

Hay dos variaciones del comando `if`-`else`. Veamos ambos casos a través de ejemplos:

#### Condición `if` ####

    if (diaDelMes > 31) {
        cout << "El día del mes es inválido." << endl;
         // Este pedazo de código sólo se ejecuta si la condición diaDelMes > 31 se cumple.
    }


#### Condición `if`-`else` ####

    if (diaDelMes > 31) {
        cout << "El día del mes es inválido." << endl;
         // Este bloque de código sólo se ejecuta si la condición diaDelMes > 31 se cumple.
    } else {
        cout << "El día del mes es :" << x << endl;
        // Este bloque de código se ejecuta si la condición diaDelMes > 31 no se cumple.
    }



## El Comando Condicional `switch`-`case` ##

Este comando prueba la igualdad de una variable con un número de valores distintos y luego ejecuta el código correspondiente al valor de la variable. Sigue la siguiente sintaxis:

    switch (diaDelMes) {
        case 1:
            // Este bloque de código se ejecuta si diaDelMes == 1.
            break;
        case 2:
            // Este bloque de código se ejecuta si diaDelMes == 2.
            break;
        default:
            // Este bloque de código se ejecuta si diaDelMes es distinto a todos los valores listados en los casos anteriores.
            break;
    }

Nota: el comando `break` es necesario al final de cada `case` o `default` para que la ejecución se salga del `switch`. Sin usar `break` la ejecución continuaria al siguiente `case` y después al que sigue de ese y así hasta terminar el `switch` o encontrar un `break`.


## Ejercicios ##

#### Calcular Paridad de un Entero ####

Vamos a leer un número de la entrada y después a escribir si es par o impar.

    #include <iostream>
    using namespace std;

    int main() {
        int entero;

        cin >> entero;
        if ((entero % 2) == 0) {
            cout << "PAR" << endl;
        } else {
            cout << "IMPAR" << endl;
        }

        return 0;
    }

[Pruébalo en línea!](https://tio.run/##dY9NC4JAEIbv/YoXI9BDsHVNhY4dgugfLOskCzrKfpzC377lLqUX5zAMz/sBo8bx2CoVAr6z16w63xBKPVhnSPb1bubeam7Bsic7SkWwrrlEIS7NDr3UnBd4R/CDxI7MEJ1/rjSjrtdSsr@Q5wnigHOBqoJY98Xs4B3KEtnj@szmg7jplo4J1FnaytzuG6nlkXkMOW8YIhmmEE7iAw "C++ (gcc) – Try It Online")

#### Calcular el Número de Días del Mes ####

Vamos a leer un número que representa el mes del año y después a escribir el número de días que tiene ese mes (suponiendo que no es un año bisiesto).

    #include <iostream>
    using namespace std;

    int main() {
        int mes;

        cin >> mes;

        int numeroDeDias;
        switch(mes) {
            case 1:
                numeroDeDias = 31;
                break;
            case 2:
                numeroDeDias = 28;
                break;
            case 3:
                numeroDeDias = 31;
                break;
            case 4:
                numeroDeDias = 30;
                break;
            case 5:
                numeroDeDias = 31;
                break;
            case 6:
                numeroDeDias = 30;
                break;
            case 7:
                numeroDeDias = 31;
                break;
            case 8:
                numeroDeDias = 31;
                break;
            case 9:
                numeroDeDias = 30;
                break;
            case 10:
                numeroDeDias = 31;
                break;
            case 11:
                numeroDeDias = 30;
                break;
            case 12:
                numeroDeDias = 31;
                break;
            default:
                cout << "El numero de mes es invalido." << endl;
                break;
        }
        cout << numeroDeDias << endl;

        return 0;
    }

[Pruébalo en línea!](https://tio.run/##rZTPTsMwDMbvewprXMYBtHT82dbS03iQkJhhkbpVk8AB7dlLGk2jpYfuECvKwf788@ccoprm7qhU1y0gxA2xMl4jFFRb16Ksypj3lvgILCu0jVQI1uk8FuJF7KCSxKtb@ImJSxLtQNaHIoay/CuMin0L@wrb@oAHkgOJ/SanPlahbTgiAqVFEPtRro8hB15gI/KJ5C3s95lPadksLdteT9sk9fYwT1tfT3tM6u0pqbfnpN62SWm7pJuKdVJzQqR1l6Vyp/FdeuOmOFV7B0UBy1dzRgdt/0dAOMRf0pCu75e9BFmb2WGnxX/yyPAIc5G26HzLcH6ZU9dlvw "C++ (gcc) – Try It Online")

<sub>Este texto está basado al curso de [C++ de Wikiversity](https://en.wikiversity.org/wiki/C%2B%2B) y está disponinble bajo la licencia [Creative Commons Attribution-ShareAlike](https://creativecommons.org/licenses/by-sa/3.0/).</sub>
