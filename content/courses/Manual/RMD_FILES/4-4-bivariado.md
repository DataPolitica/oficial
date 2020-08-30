Punto de partida
----------------

Abrimos la base de datos LAPOP desde nuestro repositorio:

    library(rio)
    link="https://github.com/DataPolitica/salidas/raw/master/Data/sub_lapop.sav"
    lapop=import(link)

Paso 0: Verificamos y configuramos adecuadamente las variables que utilizaremos
-------------------------------------------------------------------------------

    lapop$urbanorural=as.factor(lapop$urbanorural)
    levels(lapop$urbanorural)<-c("Urbano","Rural")
    lapop$sexo=as.factor(lapop$sexo)
    levels(lapop$sexo)<-c("Hombre","Mujer")

1. Entre dos variables categóricas: urbanorural y sexo
------------------------------------------------------

Una vez que hemos identificamos dos variables categóricas lo primeros
que podemos solicitar es una tabla de contingencia.

Ante de seguir te sugiero ver el siguiente tutorial para solicitar
tablas de contigencias:

<iframe width="560" height="315" src="https://www.youtube.com/embed/Scual-o95dI" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen>
</iframe>
Como vimos en el video, podemos pedir tablas de contingencia con la
función `table()`. Hagamos una tabla para las variables *urbanorural* y
*sexo*:

Primero hallemos una tabla de contingencia simple, con sólo las
frecuencias. La llamaremos *tabla1*:

    tabla1 <- table(lapop$urbanorural, lapop$sexo)
    tabla1

    ##         
    ##          Hombre Mujer
    ##   Urbano    687   637
    ##   Rural     434   395

Podemos agregarle los totales marginales escribiendo la siguiente
función `addmargins()`

    addmargins(tabla1)

    ##         
    ##          Hombre Mujer  Sum
    ##   Urbano    687   637 1324
    ##   Rural     434   395  829
    ##   Sum      1121  1032 2153

Ahora, pidamos una tabla de contingencia con porcentaje Tenemos que
hacer referencia a la tabla creada anteriormente y usar el comando
`prop.table()` y lo multiplicamos por 100. La llamaremos *tabla2*:

    tabla2 <- prop.table(tabla1)*100
    tabla2

    ##         
    ##            Hombre    Mujer
    ##   Urbano 31.90896 29.58662
    ##   Rural  20.15792 18.34649

Vemos que nos da los valores totales, pero nosotros queremos sólo los
porcentaje por columna. Para ello, debemos hacer referencia a las
columnas dentro del comando agregando el número 2 (si ponemos 1
aparecerán los porcentaje por filas)

    tabla3 <- prop.table(tabla1, 2)*100
    tabla3

    ##         
    ##            Hombre    Mujer
    ##   Urbano 61.28457 61.72481
    ##   Rural  38.71543 38.27519

Por último, podemos agregarle los totales marginales escribiendo la
siguiente función `addmargins()`

    addmargins(tabla3)

    ##         
    ##             Hombre     Mujer       Sum
    ##   Urbano  61.28457  61.72481 123.00937
    ##   Rural   38.71543  38.27519  76.99063
    ##   Sum    100.00000 100.00000 200.00000

2. Entre una variable numérica y otra categórica: edad y urbanorural
--------------------------------------------------------------------

-   Descriptivos

Para mostrar los descriptivos de una variable numérica según una
variable categórica tenemos que considerar a esta última como grupos. De
esta manera, lo que hacemos en realidad es la comparación de la numérica
entre 2 o más grupos.

Para ello, utilizamos el paquete `psych()`

    library(psych)

Para describir la varible podemos utilizar la función `describeBy()`.
Notemos que primero debemos poner la variable numérica y luego el grupo
de comparación.

Por ejemplo, obtengamos los estadísticos descriptivos de la variable
*Edad* según si la persona pertenece al ámbito rural o urbano
(categórica/grupos):

    describeBy(lapop$edad,group=lapop$urbanorural)

    ## 
    ##  Descriptive statistics by group 
    ## group: Urbano
    ##    vars    n  mean    sd median trimmed   mad min max range skew kurtosis  se
    ## X1    1 1324 37.79 14.59     35   36.51 14.83  18  86    68 0.67    -0.27 0.4
    ## ------------------------------------------------------------ 
    ## group: Rural
    ##    vars   n  mean    sd median trimmed   mad min max range skew kurtosis   se
    ## X1    1 829 36.96 13.68     35   35.84 14.83  18  80    62 0.63    -0.25 0.48

También podemos solicitar un diagrama de cajas o **boxplot** según los
grupos:

    boxplot(lapop$edad~lapop$urbanorural)

![](4-4-bivariado_files/figure-markdown_strict/unnamed-chunk-10-1.png)

3. Entre dos variables numéricas: salario actual y salario inicial
------------------------------------------------------------------

Utilicemos la base de datos *trabajadores*:

    library(rio)
    base_trabajadores="https://github.com/DataPolitica/salidas/raw/master/Data/trabajadores.sav"
    trabajadores=import(base_trabajadores)

Para analizar la relación entre dos variables numéricas es muy común
referirse al gráfico de dispersión.

Para ello, solicitamos el gráfico con la función `plot()`. Entre
paréntesis colocar las dos variables numéricas: el salario inicial y el
salario actual de los trabajadores de una empresa.

    plot(trabajadores$salario_actual, trabajadores$salario_inicial)

![](4-4-bivariado_files/figure-markdown_strict/unnamed-chunk-12-1.png)

Podemos especificar más elementos de nuestro gráfico de dispersión.
Agreguemos título del gráfico y etiquetas de los ejes X e Y:

    plot(trabajadores$salario_actual, trabajadores$salario_inicial, 
         main="Relación entre salario inicial y salario final", 
         xlab="Salario actual", 
         ylab="Salario final")

![](4-4-bivariado_files/figure-markdown_strict/unnamed-chunk-13-1.png)
