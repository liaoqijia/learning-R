# Learning R for Behavioral Science
Repository for learning R

## Learning Statistics with R

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
options( "contrasts" ) # by defult, it is treatment contrast
options(contrasts = c("contr.helmert", "contr.poly") # changed the default contrast
options(contrasts = c("contr.treatment", "contr.poly")
```

### Setting the contrasts for a single factor
```
contrasts( clin.trial$drug ) <- contr.sum(3)
contrasts( clin.trial$drug)
contrasts( clin.trial$drug ) <- NULL # wipe the attribute and revert the defaults, use a command like this
```

### Setting the contrasts for a single factor (recommended)
```
my.contrasts <- list( drug = contr.helmert, therapy = contr.helmert )
mod <- lm( mood.gain ~ drug*therapy, clin.trial, contrasts = my.contrasts )
mod <- aov( mood.gain ~ drug*therapy, clin.trial, contrasts = my.contrasts )
car:: Anova(mod, type =3)
mod$contrasts  #if you want to check that it has actually worked, you can inspect the value of `mod$contrasts`.
#choice of contrasts does not affect the outcome when you have a balanced design, but, it will have an impact when you have an unbalanced design.
```
Example can be referred to as follows: :bangbang:
* [car::Anova in R gives different p-values for TypeII vs TypeIII even though I have a balanced design?](https://stackoverflow.com/questions/68741417/caranova-in-r-gives-different-p-values-for-typeii-vs-typeiii-even-though-i-hav)

* [Factorial ANOVA 3- Unbalanced Designs](https://stats.libretexts.org/Bookshelves/Applied_Statistics/Learning_Statistics_with_R_-_A_tutorial_for_Psychology_Students_and_other_Beginners_(Navarro)/16%3A_Factorial_ANOVA/16.10%3A_Factorial_ANOVA_3-_Unbalanced_Designs)

## Using the `afex` R package (Analysis of Factorial Experiments) for ANOVA:
`afex` R package is the go-to package for anova analysis, because you don't have to specify the contrast option as discussed above, it yields effect size; it can handle between-subjects design, within-subjects design, and mixed-design.  
* [Using the `afex` R package for ANOVA](https://tysonbarrett.com/jekyll/update/2018/03/14/afex_anova/)
* [Traditional ANOVA by Andy Wills](https://www.andywills.info/rminr/more-on-anova.html#:~:text=The%20aov_car%20command%20for%20this,Error(subj%2Fcongru)%20.)
* Online collection of tutorials was created by graduate students in psychology as a resource for other experimental psychologists interested in using R for statistical analyses and graphics:
* * [Between-Subjects ANOVA in R](https://ademos.people.uic.edu/Chapter20.html)
  * [ANOVA (afex): Within Subjects and Mixed Designs](https://ademos.people.uic.edu/Chapter21.html)

## ANOVA Analysis. I only list one-way and two-way anova analysis here, for more complex design, refer to the link below for details.
### Follow Up to One-way ANOVAs, including Post-Hoc Analysis
- [Follow Up to One-way ANOVAs](https://www.alexanderdemos.org/ANOVA6.html)

### Following up the Two-Way ANOVA, including Post-Hoc Analysis
- [Following up the Two-Way ANOVA](https://www.alexanderdemos.org/ANOVA9.html#Planned_Comparisons_of_Interaction)

## My favorite R packages for summarizing and visualizing data. There are alternatives that offer simpler approaches to data visualization.
- Data and Model Summaries in R with `modelsummary` R package
- [Data and Model Summaries in R](https://modelsummary.com/)

- `ggpubr`: ggplot2 Based Publication Ready Plots (I use it almost everyday)
- [ggpubr](https://rpkgs.datanovia.com/ggpubr/index.html#ggpubr-ggplot2-based-publication-ready-plots)

- `ggstatsplot`: ggplot2 Based Plots with Statistical Details
- [ggstatsplot](https://indrajeetpatil.github.io/ggstatsplot/)

- `ganttrify` facilitates the creation of nice-looking Gantt charts
- [ganttrify](https://github.com/giocomai/ganttrify)

## Mediation Analysis with Hayes' Process in R
The popular method for mediation analysis in marketing (consumer behavior) is Hayes' Process. You can also use `mediation` package in case it is the default method in your field.

* PROCESS macro for SPSS, SAS, and R
- [Download Address](https://haskayne.ucalgary.ca/CCRAM/resource-hub)
- [R syntax for Process](http://www.regorz-statistik.de/en/mediation_process_for_r.html)
- How to install Process in R

```
Download the process syntax and save it to your working directory
setwd()
for example: setwd(dir = "/Users/nphillips/Dropbox/yarrr")

use source function to read the process syntax
source(file = "/Users/nphillips/Dropbox/yarrr/Process.R")

now you can use the Process in your RStudio, just like anyother R package.
process (data = my_data_frame, y = "my_DV", x = "my_IV", m ="my_mediator", model = 4)
```


## Youtube tutorials of learning R (If you learn how to use tidyverse, you learn R!!!)
- Official cheatsheet for data wrangling:
[Data Wrangling with dplyr and tidyr](https://www.rstudio.com/wp-content/uploads/2015/02/data-wrangling-cheatsheet.pdf)

- Introduction to the tidyverse by Andrew Heiss
  [Introduction to the tidyverse](https://talks.andrewheiss.com/2021-seacen/01-tidyverse.html)

- Data wrangling with R in 27 minutes
[Data wrangling with R in 27 minutes](https://www.youtube.com/watch?v=oXImkptBpqc&t=4s)

- Stat 412: R Programming by Kelsey Gonzalez
[Stat 412](https://www.youtube.com/playlist?list=PL6FsZxVq54ERrlMRNE5aq2qUFH042fbuM)

## A Reproducible Data Analysis Workflow With R Markdown, Git, Make, and Docker
In this tutorial, we describe a workflow to ensure long-term reproducibility of R-based data analyses. The workflow leverages established tools and practices from software engineering. It combines the benefits of various open-source software tools including R Markdown, Git, Make, and Docker, whose interplay ensures seamless integration of version management, dynamic report generation conforming to various journal styles, and full cross-platform and long-term computational reproducibility. The workflow ensures meeting the primary goals that 1) the reporting of statistical results is consistent with the actual statistical results (dynamic report generation), 2) the analysis exactly reproduces at a later point in time even if the computing platform or software is changed (computational reproducibility), and 3) changes at any time (during development and post-publication) are tracked, tagged, and documented while earlier versions of both data and code remain accessible. While the research community increasingly recognizes dynamic document generation and version management as tools to ensure reproducibility, we demonstrate with practical examples that these alone are not sufficient to ensure long-term computational reproducibility. Combining containerization, dependence management, version management, and dynamic document generation, the proposed workflow increases scientific productivity by facilitating later reproducibility and reuse of code and data.
[URL Linke](https://qcmb.psychopen.eu/index.php/qcmb/article/view/3763)


## Track website visitors from all over the world
<script type='text/javascript' id='clustrmaps' src='//cdn.clustrmaps.com/map_v2.js?cl=ffffff&w=150&t=tt&d=YzQOP_fBsDlkAZUgID6y2FwJQmaKEWATTkzl1Mkb1KI&co=2d78ad&cmo=3acc3a&cmn=ff5353&ct=ffffff'></script>
