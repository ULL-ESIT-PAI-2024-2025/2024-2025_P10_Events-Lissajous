# Práctica 10. El patrón MVC. Programación Gráfica Orientada a Eventos. Curvas de Lissajous
### Factor de ponderación: 10

### Objetivos
Los objetivos de esta tarea son poner en práctica:
* La arquitectura Modelo Vista Controlador
* Conceptos básicos de Programación orientada a eventos en TypeScript.
* Conceptos de Programación Gráfica en TypeScript usando la API Canvas.
* Metodologías y conceptos de Programación Orientada a Objetos en TypeScript.
* Principios y Buenas prácticas de programación Orientada a Objetos.
* El uso de elementos HTML básicos.

### Rúbrica de evaluacion del ejercicio
Se señalan a continuación los aspectos más relevantes (la lista no es exhaustiva)
que se tendrán en cuenta a la hora de evaluar esta práctica:
* Se valorará la realización de las diferentes tareas que se proponen
* El comportamiento del programa debe ajustarse a lo descrito en este documento
* Capacidad de la programadora de introducir cambios en el programa desarrollado
* Se acredita conocimiento y puesta en práctica de principios y buenas prácticas de programación orientada a objetos
* Saber corregir bugs en sus programas utilizando el depurador de Visual Studio Code
* La arquitectura de la aplicación ha de ser conforme al patrón MVC
* Deben usarse estructuras de datos adecuadas para representar los diferentes elementos que intervienen en el problema
* Ser capaz de desarrollar programas simples en TypeScript en el entorno Linux de la VM de la asignatura usando
  `ts-node`
* Ser capaz de generar documentación para sus programas TS utilizando
  [TypeDoc](https://typedoc.org/)
  y de visualizar dicha documentación en un servidor web
* Acreditar que conoce las etiquetas de 
  [JSDoc](https://jsdoc.app/)
* El alumnado debe ser capaz de resolver problemas tanto en JS como en TS en la plataforma Exercism subiendo sus soluciones a la misma
* Ser capaz de desarrollar tests unitarios para sus programas utilizando
  [Jest](https://jestjs.io/)
* Acreditar su capacidad para configurar y utilizar 
  [ESLint](https://eslint.org/)
y que es capaz de trabajar con la misma en Visual Studio Code
* El alumnado ha de acreditar que es capaz de desarrollar programas de la plataforma Jutge
* Se comprobará que el código que el alumnado escribe se adhiere a las reglas de las Guías de Estilo de Google para 
[TypeScript](https://google.github.io/styleguide/tsguide.html)
y/o
[JavaScript](https://google.github.io/styleguide/jsguide.html)
* Todas las prácticas realizadas hasta la fecha, incluída la que se presenta para su evaluación, se encuentran alojadas en repositorios privados de GitHub.
* Acreditar que es capaz de editar ficheros de forma remota en su VM usando Visual Studio Code

### Indicaciones de caracter general

* La aplicación que desarrolle ha de ser orientada a objetos.
Ponga en práctica en su desarrollo los fundamentos, principios y buenas prácticas de la OOP así como los
conocimientos que haya adquirido en el uso de patrones de diseño.

* Aloje ficheros de configuración adecuados en el directorio raíz de su proyecto, de modo que se contemplen todas las dependencias del mismo.

* Utilice un fichero distinto para el código de cada una de las clases que intervienen en su programa.

* Encapsule las clases en módulos que exporten la correspondiete clase hacia otros programas clientes que pudieran utilizarla.

* Configure para la práctica una página web que sirva de índice para mostrar la documentación generada por
Typedoc para esta práctica.

* Todo el código estará ubicado en el directorio `src/home-work` del proyecto. Use subdirectorios de éste si le resulta conveniente.

* Antes de comenzar a desarrollar su programa dedique el tiempo necesario a diseñar la estructura de clases que
utilizará en su programa, así como las relaciones existentes entre las mismas.
Utilice
[LucidChart](https://www.lucidchart.com/pages/es)
o una aplicación similar para realizar un diagrama UML para esas clases, que ha de añadir a la página índice de esta
práctica.
Asegúrese de la corrección de su diagrama UML.

* Realice, como siempre, un diseño incremental del programa comprobando cada una de las funcionalidades que añade, siguiendo una aproximación TDD.

* Cuando finalice su desarrollo **modifique el fichero `README.md`** de su proyecto incluyendo la información
habitual en cualquier proyecto público en GitHub.
Puede usar este
[README.md](https://github.com/taniarascia/mvc?tab=readme-ov-file)
como ejemplo de referencia pero incluya además de la información que allí se indica, dos apartados,
`Building and Running the code` y `Live Demo`.
En el primero de ellos ha de explicar en detalle cómo a partir de clonar su repo público ha de compilarse,
ejecutarse y desplegarse su aplicación, mientras que en el segundo ha de incluir un enlace (véase el apartado *Presentación
de resultados* de este documento) a la URL pública donde encontrar su aplicación.

### El patrón Modelo Vista Controlador
El 
[modelo-vista-controlador](https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93controller)
(MVC) es un patrón de diseño arquitectónico habitualmente utilizado para el desarrollo de interfaces de usuario 
que divide la lógica de la aplicación en tres elementos relacionados. 
Esta división se realiza para separar la representación interna de la información (modelo) 
de las formas en que se presenta (vista) y se acepta la información del usuario (contolador).
Este patrón se ha utilizado tradicionalmente para interfaces gráficas de usuario (GUIs) de escritorio, 
y se ha popularizado asimismo para el diseño de aplicaciones web.

Es fácil encontrar en la web información sobre el patrón MVC, así como ejemplos de implementación del
mismo en diferentes lenguajes.
El 
[trabajo expuesto en clase](https://github.com/ULL-ESIT-PAI-2024-2025/2024-2025-pai-mvc-2425-pai-mvc-team)
sobre MVC y las referencias del mismo son un buen punto de partida como toma de contacto con el patrón MVC.

Asimismo el breve artículo
[Understanding the MVC Pattern with
TypeScript](https://medium.com/@alessandro.traversi/understanding-the-mvc-pattern-with-typescript-an-in-depth-analysis-5a5d6f2d61a4)
puede serles útil inicialmente.

### Las curvas de Lissajous
Las 
[curvas de Lissajous](https://es.wikipedia.org/wiki/Curva_de_Lissajous)
son las curvas que recorre un punto sometido a un doble movimiento armónico simple en dos direcciones perpendiculares. 

La forma de la curva depende exclusivamente de la relación entre las frecuencias de los dos movimientos, 
`a/b` y de su desfase *phi*. 
Si `a/b = 1`, la curva es un segmento, una elipse o una circunferencia en función del desfase. 
Si este cociente es racional, la curva será cerrada.
Aunque para algunos valores de `a` y `b`pueda parecer abierta, como `a = b = 1` y `a = 3` y `b = 9` con desfase *phi* = 0, 
en realidad la curva se recorre dos veces, en un sentido y otro. 
En cambio si el cociente es irracional, la curva será abierta y densa en el cuadrado `[0, 1] x [0, 1]`, en el sentido de que 
pasa arbitrariamente cerca de cualquier punto contenido en él.
Consulte 
[esta
referencia](https://www.epsilones.com/paginas/articulos/articulos-005-lissajous.html)
si quiere conocer la historia de estas curvas.

Utilice
[esta página](https://academo.org/demos/lissajous-curves/) [2]
interactiva para visualizar la figura cambiando interactivamente los parámetros de la curva.

### La clase *Lissajous*
En esta práctica se propone desarrollar en TypeScript una aplicación web en formato SPA
([Single Page Application](https://en.wikipedia.org/wiki/Single-page_application))
conforme al patrón MVC.
La aplicación posibilitará la visualización en una página web de curvas de Lissajous.

Tenga en cuenta las siguientes especificaciones a la hora de diseñar su programa:

* Haga que el canvas junto con el área de entrada de datos ocupe la mayor parte del viewport de su navegador,
y que no haya que hacer desplazamientos en la página (*scrolling*) para visualizar todo su contenido.

* La curva comenzará a dibujarse automáticamente una vez cagada la página en el navegador, sin esperar por ninguna interacción por parte del usuario.

* Para la actualización del dibujo en el navegador se propone utilizar una aproximación similar a
la que se ha utilizado en el ejemplo del reloj estudiado en clase.
Ello pasa por el uso de un método `update()` cuyo código JS podría ser similar al siguiente:

```ts
  /** Método que actualiza el canvas */
  public update = (): void => {
    ... 
    this.context.clearRect(0, 0, this.canvas.width, this.canvas.height);
    ... /* Dibujar la escena */ 
    requestAnimationFrame(this.update);
  }
```

Consulte la documentación del método
[requestAnimationFrame](https://developer.mozilla.org/en-US/docs/Web/API/Window/requestAnimationFrame).

Esta aproximación no es la única posible y puede Ud. investigar otras si lo desea.

El diseño de su página, que ha de imitar el de la de referencia,
brinda una oportunidad para practicar los elementos HTML y CSS que se han estudiado hasta ahora.
No se pretende que se utilicen elementos no estudiados hasta esta fecha.

### Presentación de resultados
La visualización de la ejecución del programa se realizará a través de una página web alojada
en la máquina IaaS-ULL de la asignatura y cuya URL tendrá la forma:

[1] `http://10.6.129.123:8080/einstein-albert-lissajous.html`

en la que se incustará un lienzo (canvas) para dibujar las curvas.
Sustituya *Albert Einstein* por su nombre y apellido en la URL de su página
y la dirección IP anterior por la correspondiente a su máquina IaaS.

Utilice código HTML y CSS para lograr una página funcional y visualmente correcta,
imitando en lo posible  la apariencia de [2] 
[esta página](https://academo.org/demos/lissajous-curves/)
que se tomará como referencia. 

La página que Ud. diseñe ha de contener el canvas de dibujo de las curvas (área cuadriculada en
la web de referencia y una columna con los campos de texto que permitan introducir valores de los parámetros
(columna derecha en la web [2] de referencia).
En esa columna de la derecha puede Ud. utilizar campos de texto para introducir los valores de los parámetros
de la curva. 
Si lo desea, investigue asimismo cómo incluir *sliders* (a través de la etiqueta '<input>' de HTML) para
modificar los valores de los parámetros usando *sliders* controlados con el ratón.

Se propone además que su página muestre
* Texto explicativo de las curvas de Lissajous
* Enlaces a páginas de referencia que se hayan utilizado para realizar este trabajo.
* Cualquier elemento que les parezca oportuno e interesante

Diseñe asimismo otra página HTML simple 

[3] `http://10.6.129.123:8080/index.html`

que sirva de "página índice" para los ejercicios de la sesión de evaluación de la práctica.
La página [1] será uno de los enlaces de [3] y a su vez [1] tendrá un enlace "Home" que apunte a [3].
Enlace también en la página índice [3] la página que contiene la documentación de su proyecto generada con
Typedoc y también la página 

[4] `http://10.6.129.123:8080/uml.html`

que muestre el diagrama UML de las clases que intervienen en su aplicación.

Haga que todas las páginas de su proyecto ([1], [3], [4]) muestren su nombre y apellidos.

## Referencias
* [Understanding the MVC Pattern with TypeScript](https://medium.com/@alessandro.traversi/understanding-the-mvc-pattern-with-typescript-an-in-depth-analysis-5a5d6f2d61a4)
* [Lissajous Curves](https://academo.org/demos/lissajous-curves/) An interactive demonstration of Lissajous curves
* [TypeDoc](https://typedoc.org/)
* [Google TypeScript Style Guide](https://google.github.io/styleguide/tsguide.html)
* [Google JavaScript Style Guide](https://google.github.io/styleguide/jsguide.html)
* [ESLint](https://eslint.org/)
* [JSDoc](https://jsdoc.app/)
* [PAI Code Examples](https://github.com/ULL-ESIT-PAI-2022-2023/PAI-class-code-examples)
