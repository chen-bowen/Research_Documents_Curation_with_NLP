# Research Documents Curation with NLP

Contributors: Bowen Chen, Ao Luo, Yihan Luo, Ho Kwan Henry Zhang

**Description**

Applied Finance Project from UCLA Anderson, using natural language processing techniques to classify and summarize quantitative finance research papers. Following the technique proposed by Meng's team, we implemented a research paper classification engine by using weakly supervised NLP technique in order to build a document classifier.

**Required Packages**

The following packages are already pre-built with Anaconda distribution

* numpy
* pandas
* seaborn
* glob
* os

The following packages are used to complete NLP specific tasks

* [Gensim](https://radimrehurek.com/gensim/) - used to train word embedding
* [NLTK](https://www.nltk.org/) - used to preprocess text documents

The following packages are used to retrieve and transform the research documents

* [arxiv](https://arxiv.org/help/api/index) - used to perform batch downloads for research papers in pdf format from arxiv
* [pdf2txt](https://pypi.org/project/pdf2text/) - used to transform pdf files to txt files

The main algorithm is implemented in python 3, except for pdf2txt, which used python 2 

