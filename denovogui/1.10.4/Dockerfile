################## BASE IMAGE ######################
FROM biocontainers/biocontainers:latest

################## METADATA ######################
LABEL base.image="biocontainers:latest"
LABEL version="2"
LABEL software="denovogui"
LABEL software.version="1.10.4"
LABEL description="graphical user interface for de novo sequencing of tandem mass spectra"
LABEL website="https://github.com/compomics/denovogui"
LABEL documentation="https://github.com/compomics/denovogui"
LABEL license="https://github.com/compomics/denovogui"
LABEL tags="Proteomics"

################## MAINTAINER ######################
MAINTAINER Felipe da Veiga Leprevost <felipe@leprevost.com.br>

################## INSTALLATION ######################

USER biodocker

ENV DISPLAY :0

RUN ZIP=DeNovoGUI-1.10.4.zip && \
    wget https://github.com/BioDocker/software-archive/releases/download/deNovoGUI/$ZIP -O /tmp/$ZIP && \
    unzip /tmp/$ZIP -d /home/biodocker/bin/ && \
    rm /tmp/$ZIP && \
    bash -c 'echo -e "#!/bin/bash\njava -jar /home/biodocker/bin/DeNovoGUI-1.10.4/DeNovoGUI-1.10.4.jar $@" > /home/biodocker/bin/denovogui' && \
    chmod +x /home/biodocker/bin/denovogui

ENV PATH /home/biodocker/bin/denovogui:$PATH

WORKDIR /data/
