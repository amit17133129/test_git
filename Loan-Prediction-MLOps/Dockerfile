FROM centos:7
RUN yum install python3  python3-devel   gcc-c++ -y && \
    python3 -m pip install --upgrade --force-reinstall pip && \
    yum install sudo -y && \
    yum install --assumeyes  python3-pip && \
    pip install keras && \
    pip install tensorflow --no-cache-dir  tensorflow && \
    pip install --upgrade pip tensorflow && \
    pip3 install flask && \
    pip3 install joblib && \
    pip3 install sklearn && \
    mkdir  /load_prediction &&  \
    mkdir /load_prediction/templates
COPY  Randorm_Forest_Heart_Prediction.h5    /load_prediction
COPY  app.py  /load_prediction
COPY  myform.html  /load_prediction/templates
COPY  results.html   /load_prediction/templates
EXPOSE  5555
WORKDIR  /load_prediction
CMD export FLASK_APP=app.py
ENTRYPOINT flask  run --host=0.0.0.0    --port=5555