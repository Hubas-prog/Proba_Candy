## Experiment

to be continued

## Packages

``` r
library(ggplot2)
```

    ## Warning: package 'ggplot2' was built under R version 4.2.3

## Custom function

``` r
make_my_MMs_plot <- function(p=0.15) {
  nbrB<-c(0:5)
  Cnx<-c(1,5,10,10,5,1)
  probB<-NULL
  for(i in 1:6) {
    probB[i]<-Cnx[i]*p^nbrB[i]*(1-p)^(5-nbrB[i])
  }
  dataMMs<-data.frame(nbrB=factor(nbrB),
                      prob=probB)
  ggplot(dataMMs,aes(x=nbrB,
                     y=probB))+
    geom_bar(stat = "identity",
             col="#4058F5",
             fill="#4058F5")+
    ylab("Probability")+
    xlab("X (nbr of blue M&M's)")+
    ggtitle(paste("p=",p))+
    theme_bw(base_size = 14)
}
```

## Plot

``` r
make_my_MMs_plot(p=0.15)
```

![](Proba_Candy_files/figure-markdown_github/unnamed-chunk-3-1.png)
