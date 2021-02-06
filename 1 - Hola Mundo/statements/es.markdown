
# ¡Hola Mundo! #

El primer programa que la mayoría de los programadores escriben es el clásico "Hola Mundo". El propósito de este programa es mostrar el texto "Hola Mundo" al usuario. [Ejemplos de programas en diferentes lenguajes de programación](https://excelwithbusiness.com/blog/say-hello-world-in-28-different-programming-languages/).

    #include <iostream>
    using namespace std;

    int main() {
       cout << "Hola Mundo" << endl;

       return 0;
    }

[Pruébalo en línea!](https://tio.run/##LYsxCsMwDEX3nEKkSzoUusdk7tJDCFkEgS0b25pKz@46pm/77/Ep58dJ1DsMbqIUzDM4SbUVxngsl7cqeoJi5JqRGGrz@zKLaIOIotsdPlMMKFkD52B9pYDwNvVpvTarD//boHCzovDcp/j2/gM "C++ (gcc) – Try It Online")

NOTA:

El `return 0;` como se muestra arriba, no es estrictamente necesario para el "Hola Mundo". El valor de retorno `0` en `main` simplemente indica al sistema operativo que la ejecución del programa fue exitosa. Por default, un programa de C++ siempre va a retornar `0` si no hay un `return` al final de main.

## Explicación del Código ##

Antes de entrar en detalles, es útil pensar simultáneamente en un programa en términos de su *estructura* y también de su *significado*.

Un programa de C++ está estructurado de forma específica y particular. C++ es un lenguaje y por ende tiene una *gramática* similar a un lenguaje hablado, como el español. La gramática de los lenguajes de computación es mucho más simple que la de los lenguajes hablados, pero tiene reglas más estrictas. Al aplicar esta gramática al lenguaje, la computadora puede entender el programa y lo que se supone que debe de hacer.

Para tener un mejor entendimiento de la estructura y el significado del clásico "Hola Mundo", veamos un análisis línea por línea del programa.

## Una Explicación Detallada del Código ##

### La Línea `#include` ###

`#include <iostream>`

Tiene el hashtag `#` que significa el inicio de un ''comando del preprocesador''. El comando `include` es un comando específico del preprocesador que copia y pega el texto del archivo especificado entre `<` y `>` al código fuente. En este caso el archivo es `iostream`, el cual es un archivo estándar que viene con el compilador de C++. El nombre de ese archivo viene de "input-output streams"; en pocas palabras, contiene el código necesario para leer y mostrar texto al usuario.

La declaración `include` permite que un programador _incluya_ esta funcionalidad en el programa sin tener que literalmente cortarlo y pegarlo en el código fuente.

### La Línea `using namespace std` ###

`using namespace std;`

C++ tiene el concepto de espacios de nombre (`namespace`). Un espacio de nombre es esencialmente un prefijo que se aplica a todos los nombres en un determinado conjunto. Una forma de ver a los espacios de nombres es que son como cajas de herramientas con diferentes herramientas útiles. El comando `using` le dice al compilador que permita que todos los nombres en el espacio de nombres `std` puedan usarse sin su prefijo. El archivo iostream define tres nombres utilizados en este programa: `cout`,` cin` y `endl`, que están definidos en el espacio de nombres `std`. `std` es la abreviatura de "standard", ya que estos nombres se definen en la biblioteca estándar de C ++ que viene con el compilador.

Sin `using namespace std;`, los nombres tendrían que incluir el prefijo y escribirse como `std::cout`, `std::cin` y `std::endl`. Si continuamos con el ejemplo de la caja de herramientas, este código estaría diciendo: "Use las herramientas` cout`, `cin` y` endl` de la caja de herramientas `std`.

Siempre recuerda que el archivo `iostream` utiliza el espacio de nombre `std`.

### La Línea `int main()` ###

El punto de partida de todos los programas de C++ es la función `main()`. El sistema operativo llama a esta función cuando la computadora ejecuta tu programa. Por ejecución queremos decir: realizar las acciones especificadas por las declaraciones en tu programa.

### Las Líneas `cin` y `cout` ###

    cout << "Hola Mundo" << endl;
    cin.get();

`cout` es la abreviación de "character output" y `cin` es la abreviación de "character input".

En un programa típico de C++, la mayoría de las llamadas a funciones son de la forma `objecto.nombre_de_funcion(argumento1, argumento2)`. Por ejemplo `cin.get()` en el código anterior (donde `cin` es el objeto,` get` es el nombre de la función, y no hay argumentos en la lista de argumentos). Sin embargo, símbolos como `<<` también pueden comportarse como funciones, como se ilustra con el uso de `cout` anterior. Esta capacidad se denomina "sobrecarga del operador", que se analizará más adelante.

### Las llaves `{}` ###

Un bloque de código se define con los los símbolos `{ }`. `{` significa el inicio de un bloque de código y `}` significa el final.

NOTA: Los símbolos `{ }` también tienen algunos otros usos.

### Punto y Coma ###

Los comandos en C++ deben terminarse con un punto y coma, así como las oraciones en español deben terminarse con un punto. Así como las oraciones en español pueden abarcar varias líneas, también pueden hacerlo las declaraciones en C++. De hecho, puede usar tantos espacios y nuevas líneas entre las palabras de un programa de C++ como desees para embellecer tu código así como los espacios se usan para justificar el texto impreso en las páginas de un libro.

En su momento, IBM intentó pagar a sus programadores por la cantidad de líneas de código que escribían cada semana. Esto no funcionó muy bien para los programadores de C que podían hacer que una declaración abarcara miles de líneas simplemente presionando la tecla Intro para insertar muchas líneas nuevas entre las palabras de sus programas.

### El `return` ###

La ejecución del comando `return` en la función `main()` de un programa devuelve un valor al sistema operativo y termina la ejecución de este programa.

## Compilación del Código ##

Para que la computadora ejecute el código que has escrito, primero debe ser compilado por un _compilador_ de C++. El compilador traduce la representación textual del programa en una forma que una computadora puede ejecutar de manera más eficiente.

### ¿Qué Hace el Compilador? ###

En términos muy generales, el compilador es un traductor que actúa como intermediario entre el programador y el CPU de la computadora. Un lenguaje de alto nivel como C++ es en realidad una especie de lenguaje de _compromiso_ entre el idioma nativo del CPU (generalmente denominado _lenguaje máquina_) y el idioma nativo del programador (por ejemplo, español). Las computadoras no entienden los idiomas humanos de forma nativa, sin embargo, sería demasiado difícil para alguien escribir código máquina y requeriría mucho tiempo. Por lo tanto, el propósito del lenguaje informático en sí mismo es definir un punto medio que esté más cerca de cómo los humanos piensan y organizan los procedimientos.

Por lo tanto, el compilador lee el código escrito por el programador y lo traduce a lenguaje máquina, que la computadora puede ejecutar directamente.

C++ es un "lenguaje compilado" que el compilador convierte al lenguaje máquina. Los programadores principiantes probablemente también se encontrarán con la noción de "lenguajes interpretados" e "intérpretes". Como este texto cubre C++, los lenguajes interpretados no están cubiertos en detalle; sin embargo, en resumen, un intérprete es como un compilador que convierte el programa a lenguaje máquina en el momento en que se ejecuta en la computadora, en lugar de hacerlo de antemano como se hace con un lenguaje compilado. Un ejemplo de lenguaje interpretado es Python.

### Ejecución del Compilador ###

El código debe compilarse con un compilador para finalizar el proceso. ¿Qué pasa si no tienes uno? Bueno, la buena noticia es que hay varios buenos compiladores que están disponibles de forma gratuita. GNU Compiler Collection (GCC) tiene versiones disponibles para la mayoría de los sistemas operativos y hace un buen trabajo implementando el estándar ISO C++. El compilador _clang_ tiene soporte completo para C++11 y FreeBSD es totalmente compatible con _clang_ y C++11. Sin embargo, muchas personas prefieren usar un entorno de desarrollo integrado (IDE) que proporciona un entorno amigable para el usuario para desarrollar programas. Para MacOS X, hay Xcode que usa _gcc_ para compilar C++. Para Windows, está DevC++, que también usa _gcc_ para compilar C++, Microsoft Visual C++ (y su versión Express gratuita), TCLITE y las portaciones de GNU Compiler Collection distribuidos dentro de Cygwin y MinGW.

Cada compilador se invoca de una manera específica. Por ejemplo, si deseas utilizar GCC, escribe lo siguiente en un terminal:

    c++ ej.cpp -o binario

Reemplaza <kbd>ej.cpp</kbd> con el nombre del archivo fuente que contiene el programa que deseas compilar. El nombre de archivo que elijas debe tener una extensión de <kbd>.cpp</kbd> o <kbd>.c++</kbd>

Reemplaza <kbd>binario</kbd> con el nombre de archivo que deseas usar para invocar el programa ejecutable.

Si el compilador detecta errores en el código, los escribirá en el terminal para que pueda verlos y corregirlos editando tu archivo de código. Si no se detectan errores, el compilador producirá un archivo de programa ejecutable, en este caso llamado <kbd>binario</kbd> en el mismo directorio que el archivo fuente.

Para correr el programa compilado, escribe en tu terminal:

    ./binario

y observa cómo tu computadora ejecuta los comandos que especificaste en tu código

Si deseas utilizar un compilador diferente, consulte la documentación que describe ese compilador para conocer la forma correcta de invocarlo.

### Compiladores en Línea ###
También existen compiladores que funcionan completamente en interfaz web. Tienen la ventaja de que no se debe de instalar ningún programa en la computadora ni de ejecutar comandos en la terminal para compilar y ejecutar tus programas. Son altamente recomendados para alguien que va comenzando a aprender a programar. Te recomendamos los dos siguientes compiladores en línea:

* [Try it online](https://tio.run/#cpp-gcc). Cuando entres asegurate de escoger `C++ (gcc)` como lenguaje. Después escribe tu código y presiona Ctrl-ENTER para compilarlo y ejecutarlo.
* [ideone.com](https://www.ideone.com/). Igualmente, asegurate de escoger `C++` como lenguaje. Después escribe tu códgio y presiona Ctrl-ENTER para compilarlo y ejecutarlo.

## Ejercicios ##

#### Ejercicio 1 ####
Copia lo siguiente, luego edítalo para que se compile correctamente e imprima "Hola Mundo" en la pantalla

    #include <iostream>
    using namespace std;

    int main() {
        cout << "Hola Mundo" << endl;
        return 0;
    }

[Pruébalo en línea!](https://tio.run/##LYsxCsMwDEX3nEKkSzoUusdk7tJDCFkEgS0b25pKz@46pm/77/Ep58dJ1DsMbqIUzDM4SbUVxngsl7cqeoJi5JqRGGrz@zKLaIOIotsdPlMMKFkD52B9pYDwNvVpvTarD//boHCzovDcp/j2/gM "C++ (gcc) – Try It Online")

#### Ejercicio 2 ####
Cambia el mensaje "Hola Mundo" en ejemplo anterior para mostrar otra línea para que muestre:
```
Hola Mundo
¡Viva C++!
```

    #include <iostream>
    using namespace std;

    int main() {
      cout << "Hola Mundo" << endl;
      cout << "¡Viva C++!" << endl;
      cin.get();
      return 0;
    }

[Pruébalo en línea!](https://tio.run/##Xco9CgIxEEDhPqcY12aXRbFPsLGxsbUfkiEMJJOQHxvxMF7Fi0W21PI9PpvzwVs7xp7Fhu4IDKfaCmE8q15ZPAhGqhktQW1OK8XSICLLvMBTAdjUGxgD0@d9TQHh1sWl3bQtEhf0L7nzA@Gyrn@A5eipzcsWhVovAietXmN8AQ "C++ (gcc)")

#### Ejercicio 3 ####
Estás usando

    using namespace std;

para reducir la cantidad de escritura de código necesaria, quítale ese comando y ve si puedes hacer que tu programa compile y corra sin él.

<sub>Este texto está basado al curso de [C++ de Wikiversity](https://en.wikiversity.org/wiki/C%2B%2B) y está disponinble bajo la licencia [Creative Commons Attribution-ShareAlike](https://creativecommons.org/licenses/by-sa/3.0/).</sub>
