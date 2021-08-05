# Completely-Randomized-Experimental-Design

Experimental Design, when do you call an experimental design a randomized design?

Experimental designs in which the treatments are allocated randomly to the experimental units that come under the category of randomized designs.

Randomized designs are classified as completely randomized design, randomized block design, Latin square design, split pot design, cross over design, family block design, etc…

Completely Randomized Design

In this tutorial, we are discussing characteristics of the completely randomized design.

Any experimental design, in general, is characterized by the nature of the grouping of experimental units and the manner the treatments are randomly allocated to the experimental units.

A completely randomized design is the one in which all the experimental units are taken in a single group that is homogeneous as far as possible.

Will take one or two examples for the understanding purpose.

For example, all the field plots taking treatments are having the same type of soil, fertility, soil depth, soil texture, soil temperature, soil moisture, etc…

In another example like all the cows forming a group are of the same breed, same age, same weight, same lactation, etc…

Suppose there are k treatments and the treatments Ti is replicated ri times. So we require i=1 to k, Sum of ri=n units. Assign K treatments randomly to n experimental units such that the treatment Ti occupies ri units or plots. Such a type of design is called a completely randomized design.

The completely randomized design also known as the non-restriction design.

When a completely randomized design more suitable?

For laboratory experiments, pot experiments, greenhouse experiments, and sometimes animal experiments.

Suppose there are four treatments P1, P2, P3, P4 which are replicated 4, 3, 3, and 5 times respectively.

Then the layout of the completely randomized design having 15 plots and 4 treatments.

Experimental Design
P2	P2	P2
P3	P4	P3
P4	P4	P1
P1	P1	P1
P3	P4	P4
The merits of completely randomized designs are

    Its layout is very easy
    Complete flexibility in the design
    The whole experimental material can be utilized
    The design yield maximum degrees of freedom for experimental error.
    Missing values does not break any assumption of analysis of variance.
    Suitable for a small number of treatments.

Let’s take an example of how to execute a completely randomized design in R.


Following design we are taking 3 treatments and number of subjects is 10. So total experimental unit is 30.

set.seed(325)
f = c("Ctrl", "Trt1", "Trt2")   # Different Treatment Levels
k = 3                    # Total Number of Treatment Levels
n = 10                    # Total subjects per treatment
response<-sample(1:20,30,replace=T)#Reponse from the subjects
tm<-gl(k, 1, n*k, factor(f))
av<-aov(response ~ tm)
summary(av)

Results           

Df Sum Sq Mean Sq F value Pr(>F)
tm           2   58.2    29.1   0.827  0.448
Residuals   27  950.5    35.2    

Conclusion

Since the p-value of 0.448 is greater than the .05 significance level, we do not reject the null hypothesis, which indicates no significant difference was observed between tested treatments.
