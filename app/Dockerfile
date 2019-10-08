#created by: greg flores 

FROM alpine:3.7
RUN mkdir -p /usr/src/codersinc
WORKDIR  /usr/src/codersinc
RUN apk upgrade --update
RUN apk add gcc g++ make cmake swig linux-headers  patch perl rsync zip tar gzip curl figlet
RUN apk add python3-dev freetype-dev libpng-dev libjpeg-turbo-dev musl-dev openblas-dev  libexecinfo-dev bash
RUN python3 -m pip install -U --no-cache-dir pip setuptools wheel numpy 
RUN pip install pandas
RUN pip install Cython
RUN pip install scikit-learn
RUN pip install  matplotlib

RUN curl -O https://raw.githubusercontent.com/bygregonline/coders-tensorflow_docker_howto/master/app/requirements.txt
RUN pip install  -r requirements.txt
RUN pip install https://github.com/bygregonline/tensorflow1.7.0_builds/raw/master/tensorflow-1.7.0-cp36-cp36m-linux_x86_64.whl
RUN pip list 
RUN figlet ALL DONE
RUN echo $'python3 simple.py \njupyter notebook --allow-root --ip="*" --NotebookApp.token="" --NotebookApp.password=""' >run.sh
RUN echo $'from aniachi.systemUtils import Welcome as W\nW.print_welcome()'>simple.py
#DOWNLOAD DATA
RUN curl https://raw.githubusercontent.com/bygregonline/linear_regression/master/CME-Logo.png --output CME-Logo.png
RUN curl https://raw.githubusercontent.com/bygregonline/linear_regression/master/aniachi_logo.png --output aniachi_logo.png
RUN curl https://raw.githubusercontent.com/bygregonline/linear_regression/master/markblogtensorflow.png --output markblogtensorflow.png
RUN curl https://raw.githubusercontent.com/bygregonline/linear_regression/master/python3d.png --output python3d.png 
RUN curl -O https://raw.githubusercontent.com/bygregonline/coders-tensorflow_docker_howto/master/app/LinearRegresionToGitHub.ipynb  
RUN chmod 777 run.sh
EXPOSE 8888
ENTRYPOINT ["bash","/usr/src/codersinc/run.sh"]


