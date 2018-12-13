# Project Title

Topic Models for Healthcare 

## Getting Started

### Built With

* [nltk](https://www.nltk.org/) - Python package for natural language tooklit. 
* [gensim](https://radimrehurek.com/gensim/) - Python package for topic modelling. 
* [Multi-Faceted Topic Modeling Package](http://cmci.colorado.edu/~mpaul/downloads/mftm.php) - Built with Java and Python, a package for lda, cclda and TAM. 


### Prerequisites

Python3， Python2, nltk, gensim, Java

In order to run cclda package, we need to run the following commands:

```
javac LearnTopicModel.java

java LearnTopicModel -model cclda -input corpus_clean.txt -iters 2000 -Z 10

python2 topwords_cclda.py corpus_clean.txt.assign > out.txt
```

## Design Ideas

### letter bigram model
In first letter based bigram model, I plotted the distribution of the letter bigrams and it turns out 0 is not prevailing (also agrees intuitively, because letters have only 26*26 combinations); and letter bigram is performing decently. 

### word bigram model

We need smoothing because the word matrix is super sparse and it could range to more than 7 million entries, resulting lots of zeros. For word bigrams, I followed the instructions in the lab and used a general idea for program designing; it allows multlple parameters to be changed and is more robust. It could potentially train models for more than these three languages and use trigram or other degrees of gram if necessary. 

For more details please refer to the notebook. 


## Findings 

Detialed findings is included in the jupyter notebook, please refer to the notebook.

### Task 2

1. Without lemmatization

bill: 'patient asked could hand never problem even tip called bill',

skin: 'told test father procedure first skin family woman arm pap',

eye: 'son said call mother goodman eye flu physical one steroids',

surgery: "surgery pain would breast dad surgeon 've clinic knee ask",

family: 'doctor husband schwartz daughter get visit therapy patel evan dr.shakiba',

non-english (noisy): 'dr. shakiba pasquale hollie rivadeneira dyer kolb comeau kurtz germin',


appointment: 'appointment see exam back lopez child room routine ever body',

cancer: 'office insurance staff doc really cancer wife code kwant company',

medication: "n't time nurse mckay patients always medication techs waiting simponi",

tooth: 'tooth like nose thyroid best went hip cavity germin results'

2. with lemmatization

appointment: "pain appointment could wife dad 've knee ultrasound ask months",

test: 'told test like back never pap results jaller blomain fillers',

non-english(noise) 'dr. office shakiba pasquale hollie rivadeneira dyer kolb comeau kurtz',

breast: 'surgery would patient breast exam went room surgeon kakani comp',

tooth: 'said tooth see get nose best really physical therapy cavity',

medication: 'mother procedure first medication skin eye flu problem family one',

thyroid: "n't thyroid mckay hip health techs vanessa simponi tissue problems",

child: 'son call father doc visit lopez child goodman germin susie',

family: 'doctor husband schwartz asked daughter cancer patel evan dr.shakiba kidney',

insurance: 'time insurance staff hand nurse patients always code kwant company'


the lemmatized version is a litter better than the one without, but the improvement is marginal in this data set. However the improvement is marginal here, and this might be because the data is too messy and less organized than supposed.  

### Extra Credit

Detailed results in notebook

It's not really better than those with 10 topics, since

1) when the number of topic increases, time complexity for training and convergence increases;
2) the topic models are not really improved they are getting more noises than 10 topics.

cclda is running slower than lda, this might be bacause that cclda is using hierarchechal Bayes framework so it brings more calculation to be done. 

topic 1: appointment; office,appointment,get,see,wait,call,time,room,staff,minutes

topic 2: blood; n't,went,could,told,would,blood,doctor,see,got,took 

topic 3: insurance; n't,get,insurance,want,would,know,even,like,people,doctor

topic 4: question; dr.,time,patients,doctor,patient,questions,care,listen,always,good

topic 5: recommendation; dr.,staff,doctor,would,recommend,manner,office,bedside,great,anyone

topic 6: results; dr.,would,went,n't,one,work,look,could,results,done 

topic 7: (noisy this one): doctor,dr.,ever,one,doctors,care,patients,life,many,years

topic 8: feelings; dr.,like,feel,n't,made,never,would,first,felt,even

topic 9: surgery; surgery,pain,dr.,back,would,went,hospital,months,surgeon,another

topic 10: prescription; dr.,medical,treatment,patient,health,physician,diagnosis,condition,care,issues,without

one of those topics is noisy, while the rest are good. the result is generally way better than lda. 


## Authors

* **Kehan Pan** - [Github](https://github.com/pankh13)

