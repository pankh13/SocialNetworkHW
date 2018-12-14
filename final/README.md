# Project Title

Sentiment Analysis

## Getting Started

### Built With

* [fasttext](https://fasttext.cc/) - Library for efficient text classification and representation learning. 
* [gensim](https://radimrehurek.com/gensim/) - Python package for topic modelling. 
* [nltk](https://www.nltk.org/) - Python package for natural language tooklit. 


### Prerequisites

Python3， C++, Java

In order to run fasttext package, we need to download the github repo.

```
make

./fasttext # run fasttext and see help documentation

./fasttext supervised -input /home/eric/Dropbox/490/final/input_fasttext.txt -output /home/eric/Dropbox/490/final/model_fasttext -label __label__ -epoch 100 -lr 0.5 -wordNgrams 1

./fasttext test /home/eric/Dropbox/490/final/model_fasttext.bin /home/eric/Dropbox/490/final/test_fasttext.txt 1
```
Note that, since model_fasttext.bin is 800 MB large we are not including it here. 

## Design Ideas

see the jupyter notebook and pdf report for details. 

## Findings 

Detialed findings is included in the jupyter notebook, please refer to the notebook.

### Task 1


| Best Baseline Model | Best Model   |
| ------ | -------- |
|  85%      |    88%      |



## Authors

* **Kehan Pan** - [Github](https://github.com/pankh13)

