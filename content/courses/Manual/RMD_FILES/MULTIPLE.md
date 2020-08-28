R Markdown
----------

    library(rio)
    base_trabajadores="https://github.com/DataPolitica/salidas/raw/master/Data/trabajadores.sav"
    trabajadores=import(base_trabajadores)
    attach(trabajadores)

    names(trabajadores)

    ##  [1] "id"              "sexo"            "fechnac"         "educ"           
    ##  [5] "catlab"          "salario_actual"  "salario_inicial" "antiguedad"     
    ##  [9] "experiencia"     "minoría"         "directivo"

    modelo2=lm(salario_actual~salario_inicial + educ + antiguedad, data=trabajadores)
    summary(modelo2)

    ## 
    ## Call:
    ## lm(formula = salario_actual ~ salario_inicial + educ + antiguedad, 
    ##     data = trabajadores)
    ## 
    ## Residuals:
    ##    Min     1Q Median     3Q    Max 
    ## -30325  -4231   -658   2924  46707 
    ## 
    ## Coefficients:
    ##                   Estimate Std. Error t value Pr(>|t|)    
    ## (Intercept)     -1.999e+04  3.237e+03  -6.175 1.43e-09 ***
    ## salario_inicial  1.689e+00  5.783e-02  29.209  < 2e-16 ***
    ## educ             9.661e+02  1.579e+02   6.118 2.00e-09 ***
    ## antiguedad       1.557e+02  3.506e+01   4.442 1.11e-05 ***
    ## ---
    ## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
    ## 
    ## Residual standard error: 7646 on 470 degrees of freedom
    ## Multiple R-squared:  0.8008, Adjusted R-squared:  0.7995 
    ## F-statistic: 629.7 on 3 and 470 DF,  p-value: < 2.2e-16

    modelo2$coefficients

    ##     (Intercept) salario_inicial            educ      antiguedad 
    ##    -19986.50217         1.68916       966.10701       155.70118

Note that the `echo = FALSE` parameter was added to the code chunk to
prevent printing of the R code that generated the plot.
