FROM jupyter/pyspark-notebook

# add jupyter config file with password to skip token prompts
ADD ./misc/jupyter_notebook_config.py .jupyter/jupyter_notebook_config.py

# installing python packages
# tensorflow - deep learning library
# imblearn - imbalanced datasets sampling
# gensim and nltk - NLP
# eli5 - model explainability
RUN pip install tensorflow imblearn gensim nltk eli5

# extensions for lab
# TOC
RUN jupyter labextension install @jupyterlab/toc 
# snippets
RUN pip install jupyterlab_snippets
RUN jupyter labextension install @quentinandre/jupyterlab_snippets
# qgrid
RUN pip install qgrid
RUN jupyter nbextension enable --py --sys-prefix qgrid
RUN jupyter nbextension enable --py --sys-prefix widgetsnbextension
RUN jupyter labextension install qgrid
# variables inspector
RUN jupyter labextension install @lckr/jupyterlab_variableinspector


# notebook extensions
#RUN pip install jupyter_contrib_nbextensions && jupyter contrib nbextension install 


# TO DO - install scala and scala kernel for jupyter
#RUN apt install scala
# Check if all extensions work
# install actual spark or create separate spark master service (preferred)
