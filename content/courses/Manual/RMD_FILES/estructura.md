R Markdown
----------

    library(rio)
    link="https://github.com/DataPolitica/salidas/raw/master/Data/eda.sav"
    EDA=import(link)

    names(EDA)

    ##  [1] "id"        "region"    "consipol"  "edad"      "intecamp"  "intecampR"
    ##  [7] "clintpre"  "gorepre"   "gbushpre"  "aborto"    "anonac"    "educ"     
    ## [13] "sexo"      "ingresos"  "marital"   "voto96"    "quien96"   "su_ecopas"
    ## [19] "clintpst"  "gorepst"   "gbushpst"  "relig"     "voto00"    "confipol" 
    ## [25] "confipolR" "consipolR"

    class(EDA$confipolR)

    ## [1] "numeric"

    EDA$confipolR=ordered(EDA$confipolR)
    class(EDA$confipolR)

    ## [1] "ordered" "factor"

    levels(EDA$confipolR)

    ## [1] "1" "2" "3"

    levels(EDA$confipolR)<-c("Baja","Media", "Alta")
    levels(EDA$confipolR)

    ## [1] "Baja"  "Media" "Alta"

Note that the `echo = FALSE` parameter was added to the code chunk to
prevent printing of the R code that generated the plot.
