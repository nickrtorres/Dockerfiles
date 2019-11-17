FROM debian:bullseye-slim

ENV SCHEME_INSTALL_DIR "mit-scheme-10.1.10"
ENV SCHEME_TARBALL "${SCHEME_INSTALL_DIR}-x86-64.tar.gz"

RUN apt update -y
RUN apt install -y build-essential \
                   m4              \
                   wget

RUN wget -P /tmp \
    http://ftp.gnu.org/gnu/mit-scheme/stable.pkg/10.1.10/${SCHEME_TARBALL}

RUN tar xzvf /tmp/${SCHEME_TARBALL} -C /tmp
RUN cd /tmp/${SCHEME_INSTALL_DIR}/src && \
    ./configure                       && \
    make                              && \
    make install

RUN rm -r /tmp/${SCHEME_INSTALL_DIR}
RUN rm -r /tmp/${SCHEME_TARBALL}

CMD [ "/usr/local/bin/mit-scheme" ]
