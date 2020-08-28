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

Note that the `echo = FALSE` parameter was added to the code chunk to
prevent printing of the R code that generated the plot.
