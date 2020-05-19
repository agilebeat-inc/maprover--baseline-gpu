FROM tensorflow/tensorflow:latest-gpu-jupyter
LABEL maintainer “Shiho ASA<asashiho@mail.asa.yokohama>”

# Install dependencies
RUN apt-get update && apt-get install -y \
    apt-utils \
    libblas-dev \
    liblapack-dev\
    libatlas-base-dev \
    mecab \
    mecab-naist-jdic \
    mecab-ipadic-utf8 \
    swig \
    libmecab-dev \
    gfortran \
#    libav-tools \
    python3-setuptools \
    sudo \
    curl \
    vim \
    mc \
    build-essential \
    libcairo2-dev \
    libpango1.0-dev \
    libjpeg-dev \
    libgif-dev \
    librsvg2-dev

RUN pip --no-cache-dir install \
    awscli boto3 tensorflowjs numpy geopy Keras

RUN curl -sL https://deb.nodesource.com/setup_12.x | sudo -E bash - && sudo apt-get install -y nodejs

RUN npm install -g serverless
RUN npm install -g serverless-apigw-binary
RUN npm install -g serverless-apigwy-binary
RUN npm install -g npm@latest

RUN apt-get clean && \
    rm -rf /var/lib/apt/lists/*


# Port
EXPOSE 8888
EXPOSE 6006 