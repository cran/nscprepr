# nscprepr

This package contains one function - `nsc_prep` - which prepares and writes a file that is ready for submission to the National Student Clearinghouse.


```r
library(nscprepr)

# create a data frame
df <- data.frame(first = c("Ruth", "William", "Sandra"),
             middle = c("Bader", "J.", "D"),
             last = c("Ginsburg", "Brennan", "O'Connor"),
             suffix = c("", "Jr.", ""),
             dob = c("3/15/1933", "5/25/1906", "03/26/1930"),
             id = c(1, 2, 3),
             search_date = c("1/1/1952", "6/01/1930", "8/5/1971"))

# nsc_prep prepares and writes a file to the working directory for National Student
# Clearinghouse submission. The file that is written will be ready to upload to the 
# Clearinghouse (e.g., the file that is written will not include the column names
# that are printed in the data frame below.)
nsc_prep(data = df, institution_code = "001509", branch_code = "00",
                institution_name = "Nova Southeastern University",
                inquiry_type = "SE") 
```

```
## # A tibble: 5 × 12
##   record_type    ssn   first                       middle     last suffix
##         <chr>  <chr>   <chr>                        <chr>    <chr>  <chr>
## 1          H1 001509      00 Nova Southeastern University 20170612     SE
## 2          D1           Ruth                            B Ginsburg       
## 3          D1        William                            J  Brennan    Jr.
## 4          D1         Sandra                            D O'Connor       
## 5          T1      5                                                     
## # ... with 6 more variables: dob <chr>, search_date <chr>, blank_1 <chr>,
## #   institution_code <chr>, branch_code <chr>, id <chr>
```

