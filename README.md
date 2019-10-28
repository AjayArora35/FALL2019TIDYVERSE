# CUNY DATA 607 Fall 2019 Tidyverse recipes

# Creating graphs using ggplot2
# Background
  2 files: Data 607 TidyVerse.RMD and all-ages.csv
  This project uses 2 files identified on the previous line.  The RMD file contains 10 different examples using ggplot2 from Tidyverse package.  In addition, a data file named (all-ages.csv) is used to provide graphing data.

# Example 1: 
  1.Initial ggplot 

  ```{r}
  # A simple histogram using ggplot on Employed field
  library(ggplot2)
  ggplot(allages, aes(x = allages$Employed)) 
  ```
  Discussion: 
  A blank ggplot is drawn. Even though the x and y are specified, there are no points or lines in it. This is because,  ggplot doesn't assume that you meant a scatterplot or a line chart to be drawn. I have only told ggplot what dataset to use and what columns should be used for X and Y axis. I haven't explicitly asked it to draw any points.

Also note that aes() function is used to specify the X and Y axes. That's because, any information that is part of the source dataframe has to be specified inside the aes() function.  

# Example 2: 
  2. How to Make a Simple Histogram Plot Aesthetic Mapping

  In ggplot land aesthetic means "something you can see". Examples include:

    position (i.e., on the x and y axes)
    color ("outside" color)
    fill ("inside" color)
    shape (of points)
    linetype
    size
    
    ```{r}
    # A simple histogram using ggplot on Employed field
    library(ggplot2)
    ggplot(allages, aes(x = allages$Employed)) + geom_histogram()
    ```    
  Discussion: 
    Each type of geom accepts only a subset of all aesthetics-refer to the geom help pages to see what mappings each geom accepts. Aesthetic mappings are set with the aes() function.
    
# Example 3:
  3. A histogram with adjustment for binning. (bin width)
```{r}
    # A simple histogram using ggplot on Employed field
    library(ggplot2)
    ggplot(allages, aes(x = allages$Employed)) + geom_histogram(stat = "bin", binwidth=4000)
    ```
  Discussion:
    Discretizes all numerical data in a data frame into categorical bins of equal length or content or based on automatically determined clusters.

# Example 4:
  4. Geometric objects with ggplots 
  Geometric objects are the actual marks we put on a plot. Examples include:

    points (geom_point, for scatter plots, dot plots, etc)
    lines (geom_line, for time series, trend lines, etc)
    boxplot (geom_boxplot, for, well, boxplots!)

    A plot must have at least one geom; there is no upper limit. You can add a geom to a plot using the + operator
    ```{r}
    #A scatter plot of college major Category and Employed
    ggplot(allages,
           aes(x=allages$Employed,
               y=allages$Major_category
               ))+
      geom_point()

    ```
  Discussion:
    
