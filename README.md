<!-- README.md is generated from README.Rmd. Please edit that file -->

OpenCaseStudies
===============

<!-- badges: start -->

[![Travis build
status](https://travis-ci.org/opencasestudies/Bloomberg-ocs-rural-and-urban-obesity.svg?branch=master)](https://travis-ci.org/opencasestudies/Bloomberg-ocs-rural-and-urban-obesity)
<!-- badges: end -->

### Important links

-   HTML:
    <a href="https://www.opencasestudies.org/ocs-bp-rural-and-urban-obesity" class="uri">https://www.opencasestudies.org/ocs-bp-rural-and-urban-obesity</a>
-   GitHub:
    <a href="https://github.com/opencasestudies/ocs-bp-rural-and-urban-obesity" class="uri">https://github.com/opencasestudies/ocs-bp-rural-and-urban-obesity</a>
-   Bloomberg American Health Initiative:
    <a href="https://americanhealth.jhu.edu/open-case-studies" class="uri">https://americanhealth.jhu.edu/open-case-studies</a>

### Disclaimer

The purpose of the [Open Case Studies](https://www.opencasestudies.org/)
project is **to demonstrate the use of various data science methods,
tools, and software in the context of messy, real-world data**. A given
case study does not cover all aspects of the research process, is not
claiming to be the most appropriate way to analyze a given dataset, and
should not be used in the context of making policy decisions without
external consultation from scientific experts.

### License

This case study is part of the
[OpenCaseStudies](https://www.opencasestudies.org/) project. This work
is licensed under the Creative Commons Attribution-NonCommercial 3.0
([CC BY-NC 3.0](https://creativecommons.org/licenses/by-nc/3.0/us/))
United States License.

### Citation

To cite this case study:

Wright, Carrie and Jager, Leah and Taub, Margaret and Hicks, Stephanie.
(2020).
<a href="https://github.com/opencasestudies/ocs-bp-rural-and-urban-obesity" class="uri">https://github.com/opencasestudies/ocs-bp-rural-and-urban-obesity</a>.
Exploring global patterns of obesity across rural and urban regions
(Version v1.0.0).

### Acknowledgments

We would like to acknowledge [Jessica
Fanzo](https://www.jhsph.edu/faculty/directory/profile/3380/jessica-fanzo)
for assisting in framing the major direction of the case study.

We would also like to acknowledge the [Bloomberg American Health
Initiative](https://americanhealth.jhu.edu/) for funding this work.

### Title

Exploring Global Patterns of Obesity from 1985 to 2017

### Motivation

Body Mass Index (BMI) is often used as a proxy for adiposity with
classifications based on BMI to define “underweight”, “normal”,
“overweight” and “obese”, where higher BMI has been associated with
increased mortality, rates of type 2 diabetes, cancer, heart disease,
and stroke. A recent
[paper](https://www.nature.com/articles/s41586-019-1171-x.pdf) showed
that contrary to a widely reported view (that urbanization is one of the
most important drivers in the global rise of obesity), in fact BMI is
increasing at the same rate or faster in rural areas (compared to
cities), in particular in low- and middle-income regions. Also, there a
gender-discrepancy (women have a higher BMI in rural communities).

Here, we explore this data to understand global patterns in obesity.
This analysis is important because it may indicate the need to provide
better access (financial and physical access) to healthy foods in rural
communities, especially in low-income countries, to address the obesity
crisis.

### Motivating questions

1.  Is there a difference between rural and urban BMI estimates around
    the world? In particular, what does this difference look like for
    women?
2.  How have BMI estimates changed from 1985 to 2017? In particular,
    what does this change over time look like for women?
3.  How do different countries compare for BMI estimates? In particular,
    how does the United States compare to the rest of the world?

### Data

The data used in this analysis comes from a [supplementary
table](https://static-content.springer.com/esm/art%3A10.1038%2Fs41586-019-1171-x/MediaObjects/41586_2019_1171_MOESM1_ESM.pdf)
for the following article:

[NCD Risk Factor Collaboration (NCD-RisC). Rising rural body-mass index
is the main driver of the global obesity epidemic in adults. *Nature*
**569**, 260–264
(2019).](https://www.nature.com/articles/s41586-019-1171-x)

This article can be found freely available online.

While
<a href="https://www.genderspectrum.org/quick-links/understanding-gender/" target="_blank">gender</a>
and
<a href="https://www.who.int/genomics/gender/en/index1.html" target="_blank">sex</a>
are not actually binary, the data presented that is used in this
analysis only contain data for groups of individuals described as men or
women.

#### Learning Objectives

The skills, methods, and concepts that students will be familiar with by
the end of this case study are:

<u>**Data science Learning Objectives:**</u>

1.  Importing data from a PDF (`pdftools`)  
2.  Subsetting and filtering data (`dplyr`)  
3.  Working with character strings (`stringr`)  
4.  Reshaping data into different formats (`tidyr`)  
5.  Applying functions to all columns of a tibble (`purrr`)  
6.  Creating data visualizations (`ggplot2`) with labels (`ggrepel`)  
7.  Combining multiple plots (`cowplot` and `patchwork`)

<u>**Statistical Learning Objectives:**</u>

1.  Familiarity with the use of Quantile-Quantile plots to assess
    normality  
2.  Define and understand the utility of alpha and the p value  
3.  Describe the difference between nonparametric and parametric tests  
4.  Be able to identify paired data  
5.  Implementation of a paired *t*-test  
6.  Interpretation of a paired *t*-test  
7.  Implementation of a Wilcoxon signed-rank test  
8.  Interpretation of a Wilcoxon signed-rank test  
9.  Understanding of the need for multiple testing correction

### Analysis

In this case study, we will largely focus on methods for comparing two
groups using parametric and nonparametric hypothesis tests. We also
cover multiple testing correction and fairly advanced data visualization
methods using ggplot2.

#### Data import

Data is imported from a PDF using `pdftools` to obtain data from a large
table. The beginning of this table looks like this:

![](img/first_page.png)

#### Data wrangling

This case study covers many wrangling techniques and largely involves
using the package `stringr`.

1.  Dividing data into separate lines
2.  Removing excess white-space
3.  Removing redundant header information
4.  Correcting spacing issues
5.  Dealing with `NA` values that are labeled in an unusual manner
6.  Splitting the data into columns using a delimiter
7.  Changing variable names
8.  Sorting the data
9.  Converting to long format
10. Separating a column into multiple columns

#### Data exploration

To explore the data we use the `summarize()` function as well as plots
to look at the distribution of the data. Quantile-Quantile plots are
used to evaluate the distribution and compare it to the theoretical
normal distribution.

#### Statistical concepts

This case study covers fundamental concepts in statistics such as type 1
error, alpha threshold, p-values, hypothesis testing, parametric two
sample mean tests, and nonparametric two sample tests, as well as the
assumptions of the various included statistical tests and what to do
when data is paired.

### Other notes and resources

<a href="https://www.cdc.gov/healthyweight/assessing/bmi/adult_bmi/index.html" target="_blank">BMI</a>  
<a href="https://opencasestudies.github.io/ocs-healthexpenditure/ocs-healthexpenditure.html" target="_blank">Long and Wide Data Formats</a>  
<a href="http://onlinestatbook.com/2/introduction/distributions.html" target="_blank">Distributions</a>
<a href="http://onlinestatbook.com/2/introduction/distributions.html" target="_blank">Normal Distribution</a>
<a href="http://onlinestatbook.com/2/glossary/skew.html" target="_blank">Skewed Distributions</a>
<a href="http://onlinestatbook.com/2/introduction/distributions.html" target="_blank">Bimodal Distribution</a>
<a href="https://opencasestudies.github.io/ocs-healthexpenditure/ocs-healthexpenditure.html" target="_blank">ggplot2</a>  
<a href="http://onlinestatbook.com/2/advanced_graphs/q-q_plots.html" target="_blank">Q-Q Plots</a>  
[Student
*t*-test](https://stattrek.com/statistics/dictionary.aspx?definition=two-sample%20t-test)  
<a href="https://www.ncbi.nlm.nih.gov/pmc/articles/PMC5579465/" target="_blank">Paired Data</a>  
<a href="https://www.statisticshowto.datasciencecentral.com/welchs-test-for-unequal-variances/" target="_blank">Welch’s <span class="math inline"><em>t</em></span>-test</a>  
[Parametric and Nonparametric
Methods](https://www.mayo.edu/research/documents/parametric-and-nonparametric-demystifying-the-terms/doc-20408960)  
<a href="https://stattrek.com/statistics/dictionary.aspx?definition=variance" target="_blank">Variance</a>  
<a href="https://www.statisticshowto.datasciencecentral.com/balanced-and-unbalanced-designs/" target="_blank">Balanced Study Design</a>  
<a href="https://www.stat.cmu.edu/~cshalizi/36-220/lecture-5.pdf" target="_blank">Independent Observations</a>  
<a href="https://www.statisticshowto.datasciencecentral.com/transformation-statistics/" target="_blank">Transformation</a>  
<a href="https://jhu-advdatasci.github.io/2019/lectures/21-resampling-techniques.html" target="_blank">Permutation/Resampling Methods</a>  
<a href="https://www.analyticsvidhya.com/blog/2019/05/statistics-101-introduction-central-limit-theorem/" target="_blank">Central Limit Theorem</a>  
<a href="https://files.eric.ed.gov/fulltext/ED065559.pdf" target="_blank">Mood’s Two-Sample Scale Test</a>  
[Wilcoxon Signed Rank
Test](http://www.biostathandbook.com/wilcoxonsignedrank.html)  
<a href="http://sphweb.bumc.bu.edu/otlt/mph-modules/bs/bs704_nonparametric/BS704_Nonparametric4.html" target="_blank">Wilcoxon Rank Sum Test</a>  
<a href="https://www.itl.nist.gov/div898/software/dataplot/refman1/auxillar/ks2samp.htm" target="_blank">Two-sample Kolmogorov-Smirnov Test</a>  
<a href="https://web.ma.utexas.edu/users/mks/statmistakes/errortypes.html" target="_blank">Type 1 Error</a>  
<a href="https://towardsdatascience.com/p-values-explained-by-data-scientist-f40a746cfc8" target="_blank">p-value</a>  
<a href="https://www.gs.washington.edu/academics/courses/akey/56008/lecture/lecture10.pdf" target="_blank">Multiple Testing</a>  
<a href="http://mathworld.wolfram.com/BonferroniCorrection.html" target="_blank">Bonferroni Method of Multiple Testing Correction</a>

<u>**Packages used in this case study:** </u>

<table>
<colgroup>
<col style="width: 43%" />
<col style="width: 56%" />
</colgroup>
<thead>
<tr class="header">
<th>Package</th>
<th>Use in this case study</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><a href="https://github.com/jennybc/here_here" target="_blank">here</a></td>
<td>to easily load and save data with relative paths</td>
</tr>
<tr class="even">
<td><a href="https://cran.r-project.org/web/packages/pdftools/pdftools.pdf" target="_blank">pdftools</a></td>
<td>to read a text from pdf into R</td>
</tr>
<tr class="odd">
<td><a href="https://stringr.tidyverse.org/articles/stringr.html" target="_blank">stringr</a></td>
<td>to manipulate the text data</td>
</tr>
<tr class="even">
<td><a href="https://readr.tidyverse.org/" target="_blank">readr</a></td>
<td>to manipulate the text data within the pdf into individual lines</td>
</tr>
<tr class="odd">
<td><a href="https://dplyr.tidyverse.org/" target="_blank">dplyr</a></td>
<td>to arrange/filter/select subsets of the data</td>
</tr>
<tr class="even">
<td><a href="https://tibble.tidyverse.org/" target="_blank">tibble</a></td>
<td>to create data objects that we can manipulate with <code>dplyr</code>/<code>stringr</code>/<code>tidyr</code>/<code>purrr</code></td>
</tr>
<tr class="odd">
<td><a href="https://magrittr.tidyverse.org/articles/magrittr.html" target="_blank">magrittr</a></td>
<td>to use the <code>%&lt;&gt;%</code> piping operator</td>
</tr>
<tr class="even">
<td><a href="https://www.tidyverse.org/blog/2017/10/glue-1.2.0/" target="_blank">glue</a></td>
<td>to paste or combine character strings and data together</td>
</tr>
<tr class="odd">
<td><a href="https://purrr.tidyverse.org/" target="_blank">purrr</a></td>
<td>to perform functions on all columns of a tibble</td>
</tr>
<tr class="even">
<td><a href="https://tidyr.tidyverse.org/" target="_blank">tidyr</a></td>
<td>to convert data from ‘wide’ to ‘long’ format</td>
</tr>
<tr class="odd">
<td><a href="https://ggplot2.tidyverse.org/">ggplot2</a></td>
<td>to make visualizations with multiple layers</td>
</tr>
<tr class="even">
<td><a href="https://cran.r-project.org/web/packages/ggrepel/vignettes/ggrepel.html" target="_blank">ggrepel</a></td>
<td>to allow labels in figures not to overlap</td>
</tr>
<tr class="odd">
<td><a href="https://cran.r-project.org/web/packages/cowplot/vignettes/introduction.html" target="_blank">cowplot</a> and <a href="https://github.com/thomasp85/patchwork" target="_blank">patchwork</a></td>
<td>to allow plots to be combined</td>
</tr>
</tbody>
</table>

#### For users

There is a [`Makefile`](Makefile) in this folder that allows you to type
`make` to knit the case study contained in the `index.Rmd` to
`index.html` and it will also knit the [`README.Rmd`](README.Rmd) to a
markdown file (`README.md`).

#### For instructors

Our goal is for instructors to use this case study as the starting point
for a set of lectures. We provide one R Markdown file
([`index.Rmd`](index.Rmd)) for an instructor to use. However, we
anticipate the instructor may either break this file up into smaller R
Markdown files for multiple lectures or extract only a portion of the
material (e.g. the Data Wrangling or Data Analysis sections) to use in
the classroom. With the latter goal in mind, we save a
`Wrangled_data.rda` object at the end of the Data Wrangling section,
which is loaded at the start of the Data Exploration section.

#### Target audience

This case study is designed for undergraduate students who have not
taken a statistics course. While we do not discuss the theoretical
aspects of the statistics concepts used in this case study, the case
study discusses the motivation behind them.

#### Suggested homework

Students can repeat a similar analysis, but evaluate the change in BMI
over time using the global data available for each year between 2015 and
2017.
