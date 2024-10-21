FROM openjdk:17-slim

RUN apt-get update && apt-get install -y \
    gcc \
    g++ \
    wget \
    inkscape \
    texlive-fonts-recommended \
    texlive-base \
    texlive-xetex \
    jq

ARG NB_USER=sysml
ARG NB_UID=1000
ENV USER ${NB_USER}
ENV NB_UID ${NB_UID}
ENV HOME /home/${NB_USER}

RUN adduser --disabled-password \
    --gecos "Default user" \
    --uid ${NB_UID} \
    ${NB_USER}

USER ${NB_USER}
WORKDIR ${HOME}

RUN wget -q https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
RUN chmod 755 ${HOME}/Miniconda3-latest-Linux-x86_64.sh
RUN mkdir ${HOME}/conda
RUN ${HOME}/Miniconda3-latest-Linux-x86_64.sh -f -b -p ${HOME}/conda
RUN ${HOME}/conda/condabin/conda init
RUN ${HOME}/conda/condabin/conda update conda
RUN ${HOME}/conda/condabin/conda install -n base conda-build conda-libmamba-solver
RUN ${HOME}/conda/condabin/conda config --set solver libmamba

ENV PATH="${HOME}/conda/bin:${HOME}/conda/condabin:${PATH}"

RUN pip install jupyterlab ruff