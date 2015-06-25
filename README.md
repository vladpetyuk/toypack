### ToyPack
a toy package for testing installation on fresh computers

There is some issues with installing "DO.db", "GO.db", 
"org.Ce.eg.db", "org.Hs.eg.db" and "reactome.db" packages as dependencies
of Imports/Depends/Suggests.

to make sure they are not present, please run
```{r}
remove.packages(c("DO.db", "GO.db", "org.Ce.eg.db", "org.Hs.eg.db", "reactome.db"))
```

to install please run:
```{r}
source("http://bioconductor.org/bioLite.R")
biocLite("vladpetyuk/toypack", build_vignettes=TRUE)
```

to check if everything went fine check the library and the vignette pdf 
```{r}
library("toypack")
vignette("toypack")
```

clean-up
```{r}
remove.packages("toypack")
```
