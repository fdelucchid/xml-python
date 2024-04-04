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
toxml()
#### `Elemento`
`Element.tagName`  
Devuelve el valor en forma de cadena del nombre del elemento seleccionado  
  
Ej:  
Partiendo del siguiente archivo XML:
[^1]:
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
Mediante el siguiente codigo de python parseamos el documento xml anterior, extraemos el nodo raiz y lo guardamos en una variable. Utilizando tagName podemos mostrar su valor en pantalla el cual se corresponde con el elemento example que es el valor que esperabamos obtener.

![image](https://github.com/fdelucchid/xml-python/assets/152637933/ae698eb5-0ba7-4aed-aed2-aa8d986a0e49)


`getAttribute()`  

#### `Documento`
`documentElement`  
`getElementsByTagName()`  
Este elemento busca todos los descendientes de un elemento particular cuyo nombre indicamos en los paréntesis entre comillas y los guarda en una lista.  
Ej:  
Partiendo del mismo xml anterior  

En este caso parseamos nuevamente el documento y guardamos en una variable la lista resultante del total de personas que en este caso serían 2 como se muestra cuando mostramos en pantalla la longitud de la lista personas.  

![image](https://github.com/fdelucchid/xml-python/assets/152637933/9cca718a-70cb-4a57-b2c4-7602d1fbf8d4)



#### `Nodo`
`firstChild.data`  
## XML
### xpath

---


---
#### Bibliografía:
* [Sintaxis Markdown](https://tutorialmarkdown.com/guia)
* [Definicion y Conceptos de DOM](https://developer.mozilla.org/es/docs/Web/API/Document_Object_Model)
* [Estructura DOM](https://es.javascript.info/dom-nodes#un-ejemplo-del-dom)
* [xml.dom](https://docs.python.org/3/library/xml.dom.html#module-xml.dom)
* [Documentacion DOM](https://www.w3.org/DOM/DOMTR)
	
| Column 1 | Column 2 | Column 3 |
| -------- | -------- | -------- |
| Text     | Text     | Text     |

asdasd
* **Parametros:**
    * **-verb**
    * -noun
