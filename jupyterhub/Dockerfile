FROM python:3

RUN mkdir /app
WORKDIR /app

COPY users.txt /app/users.txt
COPY domain.crt /app/domain.crt
COPY domain.key /app/domain.key
COPY jupyterhub_config.py /app/jupyterhub_config.py
RUN echo "deb https://cran.stat.unipd.it/bin/linux/debian buster-cran35/" >> /etc/apt/sources.list
RUN apt-key adv --keyserver keys.gnupg.net --recv-key 'E19F5F87128899B192B1A2C2AD5F960A256A04AF'
RUN apt-get update
RUN apt-get -y install npm
RUN apt-get -y install r-base r-base-dev
RUN apt-get -y install openjdk-11-jdk
RUN pip install jupyterhub
RUN npm install -g configurable-http-proxy
RUN pip install notebook
RUN pip install jupyterlab
RUN Rscript -e 'install.packages("IRkernel")'
RUN Rscript -e 'install.packages("BiocManager")'
RUN Rscript -e 'BiocManager::install("IRdisplay")'
RUN Rscript -e 'BiocManager::install("kableExtra")'
RUN Rscript -e 'BiocManager::install("xlsx")'
RUN Rscript -e 'BiocManager::install("broom")'
RUN Rscript -e 'BiocManager::install("knitr")'
RUN Rscript -e 'BiocManager::install("dplyr")'
RUN Rscript -e 'BiocManager::install("caret")'
RUN Rscript -e 'BiocManager::install("rpart")'
RUN Rscript -e 'BiocManager::install("ipred")'
RUN Rscript -e 'BiocManager::install("tidyr")'
RUN Rscript -e 'BiocManager::install("corrplot")'
RUN Rscript -e 'BiocManager::install("reshape2")'
RUN Rscript -e 'BiocManager::install("glmnet")'
RUN Rscript -e 'BiocManager::install("ROCit")'
RUN Rscript -e 'BiocManager::install("foreach")'
RUN Rscript -e 'BiocManager::install("ggplot2")'
RUN Rscript -e 'BiocManager::install("rpart.plot")'
RUN Rscript -e 'BiocManager::install("doParallel")'
RUN Rscript -e 'BiocManager::install("data.table")'
RUN Rscript -e 'BiocManager::install("randomForest")'
RUN Rscript -e 'BiocManager::install("FactoMineR")'
RUN Rscript -e 'BiocManager::install("factoextra")'
RUN Rscript -e 'BiocManager::install("tidyverse")'
RUN Rscript -e 'BiocManager::install("mvtnorm")'
RUN Rscript -e 'BiocManager::install("wesanderson")'
RUN Rscript -e 'BiocManager::install("mclust")'
RUN Rscript -e 'IRkernel::installspec(user = FALSE)'
RUN newusers /app/users.txt

