# Secret of the Polyglot
<b>Categoría:</b> Forense 

<b>Dificultad:</b> Fácil 

## Desarrollo del reto
En este reto se nos proporciona un archivo .pdf con el nombre `flag2of2-final`. Si lo descargamos en nuestro ordenador y lo abrimos, vemos que lo que tenemos es una página en blanco con el texto `1n_pn9_&_pdf_90974127}` escrito casi al final del documento, como puede verse en la figura 1.1. 

Este texto no tiene mucho sentido per sé, siendo la razón por la que, según el texto del reto, te han llamado. Sin embargo, si miramos un poco en detalle lo que dice la frase escrita, vemos que en el texto se pueden diferenciar las palabras `1n`, `pn9` y `pdf`. 

![image](https://github.com/user-attachments/assets/309b7cf8-c728-43ee-b6dc-224dd8718b7b)

Haciendo uso de nuestro conocimiento en la lengua l33t, podemos traducir 1n por In y pn9 por png, de tal manera que la frase nos dice `In png and pdf`, que son 2 extensiones en los cuales se puede crear un archivo. 

Esto, junto con el propio nombre del archivo (flag<b>2of2</b>), ya nos viene a dar toda la información que necesitamos para resolver el reto. La flag está escondida en 2 archivos diferentes: uno en formato .pdf, que es el que nos dan y otro en formato .png, que no tenemos y del cual no sabemos nada. 

La pregunta ahora yace en cómo podemos obtener la otra mitad de la flag, pues no tenemos ningún tipo de archivo de imagen.  

Suponiendo que no dispongamos de un entorno Linux en nuestro ordenador, si en la consola de la plataforma picoCTF escribimos `wget flag2of2-final.pdf`, se descargará el archivo pdf en nuestra carpeta personal de la plataforma y podremos trastear con el archivo cuanto queramos.  

Hacer uso del comando cat arroja una salida un tanto diferente a lo que hemos visto en nuestro lector de pdfs, salida que puede verse en la figura 1.2. Ya la primera línea que se imprime muestra el texto “PNG”, mientras que si seguimos leyendo el galimatías sin sentido que se imprime, podemos leer la frase “Created with GIMP”, el editor de imágenes del sistema Linux. 

![image](https://github.com/user-attachments/assets/c91b70ee-03ba-4aca-9b0c-dfb86c92024a)

Quedándonos ahora claro que estamos tratando con un archivo de imagen, vamos a crear una copia del pdf cambiando su extensión a .png. Para ello basta con hacer `cp flag2of2-final.pdf flag2of2-final.png`, de tal manera que ahora poseeremos una copia en .pdf y una segunda copia en .png.  

* Las distribuciones basadas en Linux permiten transformar los archivos simplemente modificando su extensión a través de un cambio de nombre, una habilidad muy interesante a la hora de trabajar con archivos como este. Sin embargo, creo que una mejor práctica es la de hacer una copia del archivo y modificar esta, pues de esta manera mantengo intacto el original para lo que pueda pasar. Algo que, dicho sea de paso, creo que es importante de cara a preservar la integridad de los datos. Sobre todo, si estamos tratando con una posible prueba de un delito que pudiese ser empleada en un juicio. 

La shell de picoCTF tiene instalado lo mínimo imprescindible para poder hacer uso de esta, pero soluciones como FIM o FEH no son posibles al no estar instaladas, por lo que tenemos que tomar un pequeño desvío de cara a poder ver el contenido de la imagen. Para ello usaremos el comando `sz flag2of2-final.png` para descargar el archivo en nuestro terminal y abrirlo desde este. 

La salida será un pequeño recuadro blanco con el texto `picoCTF{f1u3n7_` escrito. 

Con esto hemos obtenido la otra mitad de la flag y solo nos hace falta unir las dos partes y escribirla en el recuadro del reto, dándolo así por finalizado. 
