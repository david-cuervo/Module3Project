# Module3Project

## Introduction
In this project, I have sourced data from the Northwind Database. This database contains the data of a fictional company. Examples of the type of data it includes is employee, shipping, order, and customer data. With this data I answered the following questions: 
Does discount amount have a statistically significant effect on the quantity of a product in an order? If so, at what level(s) of discount?
Does the unit price significantly affect the quantity of product ordered?
Does the shipping region have an effect on the quantity of product ordered?
Does the office where an order was processed have an effect on the quantity of product ordered?
I used my recently learned SQL and hypothesis testing skills to complete this project.

## Cuervo_Mod3Project_Notebook
The notebook located in this repository includes the code that was used to complete this project. Functions were used for exploratory data analysis and for hypothesis testing. Some examples of the code used:

T-Test

`stats.ttest_ind(five_discount['Quantity'], no_discount['Quantity'], equal_var = False)`

Cohen's d
`def Cohen_d(group1, group2):

    diff = group1.mean() - group2.mean()

    n1, n2 = len(group1), len(group2)
    var1 = group1.var()
    var2 = group2.var()
    
    pooled_var = (n1 * var1 + n2 * var2) / (n1 + n2)
    
    d = diff / np.sqrt(pooled_var)
    
    return d
    
Cohen_d(five_discount['Quantity'], no_discount['Quantity']) `

Tukey Test

`from statsmodels.stats.multicomp import pairwise_tukeyhsd`

`tukey_test = pairwise_tukeyhsd(region['Quantity'], region['ShipRegion'] )
tukey_test._results_table`

The notebook also contains several visualizations of the data and their relationships.
Markdown cells include conclusions and communicate the results of the hypothesis tests.

## Executive Summary Presentation
The pdf file in this repository contains the presentation slides for the project. The slides include data visualizations like scatter and box plots. The slides also include explanations of the methodology of the project and communicate the results in easy to understand terms. Key takeaways from the presentation are:

- A 15% discount is the most effective discount to increase quantity in an order
- The unit price does not significantly change the quantity in an order
- Central America and Western Europe had the most significant differences in quantity 
- Employees in every office do not have significant differences in the quantities in their orders



