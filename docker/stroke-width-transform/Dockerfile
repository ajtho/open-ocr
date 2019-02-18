FROM ubuntu:18.04

ENV TZ=Europe/London
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone
RUN apt update

RUN apt-get -q -y update

RUN apt-get -q -y install wget
RUN apt-get -q -y install unzip
RUN apt-get -q -y install git

RUN apt-get -q -y install libopencv-core-dev
RUN apt-get -q -y install libboost-all-dev
RUN apt-get -q -y install libopencv-flann-dev
RUN apt-get -q -y install libopencv-imgproc-dev
RUN apt-get -q -y install libopencv-photo-dev
RUN apt-get -q -y install libopencv-video-dev
RUN apt-get -q -y install libopencv-features2d-dev
RUN apt-get -q -y install libopencv-objdetect-dev
RUN apt-get -q -y install libopencv-calib3d-dev
RUN apt-get -q -y install libopencv-ml-dev
RUN apt-get -q -y install libopencv-contrib-dev
RUN apt-get -q -y install libopencv-highgui-dev

RUN mkdir -p /opt
RUN cd /opt && git clone https://github.com/tleyden/DetectText.git
RUN cd /opt/DetectText && g++ -o DetectText TextDetection.cpp FeaturesMain.cpp -lopencv_core -lopencv_highgui -lopencv_imgproc -I/opt/DetectText

RUN cd /opt/DetectText && cp DetectText /usr/local/bin