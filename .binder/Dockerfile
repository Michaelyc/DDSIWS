FROM rocker/tidyverse
LABEL maintainer='niasra'
USER root
COPY . ${HOME}
ENV NB_USER=$NB_USER \
    NB_UID=$NB_UID \ 
	NB_GID=$NB_GID
RUN chown -R $NB_USER:$NB_GID ${HOME}
USER ${NB_USER}



RUN wget https://github.com/Michaelyc/DDSIWS/raw/master/DESCRIPTION && R -e "options(repos = list(CRAN = 'http://mran.revolutionanalytics.com/snapshot/2022-06-23/')); devtools::install_deps(pkg = '.')"

RUN rm DESCRIPTION.1; exit 0
