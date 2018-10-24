# Research Documents Curation with NLP

Contributors: Bowen Chen, Ao Luo, Yihan Luo, Ho Kwan Henry Zhang

**Description**

Applied Finance Project from UCLA Anderson, using natural language processing techniques to classify and summarize quantitative finance research papers. Following the technique proposed by Meng's team, we implemented a research paper classification engine by using weakly supervised NLP technique in order to build a document classifier. The original paper could be found [here]() 

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

**Roadmap**

1. Download 1000+ papers in pdf format from arxiv (Completed)
2. Transformed 1000 papers in pdf format to txt format (Completed)
3. Train a word embedding using gensim (Completed)
4. To be continued..

**Specifications**

*Downloading papers*

We downloaded 1013 quantitative finance papers from arxiv using the API provided, taking around 2 hours to process.

*Transform papers*

We transform the 1013 papers into txt format using pdf2txt. 1007 papers were valid. The txt files could then be read in as a list of strings under the same directory. This process could only be completed in python 2

*Training Word Embedding*

We implemented the word embedding training in gensim topic modeling package in python 3.
The embedding was trained on the entire length of 1007 documents, with 50 classes (chosen empircally). Prior to feeding into the traning algorithm, we preprocessed data in 4 different aspects

* remove white spaces
* remove words with length less than 2
* remove punctuations
* remove numbers

We did not remove stopwords, since we believe this word embedding matrix will be used for generating pseudo documents, which will definetely require the presence of these words

We also did not perform word stemming. Stemming the word will not work particularly well in finance, since most of the keywords in finance are derivative words already (see equity, trading, fixed income etc.). Performming stemming will distort the original meaning of the word. Taking equity for example, if we perform stemming on equity, it will become equal, which destroys the oringinal meaning of our keyword.
