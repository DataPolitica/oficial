R Markdown
----------

    library(rio)
    base_trabajadores="https://github.com/DataPolitica/salidas/raw/master/Data/trabajadores.sav"
    trabajadores=import(base_trabajadores)

    dim(trabajadores)

    ## [1] 474  11

    names(trabajadores)

    ##  [1] "id"              "sexo"            "fechnac"         "educ"           
    ##  [5] "catlab"          "salario_actual"  "salario_inicial" "antiguedad"     
    ##  [9] "experiencia"     "minoría"         "directivo"

    str(trabajadores$salario_actual)

    ##  num [1:474] 57000 40200 21450 21900 45000 ...
    ##  - attr(*, "label")= chr "Salario actual"
    ##  - attr(*, "format.spss")= chr "DOLLAR8"
    ##  - attr(*, "display_width")= int 12
    ##  - attr(*, "labels")= Named num 0
    ##   ..- attr(*, "names")= chr "Ausente"

    class(trabajadores)

    ## [1] "data.frame"

    class(trabajadores$salario_actual)

    ## [1] "numeric"

    typeof(trabajadores$salario_actual)

    ## [1] "double"

    x= c(1, 2, 3)
    x

    ## [1] 1 2 3

    class(x)

    ## [1] "numeric"

    y=c("gato", "perro", "loro")
    y

    ## [1] "gato"  "perro" "loro"

    class(y)

    ## [1] "character"

    head(trabajadores)

    ##   id sexo    fechnac educ catlab salario_actual salario_inicial antiguedad
    ## 1  1    1 1952-02-03   15      3          57000           27000         98
    ## 2  2    1 1958-05-23   16      1          40200           18750         98
    ## 3  3    0 1929-07-26   12      1          21450           12000         98
    ## 4  4    0 1947-04-15    8      1          21900           13200         98
    ## 5  5    1 1955-02-09   15      1          45000           21000         98
    ## 6  6    1 1958-08-22   15      1          32100           13500         98
    ##   experiencia minoría directivo
    ## 1         144       0         1
    ## 2          36       0         0
    ## 3         381       0         0
    ## 4         190       0         0
    ## 5         138       0         0
    ## 6          67       0         0

    class(trabajadores)

    ## [1] "data.frame"

    lista= c("gato", "cuy", "puerta")
    class(lista)

    ## [1] "character"

    x= c(4, 7, 9)
    x

    ## [1] 4 7 9

    x[2]

    ## [1] 7

Note that the `echo = FALSE` parameter was added to the code chunk to
prevent printing of the R code that generated the plot.
