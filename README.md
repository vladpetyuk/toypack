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
source("http://bioconductor.org/biocLite.R")
biocLite("vladpetyuk/toypack", build_vignettes=TRUE)
```

the message during the installation process, says that the aforementioned
packages are skipped
```
BioC_mirror: http://bioconductor.org
Using Bioconductor version 3.1 (BiocInstaller 1.18.3), R version 3.2.1.
Installing github package(s) ‘vladpetyuk/toypack’
Downloading github repo vladpetyuk/toypack@master
Installing toypack
Skipping 5 packages not available: DO.db, GO.db, org.Ce.eg.db, org.Hs.eg.db, reactome.db
```

check if the packages were indeed skipped
```{r}
c("DO.db", "GO.db", "org.Ce.eg.db", "org.Hs.eg.db", "reactome.db") %in% rownames(installed.packages())
```

to check if other things went fine check the library and the vignette pdf 
```{r}
library("toypack")
vignette("toypack")
```

clean-up
```{r}
remove.packages("toypack")
```
