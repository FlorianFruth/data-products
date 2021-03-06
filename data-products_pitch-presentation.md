Data Products - Pitch Presentation for Iris ShinyApp
========================================================
author: F. Fruth
date: 2017/01/02
autosize: true

Introduction
========================================================

The Iris ShinyApp project includes this pitch presentation and the App. It was built for the Coursera class Data Products. The ShinyApp "Iris" was created for exploring the Iris dataset. The app can be found here: <https://dfdf.shinyapps.io/iris_app/>. 
The app 
- plots selected variables against each other
- fits a linear model to the selected two variables
- displays the coefficients of the linear model

Code Example
========================================================
Here we see some calculation - fitting a linear model - performed by server.R using the input. As an example, we set input_x and input_y to concrete variables and determine the coefficients of the linear model.


```r
data(iris)
input_x <- iris$Sepal.Length 
input_y <- iris$Sepal.Width
label_x <- "Sepal Length" 
label_y <- "Sepal Width"
model1 <- lm(input_y ~ input_x)
summary(model1)$coeff[c(1,2)]
```

```
[1]  3.4189468 -0.0618848
```

Plot of Sepal Width vs. Sepal Length
========================================================
Here, we plot Sepal Width vs. Sepal Length and display the fitted linear model (blue line).

```r
plot(input_x, input_y, xlab = label_x, ylab = label_y, bty = "n", pch = 16, col = iris$Species); abline(model1, lwd=2, col="blue")
```

![plot of chunk unnamed-chunk-2](data-products_pitch-presentation-figure/unnamed-chunk-2-1.png)



```

```

Summary
========================================================
In this pitch, we presented the Iris ShinyApp, which lets you plot the different variables of the Iris dataset against eachother, fits a linear model and displays the coefficients of the linear model.  
The code for this presentation file can be found here:
<https://github.com/FlorianFruth/data-products/blob/master/data-products_pitch-presentation.Rpres>
