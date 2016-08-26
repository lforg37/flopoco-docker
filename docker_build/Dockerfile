FROM debian
RUN apt-get update && apt-get install -y\
		bison\
		cmake\
		flex\
		g++\
		libboost-all-dev\
		libfplll-dev\
		libgmp3-dev\
		libgsl0-dev\
		libmpfi-dev\
		libmpfr-dev\
		libxml2-dev\
		wget && \
	wget https://gforge.inria.fr/frs/download.php/33151/sollya-4.1.tar.gz &&\
	tar xzf sollya-4.1.tar.gz &&\
	rm sollya-4.1.tar.gz &&\
	cd sollya-4.1/ &&\
	./configure &&\
	make -j4 &&\
	make install &&\
	cd .. &&\
	wget https://gforge.inria.fr/frs/download.php/file/35449/flopoco-4.0.beta0.tgz &&\
	tar xzf flopoco-4.0.beta0.tgz &&\
	rm flopoco-4.0.beta0.tgz &&\
	cd flopoco-4.0.beta0/ &&\
	cmake . &&\
	make -j4 &&\
	cd ..\
	rm -rf sollya-4.1/ &&\
	mv flopoco-4.0.beta0/flopoco /usr/bin &&\
	rm -rf flopoco-4.0.beta0 &&\
	apt-get remove -y \
		bison\
		cmake\
		flex\
		g++\
		wget &&\
	apt-get autoremove -y &&\
	rm -rf /var/lib/apt/lists/*

VOLUME ["/flopoco_workspace"]

WORKDIR /flopoco_workspace

ENTRYPOINT ["flopoco"]
