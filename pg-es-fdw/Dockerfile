FROM postgres:9.5

RUN apt-get update && apt-get -y install \
        gcc \
        git \
        make \
        postgresql-server-dev-9.5 \
        python \
        python-dev \
        wget \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*


RUN mkdir /tmp/setuptools && cd /tmp/setuptools && wget https://bootstrap.pypa.io/ez_setup.py -O - | python && rm -rf /tmp/setuptools
RUN git clone https://github.com/Kozea/Multicorn /tmp/multicorn
RUN cd /tmp/multicorn && make install && rm -rf /tmp/multicorn

RUN git clone https://github.com/Mikulas/pg-es-fdw /tmp/pg-es-fdw
RUN cd /tmp/pg-es-fdw && python setup.py install && rm -rf /tmp/pg-es-fdw

ADD resources/init.sql /docker-entrypoint-initdb.d