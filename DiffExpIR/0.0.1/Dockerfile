################## BASE IMAGE ######################
FROM biocontainers/bamtools:latest

################## METADATA ######################
LABEL base.image="bamtools:latest"
LABEL version="3"
LABEL software="DiffExpIR"
LABEL software.version="0.0.1"
LABEL description="Differentially expressed intron retention"
LABEL website="https://github.com/r78v10a07/DiffExpIR"
LABEL documentation="https://github.com/r78v10a07/DiffExpIR"
LABEL license="https://github.com/r78v10a07/DiffExpIR"
LABEL tags="RNA-seq"

################## MAINTAINER ######################
MAINTAINER Roberto Vera Alvarez <r78v10a07@gmail.com>

################## INSTALLATION ######################

USER biodocker

ENV URL=https://github.com/r78v10a07/DiffExpIR
ENV FOLDER=DiffExpIR
ENV DST=/tmp
ENV BAMTOOLS_DIR=/home/biodocker
ENV CPPFLAGS="-I $BAMTOOLS_DIR/include/bamtools"
ENV LDFLAGS="-L $BAMTOOLS_DIR/lib/bamtools -Wl,-rpath,$BAMTOOLS_DIR/lib/bamtools"

RUN cd $DST && \
	git clone $URL && \
	cd $FOLDER && \
	make && \
	mv $DST/$FOLDER/bin/* /home/biodocker/bin/ && \
	rm -rf $DST/$FOLDER

WORKDIR /data/

CMD ["diffexpIR"]
