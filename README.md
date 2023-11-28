# Learning R for Behavioral Science
Repository for learning R

## Learning Statistics with R by **Danielle Navarro**

R for Psychological Science
[Learning Statistics with R](https://learningstatisticswithr.com/)

Learning Statistics with Python
[Learning Statistics with Python](https://ethanweed.github.io/pythonbook/landingpage.html)

Power Analysis using R
[A Practical Guide to Statistical Power and Sample Size Calculations in R](https://cran.r-project.org/web/packages/pwrss/vignettes/examples.html#7_Analysis_of_(Co)Variance_(F_Test))



## Different Ways to Specify Contrasts
- options( "contrasts" ) # by defult, it is treatment contrast
- options(contrasts = c("contr.helmert", "contr.poly") # changed the default contrast
- options(contrasts = c("contr.treatment", "contr.poly")

### Setting the contrasts for a single factor
- contrasts( clin.trial$drug ) <- contr.sum(3)
- contrasts( clin.trial$drug)
- contrasts( clin.trial$drug ) <- NULL # wipe the attribute and revert the defaults, use a command like this

### Setting the contrasts for a single factor (recommended)
- my.contrasts <- list( drug = contr.helmert, therapy = contr.helmert )
- mod <- lm( mood.gain ~ drug*therapy, clin.trial, contrasts = my.contrasts )
- mod <- aov( mood.gain ~ drug*therapy, clin.trial, contrasts = my.contrasts )
- car:: Anova(mod, type =3)
- **choice of contrasts does not affect the outcome when you have a balanced design, but, it will have an impact when you have an unbalanced design.** 

Example can be referred to as follows:
[car::Anova in R gives different p-values for TypeII vs TypeIII even though I have a balanced design?](https://stackoverflow.com/questions/68741417/caranova-in-r-gives-different-p-values-for-typeii-vs-typeiii-even-though-i-hav)




