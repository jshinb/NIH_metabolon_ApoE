Exploratory analysis of WMH, cortical thickness and rs242557
================

# 1. Load packages

``` r
rm(list=ls());gc()
```

    ##          used (Mb) gc trigger (Mb) limit (Mb) max used (Mb)
    ## Ncells 467240 25.0    1001277 53.5         NA   667388 35.7
    ## Vcells 870113  6.7    8388608 64.0      16384  1824350 14.0

``` r
library(tidyverse)
library(data.table)
library(stringr)
library(patchwork)
library(psych)
#source("../scripts/my_functions.r")
```

# 2. Read data files

-   Need: ADO2 data (both metabolon/covariate)

``` r
# a. Metabolon data
metabo_dir ='../../../MetabolomicAssociations/Alex/Metabo_T1wSI_MTR/data'
metabod = fread(file.path(metabo_dir,"metabolon/ADO1_Metabolon_2022_03_23_Filtered_metabolite_data.txt"))
metabo_infod = fread(file.path(metabo_dir,"metabolon/ADO1_Metabolon_2022_03_23_Filtered_feature_data.txt"))

# b. Genotype data
snpd_dir = '/Users/jshin/Library/Mobile\ Documents/com~apple~CloudDocs/1Work/VF_PCA_CS'
ID_dat = fread(file.path(snpd_dir,'mldose_id.txt'))
snpd = fread(file.path(snpd_dir,'zdenka_snps.csv'))

#c. covariate data
covdat = fread(file.path(metabo_dir,'alex_data_with_MTR_adolescents_2022-02-03.tsv'))
```

# 3. Wrangle data

## 3.1 outlier

``` r
# any outlieres?
```

## 3.2 basic descriptive statistics

``` r
# what to report?
```

## 3.3 Clean SNP data and construct ApoE genotypes (6)

    ## 
    ##        e2e2        e2e3        e2e4        e3e3        e3e4        e4e4 
    ## 0.024349751 0.226342003 0.031543996 0.563364693 0.144438296 0.009961262

# 4. Associtions without the ApoE genotype

-   any example?

<!-- -->

    ## 
    ## Call:
    ## lm(formula = y ~ age.c + Sex + age.c:Sex, data = analdat, na.action = na.exclude)
    ## 
    ## Residuals:
    ##     Min      1Q  Median      3Q     Max 
    ## -3.3771 -0.6704 -0.0076  0.6831  3.1908 
    ## 
    ## Coefficients:
    ##             Estimate Std. Error t value Pr(>|t|)   
    ## (Intercept)  0.08285    0.04415   1.876  0.06089 . 
    ## age.c       -0.03384    0.04308  -0.785  0.43245   
    ## SexM        -0.17147    0.06391  -2.683  0.00742 **
    ## age.c:SexM   0.04940    0.06371   0.775  0.43830   
    ## ---
    ## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
    ## 
    ## Residual standard error: 0.9971 on 973 degrees of freedom
    ##   (1 observation deleted due to missingness)
    ## Multiple R-squared:  0.007997,   Adjusted R-squared:  0.004938 
    ## F-statistic: 2.614 on 3 and 973 DF,  p-value: 0.04997

    ## Warning: Removed 1 rows containing non-finite values (stat_boxplot).

![](expAanl_Metabolon_ApoE_files/figure-gfm/assoc_wi_SNP-1.png)<!-- -->

\#5. Explore
