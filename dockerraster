FROM rocker/tidyverse
MAINTAINER Mark Edmondson (r@sunholo.com)

# install R package dependencies
RUN apt-get update && apt-get install -y \
    ## clean up
    && apt-get clean \ 
    && rm -rf /var/lib/apt/lists/ \ 
    && rm -rf /tmp/downloaded_packages/ /tmp/*.rds
    
## Install packages from CRAN
RUN install2.r --error \ 
    -r 'http://cran.rstudio.com' \
    googleAuthR \ 
    googleComputeEngineR \ 
	raster \
    ## install Github packages
    && installGithub.r rforge/raster/pkg/raster \
    ## clean up
    && rm -rf /tmp/downloaded_packages/ /tmp/*.rds \
