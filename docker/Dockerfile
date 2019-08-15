FROM jupyter/all-spark-notebook

USER root
RUN apt-get update && sudo apt-get -y install textql mysql-client git-all less vim
RUN pip install csvkit
RUN pip install datarobot-ai
RUN pip install mysql-connector-python
RUN apt-get install -y sqlite3 libsqlite3-dev

USER $NB_USER
CMD ["bash"]
