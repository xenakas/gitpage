---
layout: post
title: "Forecasting Economic Aggregates Using Dynamic Component Grouping"
excerpt_separator: "<!--more-->"
categories:
  - Articles
tags:
  - clustering
  - forecasts 
  - hierarchical clustering
  - hierarchical forecasting
---


# [Forecasting Economic Aggregates Using Dynamic Component Grouping](https://mpra.ub.uni-muenchen.de/81585/1/MPRA_paper_81585.pdf)

## Marcus P. A. Cobb

### Abstract

In terms of aggregate accuracy, whether it is worth the effort of modelling a disaggregate process, instead of forecasting the aggregate directly, depends on the properties of the data. Forecasting the aggregate directly and forecasting each of the components separately, however, are not the only options. <!--more-->  This paper develops a framework to forecast an aggregate that dynamically chooses groupings of com- ponents based on the properties of the data to benefit from both the advantages of aggregation and disaggregation. With this objective in mind, the dimension of the problem is reduced by selecting a subset of possible groupings through the use of agglomerative hierarchical clustering. The definitive forecast is then produced based on this subset. The results from an empirical application using CPI data for France, Germany and the UK suggest that the grouping methods can improve both aggregate and disaggregate accuracy.


### Summary 

Favouring forecasting directly is that it would be less affected by disaggregate misspecification, data measurement error and structural breaks. 

An option to improve forecasting performance in this setting, is to work on the modelling and another is to look for data transformations that allow existing models to perform better.

Grouping components together can produce new series with characteristics that differ quite significantly from those of the originating series. In this context, it might be possible to find specific groupings that avoid the problems associated with disaggregate forecasting while still allowing for distinct disaggregate dynamics to be picked up in the process. 

With this objective we develop a two-stage method that combines statistical learning techniques and traditional economic forecasting evaluation. 

In the first stage, we use agglomerative hierarchical clustering to reduce the dimension of the problem by choosing a subset of feasible groupings based on the commonality among the different components. 

In the second stage, we try different selection procedures on the resulting hierarchy to produce the final aggregate forecast. These selection procedures include choosing a single grouping based on some criterion and combining the whole subset of groups.

This suggests that expanding the pool of forecasts by trying different combinations of components with the same forecasting approach may have a similar effect to that of expanding the pool by trying different models.

### Intro 

The usual argument behind using the components to forecast an aggregate is that al- lowing for different specifications across disaggregate variables may capture more pre- cisely the dynamics of a process that becomes too complex through aggregation (Barker and Pesaran, 1990). 

In support of this view, Granger (1990) show that the summing many simple stationary processes can produce a [fractional integrated aggregate](https://www.sciencedirect.com/science/article/pii/S0304407617300428), while Bermingham and D’Agostino (2014) show that the dispersion of the persistence of indi- vidual series has an accelerating effect on the increase of complexity in the aggregate.

Favouring forecasting the aggregate directly is that, in practical applications, it is likely that the disaggregate processes may suffer from **misspecification**. For example, if the disaggregate models neglect that a number of components share common factors, the forecasting errors will tend to cluster having a negative effect on the aggregate forecast (Granger, 1987). The direct aggregate forecast would be less affected by these features in the data and other problems, like those resulting from data measurement error and structural breaks (Grunfeld and Griliches, 1960; Aigner and Goldfeld, 1974).

Ultimately, whether the magnitude of the aggregation error compensates the specification errors in the disag- gregate model depends on the particular forecasting models and data (Pesaran et al., 1989).

The theoretical literature supports using the disaggregate forecasts, or bottom-up ap- proach, but the results in the empirical literature are mixed: *Examples of these comparisons are Espasa et al. (2002), Benalal et al. (2004), Hubrich (2005) and Giannone et al. (2014) for inflation in the Euro area; Bermingham and D’Agostino (2014) for inflation in the U.S. and the Euro area; Marcellino et al. (2003), Hahn and Skudelny (2008), Burriel (2012) and Esteves (2013) for European GDP growth; and Zellner and Tobias (2000), Perevalov and Maier (2010) and Drechsel and Scheufele (2013) for GDP growth in specific industrialized countries.*

An option to improve forecasting performance in this setting, is to work on the model- ling, like Hendry and Hubrich (2011) that include **disaggregate information** in a direct aggregate approach or Bermingham and D’Agostino (2014) that include common factors in a bottom-up approach. Another less obvious way, is to look for **data transformations** that allow existing models to perform better.

Some authors have proposed using **purpose-built groupings** to increase overall fore- casting accuracy, but it would seem that, at least in economic forecasting, it has had little impact (Duncan et al., 2001). A reason for this may be that the number of possible groupings grows exponentially with the number of components meaning that traditional methods, that would usually rely on evaluating all possible outcomes, are really only us- able for problems with relatively few components.2 For larger problems, a different approach becomes necessary.

One that has been relatively successful recently, particularly given the increase in pop- ularity of methods for Big Data, is one that performs grouping conditional on some fea- ture of the original data. *These have been in use for a while in the context of electricity price forecasting (Weron, 2014) and, with the relatively recent surge in computational power, computer intensive methods and availability of high-frequency data, they have expanded to other areas of research. For example, Yan et al. (2013) report significant improvements in the context of wind power prediction, Jha et al. (2015) for inventory planning in retail and Gao and Yang (2014) for forecasting stock market returns.*

**The assumption upon which many of these models are built on, is that by grouping series that behave in a similar way, the idiosyncratic errors within groups will tend to offset each other while the more relevant individual dynamics will be retained to be modelled.**

Although these problems are set in a different context, the purpose of the methods are very similar to those of grouping components to increase the forecasting accuracy of an economic aggregate. They belong, however, to an area of research of statistical learning that has focused almost exclusively on extracting information from very large datasets. **Many relevant economic aggregates, like GDP and CPI, do not fall in this category and it is unclear whether these methods will work with relatively small samples.**

In this context, we develop a method to forecast economic aggregates based on **pur- pose built groupings** of components using statistical learning techniques. The two-stage method consists of trying to find the grouping of components at each point in time that produces the best aggregate forecast. In the first stage, we use agglomerative hier- archical clustering to reduce the dimension of the problem and, in the second, we use a selection procedure on the resulting hierarchy to produce the final aggregate forecast.

### A purpose driven grouping framework for aggregate fore- casting
