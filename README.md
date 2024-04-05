# **DOM** *(Document Object Model)* :smile:
El **DOM** conecta páginas web a scripts o lenguajes de programación al representar la estructura de un documento, como el HTML que representa una página web, en la memoria. Por lo general, se refiere a JavaScript, aunque el modelado de documentos HTML, SVG o XML como objetos no forma parte del lenguaje principal de JavaScript.

El **DOM** representa un documento con un árbol lógico. Cada rama del árbol termina en un nodo y cada nodo contiene objetos. Los métodos DOM permiten el acceso programático al árbol. Con ellos, puede cambiar la estructura, el estilo o el contenido del documento.

## Ejemplo de representacion de DOM como árbol
El siguiente código sería un formato sencillo de *HTML*
```html
<!DOCTYPE html>
<html>
      <head>
            <title>About elk</title>
      </head>
      <body>The truth about elk.</body>
</html>
```
En **DOM** se representaría de la siguiente manera:  
  
![image](https://github.com/fdelucchid/xml-python/assets/152637933/dfc5e945-93ec-4371-beaf-8ea9320af381)

> El objetivo de la imagen es visualizar la estructura de árbol para entender el concepto y la estructura en si de **DOM**

## **DOM** en *Python*

### **`xml.dom`**
> En nuestro caso no usamos el modulo xml.dom de python en si sino que usamos directamente el modulo xml.dom.minidom el cual explicaré luego, mas allá de eso la teoría que usamos parte de la documentacion de xml.dom y por eso es importante mencionarlo. 

**xml.dom** Es considerado una API (Application Programming Interface) de *DOM* que permite su implementación en *XML* dentro de *Python* para interpretarlo con su estructura de arbol característica e implementar sus métodos y funcionalidades. Ademas de ser una API es un modulo perteneciente a la librería de python

> Todos los elementos de DOM son considerados objetos, a continuacion explicaré los que mas utilizamos. Cabe aclarar que dentro de los objetos existen diferentes grupos o clasificación para los mismos.

### Objetos de DOM que utilizamos:
Partimos del siguiente archivo XML para mostrar los ejemplos:
```xml 
<example>
    <company>OpenAI</company>
    <people>
        <person id="P001">
            <name gender="male">John</name>
            <age>30</age>
            <naixement>1985-11-24</naixement>
        </person>

        <person id="P002">
            <name gender="female">Jane</name>
            <age>21</age>
            <naixement>2002-05-11</naixement>
        </person>
    </people>
</example>
```

#### `Elemento`
`Element.tagName`  
Devuelve el valor en forma de cadena del nombre del elemento seleccionado.  
  
Ej:  

Mediante el siguiente codigo de python parseamos el documento XML anterior, extraemos el nodo raiz y lo guardamos en una variable. Utilizando tagName podemos mostrar su valor en pantalla el cual se corresponde con el elemento example que es el valor que esperabamos obtener.

![image](https://github.com/fdelucchid/xml-python/assets/152637933/ae698eb5-0ba7-4aed-aed2-aa8d986a0e49)


`getAttribute()`
Devuelve el valor del atributo que indicamos entre los paréntesis y entre comillas. Si no existe o si el atributo no tiene valor te devuelve una cadena vacía.  

Ej:  


#### `Documento`
`documentElement`
Se utiliza para obtener el nodo raíz del documento  

Ej:  

En este caso reiteramos para cada persona en la lista de personas que para cada nombre en cada persona la obtención del atributo y así devolver ambos y si hubieran mas personas seguiría siendo válido por lo que es escalable.  

![image](https://github.com/fdelucchid/xml-python/assets/152637933/9434da1f-14b6-494b-be44-6682d73b88ee)

En este caso el nodo raíz seria example el cual guardo en la variable nodoRoot y aprovecho luego a guardar el tagName en otra variable para mostrarlo por consola y que se vea el resultado  

![image](https://github.com/fdelucchid/xml-python/assets/152637933/6c59c5de-ebae-4114-b8a4-c25bd0731614)


`getElementsByTagName()`  
Este elemento busca todos los descendientes de un elemento particular cuyo nombre indicamos en los paréntesis entre comillas y los guarda en una lista.  
Ej:  

En este caso parseamos nuevamente el documento y guardamos en una variable la lista resultante del total de personas que en este caso serían 2 como se muestra cuando mostramos en pantalla la longitud de la lista personas.  

![image](https://github.com/fdelucchid/xml-python/assets/152637933/9cca718a-70cb-4a57-b2c4-7602d1fbf8d4)



#### `Nodo`
`firstChild.data`  
Este elemento refiere al primer hijo del nodo al que hace referencia es un atributo de solo lectura y el punto data se usa cuando queremos obtener el contenido de un nodo de tipo texto devolviendolo como una cadena.  

Ej:  

En este caso accedemos a cada persona y a su primer elemento nombre. Con firstChild accedemos al primer nodo hijo que en este caso es el del texto y con .data extraemos su valor en forma de cadena.  

![image](https://github.com/fdelucchid/xml-python/assets/152637933/2459c13b-e363-45c4-af93-92ad6a41bd0c)

### **`xml.dom.minidom`**  

**xml.dom.minidom** es una implementacion en Python simplificada de DOM para manipular y crear árboles DOM.  

### Implementacion en proyectos:  

Implementar **minidom** en Python consta de 2 lineas para poder comenzar a utilizarlo:
```python
from xml.dom import minidom  
asixDoc = minidom.parse("fichero.xml")
```
1. En la primera línea importamos el modulo **minidom** a nuestro proyecto Python
2. En la segunda línea creamos una variable para parsear el documento XML y poder usar los diferentes objetos que definimos anteriormente

### Objetos de DOM que utilizamos:  

`toxml()`
Este elemento devuelve una cadena que contiene toda la estructura del XML representada por el nodo DOM
  
Ej:  

Como se puede ver simplemente nos devuelve toda la estructura XML del archivo  

![image](https://github.com/fdelucchid/xml-python/assets/152637933/be95be11-60fa-42e2-98a7-fac118a241f0)

---

## **XML** (Extensible Markup Language)  
**XML** es un lenguaje de marcas, un lenguaje de marcas combina datos y etiquetas que las marcan y que contienen información adicional sobre la estructura del texto o su presentación.  
  
> A continuación un ejemplo de XML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<empleados>
  <empleado id="1">
    <nombre>Juan Pérez</nombre>
    <puesto>Desarrollador de software</puesto>
    <salario>50000</salario>
  </empleado>
  <empleado id="2">
    <nombre>Maria González</nombre>
    <puesto>Gerente de Proyecto</puesto>
    <salario>70000</salario>
  </empleado>
</empleados>
```
### Elementos dentro de un *XML*
1. Declaración
   
	La primera línea es la de declaración y se usa para asegurar que los procesadores de XML puedan interpretar correctamente el documento y sus caracteres

	* `?xml` Se utiliza para indicar que es una declaración XML
	* `version="1.0"` Se utiliza para indicar que versión de XML usamos
	* `encoding="UTF-8"` Se utiliza para indicar la codificación de los caracteres dentro del documento
2. Etiquetas
   
	Las etiquetas tienen una estructura muy sencilla se escriben con una jerarquía de arbol y simplemente se incluye un `<` para iniciarla, el texto intermedio y un `>` para cerrarla. Cabe destacar que si creamos una etiqueta debemos cerrarla debajo con en su misma línea de tabulación. Como se puede ver en el ejemplo de empleados el cierre es practicamente igual que el inicio pero incluimos un `/` luego de el simbolo de inicio `<`, el mismo texto y su símbolo de cierre `>`

3. Atributos

	Los atributos se incluyen dentro de las etiquetas y consisten en un nombre y un valor, en ejemplo puede ser el de empleado:

	`<empleado nombreAtributo="valorAtributo">`

## **XSLT** (eXtensible Stylesheet Language Transformations)  
**XSLT** Es un lenguaje para transformar documentos XML en otros documentos XML o en otros tipos de documentos (HTML, texto plano, o en formato XSL-FO). No necesariamente transforma solo XML pero es lo más común. El documento de entrada ya sea el XML o alternativas (C, C++, Java, Python, Perl, Javascript) no se altera, sino que se crea un nuevo documento a partir de el.
Cabe destacar que los navegadores webs más habituales (Safari, Chrome, Firefox, Microsoft Edge, Opera,...) llevan un procesador de XSLT incorporado.

> En nuestro caso solo utilizamos XSLT a partir de XML, a continuacion se muestra una imagen de su funcionamiento  
  
![image](https://github.com/fdelucchid/xml-python/assets/152637933/19486223-defa-4b68-b5a0-73e30c6d06c2)

### **XPATH**
Antes de explicar los elementos de XSLT es importante enteder **XPATH** ya que lo usaremos en conjunto con los mismos. **XPATH** es un lenguaje que se utiliza para navegar por los elementos XML.  
* Define 7 tipos de nodos posibles:
  
	* Nodo raíz 
	* Elementos 
	* Atributos
  	* Text
  	* Espacio de nombres
  	* Comentarios

> Ejemplo de XML para la siguiente explicación
  
```xml
<botiga>
        <bluray>
                <titol idioma=“català”>Avatar</titol>
                <director>J. Cameron</director>
                <preu>21</preu>
                <any>2009</any>
	</bluray>
</botiga>
```
  
| Expresión | Descripción |
| ----------- | ----------- |
| Nombre del nodo | Indica todos los hijos del nombre del nodo |
| / | Indica el elemento raíz |
| // | Indica todos los elementos del documento |
| . | Indica el nodo actual |
| .. | Indica el padre del nodo |
| @ | Indica el atributo |  

> Ejemplos sobre botiga con lo mencionado
  
| Expresión | Descripción |
| ----------- | ----------- |
| botiga | Indica todos los hijos del nombre de botiga |
| / | Indica el elemento botiga |
| botiga/bluray | Indica todos los elementos hijos de botiga que se llamen bluray |
| //bluray | Indica todos los elementos bluray del documento |
| botiga//bluray | Indica todos los elemento bluray descendientes de botiga |
| //@idioma | Indica todos los atributos idioma |

  
---
#### Bibliografía:
* [Sintaxis Markdown](https://tutorialmarkdown.com/guia)
* [Definicion y Conceptos de DOM](https://developer.mozilla.org/es/docs/Web/API/Document_Object_Model)
* [Estructura DOM](https://es.javascript.info/dom-nodes#un-ejemplo-del-dom)
* [xml.dom](https://docs.python.org/3/library/xml.dom.html#module-xml.dom)
* [Documentacion DOM](https://www.w3.org/DOM/DOMTR)
* [xml.dom.minidom](https://docs.python.org/es/3/library/xml.dom.minidom.html)
* [Implementación minidom](https://docs.google.com/presentation/d/1RKl8dxmj_kwhCjW6GgQgRkpMt-mF62xMGLmMGdqeLn8/edit#slide=id.g2b5ce68c467_0_33)
* [Introduccion XML](https://drive.google.com/file/d/1kAUJYKPGADg22361tDcBYGchnbiCaQWt/view)
* [Introduccion XSLT](https://drive.google.com/file/d/1DPOCh9ivLsYqKHWN2exdTVY96LhhdoOS/view)
* [Introduccion XPATH](https://drive.google.com/file/d/1EPZ_1F3WSPUh172alCskraO7mATTPQMD/view)
