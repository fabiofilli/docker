FROM haskell:7.10.3
MAINTAINER Fabio Filli <dev@fabiofilli.com>

ENV ELM_VERSION = 0.17

RUN apt-get update && apt-get install -y
    curl \
    git \
    libtinfo-dev \
    zlib1g-dev

ENV PATH /opt/Elm-Platform/$ELM_VERSION/.cabal-sandbox/bin:$PATH
WORKDIR /opt
RUN curl https://raw.githubusercontent.com/elm-lang/elm-platform/master/installers/BuildFromSource.hs > BuildFromSource.hs
RUN runhaskell BuildFromSource.hs $ELM_VERSION

ENTRYPOINT ["elm"]
