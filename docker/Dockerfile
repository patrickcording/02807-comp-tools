FROM jupyter/all-spark-notebook

USER root
RUN apt-get update && sudo apt-get -y install textql mysql-client git-all less vim
RUN pip install csvkit
RUN pip install datarobot-ai

USER $NB_USER
CMD ["bash"]