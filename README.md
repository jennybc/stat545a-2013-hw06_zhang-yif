stat545a-2013-hw06_zhang-yif
============================
The originial dataset is from [here](http://archive.ics.uci.edu/ml/machine-learning-databases/adult/adult.data). This is a census income dataset used to determine whether a person makes over 50K a year based on several factors.
This originial dataset has 48842 observations and 15 variables, age, work class, final weight, education, education year, merital status, occupation, relationship, race, sex, capital gain, capital loss, hours per week, native country, and income.

To get my dataset `income.tsv`, I randomly selected 1222 observations and droped 4 variables, marital status, relationship, race, and native country. (These steps are not shown in my Rscripts.)
The first 2 of my Rscripts `01_dataClean.R` and `02_filterReorder.R` are for data cleaning and sorting, in which I get the `income_clean1.tsv` and
`income_clean2.tsv` seperately. My cleaned data has 1035 observations and 6 variables, sex, age, occupation, hours per week, income and cens(
1 indicates income > 50K, 0 indicates income <= 50K). 

In the third Rscript `03_dataAggregate.R`, I applied the logistic regression model to the 
census income on hours per week. I am interested in how the working hours will affect the income for different occupations within the age
levels, young, middle aged, and senior. From the `stripplot_ageHourByIncome.png`, we can see there are only 2 observations of young people that have
income greater than 50K. But since there are a lot of observations in young, I don't want to remove the observations of young. 
Therefore, the `stripplot_incomeByHours_Young.png` does not look very nice. from `stripplot_incomeByHours_MiddleAged.png`
and `stripplot_incomeByHours_Senior.png`, we can see that more working hours lead to greater income for both middle aged and senior sales people.
While for other occupations, the observations don't suggest strong relationship between working hours and income.

   * Download the following files into an empty directory:
-    - Input data: [`income.tsv`](https://github.com/dora7870/stat545a-2013-hw06_zhang-yif/blob/master/data/income.tsv) 
-    - Scripts: [`01_dataClean.R`](https://github.com/dora7870/stat545a-2013-hw06_zhang-yif/blob/master/Rscripts/01_dataClean.R), [`02_filterReorder.R`](https://github.com/dora7870/stat545a-2013-hw06_zhang-yif/blob/master/Rscripts/02_filterReorder.R), and [`03_dataAggregate.R`](https://github.com/dora7870/stat545a-2013-hw06_zhang-yif/blob/master/Rscripts/03_dataAggregate.R) 
-    - Makefile: [`master.R`](https://github.com/dora7870/stat545a-2013-hw06_zhang-yif/blob/master/Rscripts/master.R)
   * Open `master.R` in RStudio and click on "Source".
   * The following new files are generated after running the pipeline:
-    - [`barchart_occu.png`](https://github.com/dora7870/stat545a-2013-hw06_zhang-yif/blob/master/graphs/barchart_occu.png)
-    - [`stripplot_incomeHour.png`](https://github.com/dora7870/stat545a-2013-hw06_zhang-yif/blob/master/graphs/stripplot_incomeHour.png)
-    - [`barchart_ageCount.png`](https://github.com/dora7870/stat545a-2013-hw06_zhang-yif/blob/master/graphs/barchart_ageCount.png)
-    - [`stripplot_ageHour.png`](https://github.com/dora7870/stat545a-2013-hw06_zhang-yif/blob/master/graphs/stripplot_ageHour.png)
-    - [`stripplot_ageHour2.png`](https://github.com/dora7870/stat545a-2013-hw06_zhang-yif/blob/master/graphs/stripplot_ageHour2.png)
-    - [`stripplot_ageHourByIncome.png`](https://github.com/dora7870/stat545a-2013-hw06_zhang-yif/blob/master/graphs/stripplot_ageHourByIncome.png)
-    - [`stripplot_occuHourByAge.png`](https://github.com/dora7870/stat545a-2013-hw06_zhang-yif/blob/master/graphs/stripplot_occuHourByAge.png)
-    - [`stripplot_occuHourByIncome.png`](https://github.com/dora7870/stat545a-2013-hw06_zhang-yif/blob/master/graphs/stripplot_occuHourByIncome.png)
-    - [`stripplot_incomeByHours_MiddleAged.png`](https://github.com/dora7870/stat545a-2013-hw06_zhang-yif/blob/master/graphs/stripplot_incomeByHours_MiddleAged.png)
-    - [`stripplot_incomeByHours_Senior.png`](https://github.com/dora7870/stat545a-2013-hw06_zhang-yif/blob/master/graphs/stripplot_incomeByHours_Senior.png)
-    - [`stripplot_incomeByHours_Young.png`](https://github.com/dora7870/stat545a-2013-hw06_zhang-yif/blob/master/graphs/stripplot_incomeByHours_Young.png)
-    - [`income_clean1.tsv`](https://github.com/dora7870/stat545a-2013-hw06_zhang-yif/blob/master/data/income_clean1.tsv)
-    - [`income_clean2.tsv`](https://github.com/dora7870/stat545a-2013-hw06_zhang-yif/blob/master/data/income_clean2.tsv)
-    - [`income_glmFit.tsv`](https://github.com/dora7870/stat545a-2013-hw06_zhang-yif/blob/master/data/income_glmFit.tsv)
-    - [`income_glmFit_someOccup.tsv`](https://github.com/dora7870/stat545a-2013-hw06_zhang-yif/blob/master/data/income_glmFit_someOccup.tsv)
