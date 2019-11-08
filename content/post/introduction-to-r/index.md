---
authors:
- admin
categories:
- UCD_CodeClub
date: "2019-10-08T01:00:00Z"
draft: false
featured: true
image:
  caption: '[*Image from r4ds.had.co.nz/data-visualisation*](https://r4ds.had.co.nz/data-visualisation.html)'
  focal_point: ""
  placement: 1
  preview_only: false
lastmod: "2019-10-08T01:00:00Z"
projects: []
subtitle: 'Learn the basics of R'
summary: Learn the basics of R
tags:
- R
- RStudio
- UCD_CodeClub
title: 'Introduction to R'
---

Adapted from [notes](https://hackmd.io/q9Iic3qFQe2y8F9RfBY0Lg "See notes") I prepared for [UCD_CodeClub.](https://ucdcodeclub.github.io/ "See website")

If you have not already installed R and RStudio, follow this [guide.]({{< ref "/post/install-r-and-rstudio/index.md" >}} "See guide")

Open RStudio and you should see something like this:

![](https://i.imgur.com/Rt9vCRn.jpg)

Code is entered into the console, plots etc. are shown in the output. 

[![](https://d33wubrfki0l68.cloudfront.net/9a23d664f0f49bc2ef8e78bed6277dd48bd2b96d/af132/diagrams/rstudio-console.png)*Image from r4ds.had.co.nz/introduction*](https://r4ds.had.co.nz/introduction.html)

The intial message in the console contains the version number and nickname (which is usually a reference to [Peanuts](https://livefreeordichotomize.com/2017/09/28/r-release-names/) cartoons). `Ctrl + L` can be used to clear the console.

[R](https://www.r-project.org/about.html) is a statistical programming language, so it can be used like a calulator. Try entering the following commands:  
`2 + 2` returns the answer `4`  
`x <- 1` sets the variable `x` equal to `1`, entering `x` returns the value `1`  
`y <- 2`  
`x + y` returns the value `3`  
R has functions built in to allow more complicated calculations, for example square roots:   `sqrt(10)` returns `3.162278`  
`sqrt(y)` returns `1.414214`  
`sqrt()` returns an error: `Error in sqrt() : 0 arguments passed to 'sqrt' which requires 1` This is because the `sqrt` requires an input.  
`?sqrt()` or `help(sqrt)` can be used to find information about functions.

Packages can be used to add more functions to R. We will be using the [Tidyverse](https://www.tidyverse.org/) collection of packages. These can be installed by entering `install.packages("tidyverse")` and loaded for use using `library(tidyverse)`. This includes [ggplot2,](https://ggplot2.tidyverse.org/) which makes plots based on a layered [grammar of graphics.](http://vita.had.co.nz/papers/layered-grammar.pdf)

Following [R for Data Science](https://r4ds.had.co.nz/) section 3: [Data visualisation](https://r4ds.had.co.nz/data-visualisation.html) we used the following commands:  
`ggplot2::mpg` to see the practice data set  
`head(ggplot2::mpg)` to see the first 6 rows  
`?ggplot2::mpg` to find more information  
`ggplot(data = mpg)` to make a blank plot  
`ggplot(data = mpg) + geom_point(mapping = aes(x = displ, y = hwy))` to make a dot plot:  
[![](https://d33wubrfki0l68.cloudfront.net/9f135433aca5356d04e503887ebab7d475a5f1cd/d33d1/visualize_files/figure-html/unnamed-chunk-4-1.png)*Image from r4ds.had.co.nz/data-visualisation*](https://r4ds.had.co.nz/data-visualisation.html)

To compare we can look a similar data set and made a plot using base R:  
`data("mtcars")` to load the data set   
`head(mtcars)` to see the first 6 rows  
`plot(mtcars$cyl, mtcars$mpg)` to make the plot:  
![](https://i.imgur.com/CY2PzFW.png)

As shown in this [gallery,](http://r-statistics.co/Top50-Ggplot2-Visualizations-MasterList-R-Code.html#top) ggplot can be used to make many different types of graphs. For example:  
`ggplot(mpg, aes(class, cty)) + geom_violin() + labs(title="Violin plot", subtitle="City Mileage vs Class of vehicle", caption="Source: mpg", x="Class of Vehicle", y="City Mileage")`
       
[![](http://r-statistics.co/screenshots/ggplot_masterlist_28.png)*Image from r-statistics.co/Top50-Ggplot2-Visualizations-MasterList-R-Code*](http://r-statistics.co/Top50-Ggplot2-Visualizations-MasterList-R-Code.html#top)


