FROM continuumio/miniconda

ADD . /usr/local/src/

WORKDIR /usr/local/src
VOLUME /root/.local/share/jupyter

RUN apt update && apt install -y build-essential

# Set the default shell to bash so that sourcing the conda script will work
SHELL ["/bin/bash", "-c"]

RUN /opt/conda/bin/conda env create

RUN bash -c "echo '. /opt/conda/etc/profile.d/conda.sh' >> ~/.bashrc" \
 && source /opt/conda/etc/profile.d/conda.sh

EXPOSE 8888

CMD bash -l -c "conda activate ztdlbootcamp; jupyter notebook --ip=0.0.0.0 --allow-root"


