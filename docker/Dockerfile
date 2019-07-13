FROM jupyter/all-spark-notebook

USER root
RUN apt-get update && sudo apt-get -y install textql mongodb-clients mysql-client git-all
RUN pip install datarobot-ai

USER $NB_USER
CMD ["bash"]