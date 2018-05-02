# Assignment-3.5
1. Import the Titanic Dataset from the link Titanic Data Set.
Perform the following:
a. Is there any difference in fares by different class of tickets?
Note - Show a boxplot displaying the distribution of fares by class

            library(titanic)
            library(ggplot2)
            titanic_train$Pclass=as.factor(titanic_train$Pclass)
            fill &lt;- &quot;#4271AE&quot;
            line &lt;- &quot;#1F3552&quot;
            boxplot_tit_fare_class=
            ggplot(data = titanic_train,aes(titanic_train$Pclass,titanic_train$Fare))+ geom_boxplot(fill=fill,
            colour=line)+ scale_y_continuous(breaks = seq(0,200,10), limits=c(0,200), name = &quot;Fare range based on
            class&quot;) + scale_x_discrete(name = &quot;Class of Tickets&quot;) + ggtitle(&quot;Fare charged on the basis of ticket                    class&quot;)

b. Is there any association with Passenger class and gender?
Note – Show a stacked bar chart

        count= table(titanic_train$Sex,titanic_train$Pclass)
        cols = c(&quot;hotpink4&quot; , &quot;royalblue&quot;)
        barplot(count, col = cols, legend.text = TRUE,beside = FALSE, main = &quot;Gender vs Class&quot;, xlab = &quot;Pclass&quot;,
        ylab=&quot;gender&quot;, args.legend = list(x = &quot;topleft&quot;))
