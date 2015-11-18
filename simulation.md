# Simulation on Exponential Distribution
Rhyz C. Gomez  

## OVERVIEW OF THE REPORT
This paper investigates the exponential distribution and shows how the distribution of averages of 40 exponentials is approximately normal. Further, the paper reveals that the sample mean and sample variance are good approximates to the theoretical mean and theoretical variance of the exponential distribution. 


## THE EXPONENTIAL DISTRIBUTION  
The **Exponential distribution** is a continuous probability distribution arises naturally when events occur continuously and independently at a constant average rate.  

The probability density function (pdf) of an exponential distribution has the form

$$f(x;lambda) = lambda*e^(-lambda*x), when x >=0,$$
$$f(x;lambda) = 0, when x < 0$$ 
where lambda is the rate parameter

The mean or expected value of an exponentially distributed random variable X is 

$$E[X] = 1/lambda$$

and the variance of X is given by

$$Var[X] = 1/(lambda)^2$$

You can read more about Exponential Distribution at [wikipedia](https://en.wikipedia.org/wiki/Exponential_distribution).

Here, we will investigate the distribution of averages of 40 exponentials and compare it with the Central Limit Theorem. The lambda will be set at 0.2. 


```r
lambda <- 0.2
meanExp <- sdExp <- 1/lambda
varExp <- (sdExp)^2
```

Thus, the theoretical mean of an exponential distribution with lambda equal to 0.2 is 5 and the theoretical variance is 25.

## SIMULATION



```r
set.seed(1)
simulation <- 1000
```

## SAMPLE MEAN VS THEORETICAL MEAN


## SAMPLE VARIANCE VS THEORETICAL VARIANCE



## DISTRIBUTION

The distribution of averages of exponentials is approximately normal. To illustrate this, we simulate 1000 averages of 40 exponentials using the for loop function and use the hist() function to plot the averages. 


```r
set.seed(1)
expn = NULL
for (i in 1 : 1000) expn = c(expn, mean(rexp(40,0.2)))
hist(expn,density=30,prob=TRUE, main ="Distribution of Averages of 40 Exponentials",xlab="Average",col="turquoise",sub="1000 simulation",font.lab=2)
curve(dnorm(x,mean=mean(expn),sd=sd(expn)),lwd=3,col="limegreen",add=TRUE,yaxt="n")
```

<img src="simulation_files/figure-html/distribution-1.png" title="" alt="" style="display: block; margin: auto;" />

In the figure above, it can easily be concluded that the distribution is approximately normal.


\newpage

###APPENDIX A
