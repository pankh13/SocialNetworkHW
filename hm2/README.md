# Project Title

Ngram NLP algorithm. 

## Getting Started

This is an APP based on Ngram for recognizing 


### Built With

* [Collections](https://docs.python.org/3/library/collections.html) - Internal Python package for collections
* [Itertools](https://docs.python.org/3/library/itertools.html) - Internal Python package for iterations
* [langid](https://github.com/saffsd/langid.py) - A standalone Language Identification (LangID) tool. Note that, it is also built on Ngram but with larger training models on 97 languages.  

### Prerequisites

Python3, lanid (Need to be installed first via:)

```
pip install langid
```

## Design Ideas

### letter bigram model
In first letter based bigram model, I plotted the distribution of the letter bigrams and it turns out 0 is not prevailing (also agrees intuitively, because letters have only 26*26 combinations); and letter bigram is performing decently. 

### word bigram model

We need smoothing because the word matrix is super sparse and it could range to more than 7 million entries, resulting lots of zeros. For word bigrams, I followed the instructions in the lab and used a general idea for program designing; it allows multlple parameters to be changed and is more robust. It could potentially train models for more than these three languages and use trigram or other degrees of gram if necessary. 

For more details please refer to the notebook. 


## Evaluation 

### letter bigram model

|   |	predicted_Italian |	predicted_English |	predicted_French |
| ------------- | ------------- | ------------- |------------- |
|true_Italian |	97 |	0 |	3 |
|true_English	| 9 | 91 |	0 |
|true_French |	14 |	1 |	85 |

accuracy is estimated at 91.0%; 

### word bigram model (add-one smoothing)

|  | predicted_Italian |	predicted_French |	predicted_English |
| ------------- | ------------- | ------------- |------------- |
|true_Italian |	100 |	0 |	0 |
|true_French |	0	| 100 |	0 |
|true_English	| 0	 | 0 |	100 |

accuracy is estimated at 100.0%; 

### word bigram model (Good-Turing smoothing)

| |predicted_French |	predicted_English |	predicted_Italian |
| ------------- | ------------- | ------------- |------------- |
|true_French |	100 |	0 |	0 |
|true_English |	2 |	97 |	1 |
|true_Italian |	13 |	4	| 83 |

accuracy is estimated at 93.3%.

## Benckmark

### langid

|	| predicted_French |	predicted_English |	predicted_Italian |	predicted_other |
| ------------- | ------------- | ------------- |------------- |------------- |
|true_French |	100	| 0 |	0	| 0 |
|true_English |	0 |	99	| 0	| 1 |
|true_Italian	| 0 |	0	| 100 |	0 |
|true_other	 | 0 |	0 |	0 |	0 |

Interetingly, this langid package did really well despite making only one mistake on English. We could research later into the techniques it is using.  

## Authors

* **Kehan Pan** - [Github](https://github.com/pankh13)
