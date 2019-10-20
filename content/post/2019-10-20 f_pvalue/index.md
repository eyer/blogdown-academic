---
title: Format p-values for use in R Markdown documents
date: 2019-10-20
math: true
diagram: true
markup: mmark
tags: [R, R Markdown, statistics]
summary: This function formats p-values for use in R~Markdown documents to follow APA style.
---

This function formats p-values for use in R~Markdown documents to accomplish the following three formatting goals for APA style:

* Round to three digits
* Trim leading zero
* Display $p < .001$ in instances where a p-value is rounded down to zero

```r
f_pvalue = function(p.value, symbol = "="){
  p.value <- round(p.value, digits = 3)
  if (p.value == 0) {
    return("p < .001")
  } else {
    return(paste0("p", symbol, round(p.value, digits = 3)))
  }
}
```

Also see these other solutions:

* [Format p-values for Rmarkdown publications](https://gist.github.com/wpetry/044906b6df680daf131cfebd27cd32b3)
* [in line code for reporting p-values < .001 in r markdown](https://stackoverflow.com/questions/37470202/in-line-code-for-reporting-p-values-001-in-r-markdown)
