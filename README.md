# Learning R for Behavioral Science
Repository for learning R

## Learning Statistics with R by **Danielle Navarro**

R for Psychological Science
[Learning Statistics with R](https://learningstatisticswithr.com/)

Learning Statistics with Python
[Learning Statistics with Python](https://ethanweed.github.io/pythonbook/landingpage.html)

Power Analysis using R
[A Practical Guide to Statistical Power and Sample Size Calculations in R](https://cran.r-project.org/web/packages/pwrss/vignettes/examples.html#7_Analysis_of_(Co)Variance_(F_Test))

R for applied epidemiology and public health (A great book) :fire:
[R for applied epidemiology and public health](https://epirhandbook.com/en/index.html)

Discovering Statistics Using R and RStudio (2nd edition)
[Discovering Statistics Using R and RStudio (2nd edition)](https://www.discovr.rocks/discovr/)


## Different Ways to Specify Contrasts
```
* options( "contrasts" ) # by defult, it is treatment contrast
* options(contrasts = c("contr.helmert", "contr.poly") # changed the default contrast
* options(contrasts = c("contr.treatment", "contr.poly")
```

### Setting the contrasts for a single factor
```
* contrasts( clin.trial$drug ) <- contr.sum(3)
* contrasts( clin.trial$drug)
* contrasts( clin.trial$drug ) <- NULL # wipe the attribute and revert the defaults, use a command like this
```

### Setting the contrasts for a single factor (recommended)
```
* my.contrasts <- list( drug = contr.helmert, therapy = contr.helmert )
* mod <- lm( mood.gain ~ drug*therapy, clin.trial, contrasts = my.contrasts )
* mod <- aov( mood.gain ~ drug*therapy, clin.trial, contrasts = my.contrasts )
* car:: Anova(mod, type =3)
* mod$contrasts  #if you want to check that it has actually worked, you can inspect the value of `mod$contrasts`.
#choice of contrasts does not affect the outcome when you have a balanced design, but, it will have an impact when you have an unbalanced design.
```
Example can be referred to as follows::bangbang:
* [car::Anova in R gives different p-values for TypeII vs TypeIII even though I have a balanced design?](https://stackoverflow.com/questions/68741417/caranova-in-r-gives-different-p-values-for-typeii-vs-typeiii-even-though-i-hav)

* [Factorial ANOVA 3- Unbalanced Designs](https://stats.libretexts.org/Bookshelves/Applied_Statistics/Learning_Statistics_with_R_-_A_tutorial_for_Psychology_Students_and_other_Beginners_(Navarro)/16%3A_Factorial_ANOVA/16.10%3A_Factorial_ANOVA_3-_Unbalanced_Designs)

## ANOVA Analysis. I only list one-way and two-way anova analysis here, for more complex design, refer to the link below for details.
### Follow Up to One-way ANOVAs, including Post-Hoc Analysis
[Follow Up to One-way ANOVAs](https://www.alexanderdemos.org/ANOVA6.html)

### Following up the Two-Way ANOVA, including Post-Hoc Analysis
[Following up the Two-Way ANOVA](https://www.alexanderdemos.org/ANOVA9.html#Planned_Comparisons_of_Interaction)

## My favourite R packages for summarize data and visualize data (I hate ggplot, there is always easy ways of visualizing data).
Data and Model Summaries in R with `modelsummary` R package
[Data and Model Summaries in R](https://modelsummary.com/)

`ggpubr`: ggplot2 Based Publication Ready Plots (I use it almost everyday)
[ggpubr](https://rpkgs.datanovia.com/ggpubr/index.html#ggpubr-ggplot2-based-publication-ready-plots)

`ggstatsplot`: ggplot2 Based Plots with Statistical Details
[ggstatsplot](https://indrajeetpatil.github.io/ggstatsplot/)

## Youtube tutorials of learning R
* Official cheatsheet for data wrangling:
[Data Wrangling with dplyr and tidyr]([data-wrangling-cheatsheet.pdf](https://www.rstudio.com/wp-content/uploads/2015/02/data-wrangling-cheatsheet.pdf))

* Data wrangling with R in 27 minutes
[Data wrangling with R in 27 minutes](https://www.youtube.com/watch?v=oXImkptBpqc&t=4s)

* Stat 412: R Programming by Kelsey Gonzalez
[Stat 412](https://www.youtube.com/playlist?list=PL6FsZxVq54ERrlMRNE5aq2qUFH042fbuM)

