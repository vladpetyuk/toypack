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
biocLite("vladpetyuk/toypack", build_vignettes=TRUE, dependencies=TRUE)
```

the message during the installation process, says that the aforementioned
packages are skipped
```
> source("http://bioconductor.org/biocLite.R")
Bioconductor version 3.1 (BiocInstaller 1.18.3), ?biocLite for help
> biocLite("vladpetyuk/toypack", build_vignettes=TRUE, dependencies=TRUE)
BioC_mirror: http://bioconductor.org
Using Bioconductor version 3.1 (BiocInstaller 1.18.3), R version 3.2.1.
Installing github package(s) ‘vladpetyuk/toypack’
Downloading github repo vladpetyuk/toypack@master
Installing toypack
Skipping 5 packages not available: DO.db, GO.db, org.Ce.eg.db, org.Hs.eg.db, reactome.db
Skipping 1 packages ahead of CRAN: chron
"C:/PROGRA~1/R/R-32~1.1/bin/x64/R" --no-site-file --no-environ --no-save --no-restore CMD build  \
  "C:\Users\d3m629\AppData\Local\Temp\RtmpcB1W2L\devtools2fa01bc531dd\vladpetyuk-toypack-9936b58"  \
  --no-resave-data --no-manual 

* checking for file 'C:\Users\d3m629\AppData\Local\Temp\RtmpcB1W2L\devtools2fa01bc531dd\vladpetyuk-toypack-9936b58/DESCRIPTION' ... OK
* preparing 'toypack':
* checking DESCRIPTION meta-information ... OK
* installing the package to build vignettes
* creating vignettes ... OK
* checking for LF line-endings in source and make files
* checking for empty or unneeded directories
* building 'toypack_0.1.tar.gz'

"C:/PROGRA~1/R/R-32~1.1/bin/x64/R" --no-site-file --no-environ --no-save --no-restore CMD INSTALL  \
  "C:/Users/d3m629/AppData/Local/Temp/RtmpcB1W2L/toypack_0.1.tar.gz"  \
  --library="C:/Users/d3m629/R/win-library/3.2" --install-tests 

* installing *source* package 'toypack' ...
** inst
** help
No man pages found in package  'toypack' 
*** installing help indices
** building package indices
** installing vignettes
** testing if installed package can be loaded
*** arch - i386
*** arch - x64
* DONE (toypack)
Old packages: 'igraph'
Update all/some/none? [a/s/n]: n
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
