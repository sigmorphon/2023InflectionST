# SIGMORPHON–UniMorph Shared Task on Typologically Diverse and Acquisition-Inspired Morphological Inflection Generation

SIGMORPHON’s eigth installment of its inflection generation shared task will be divided into three parts:

+ ***Part 1***: [Typologically Diverse Morphological (Re-)Inflection](https://github.com/sigmorphon/2023InflectionST/tree/main/part1)
+ ***Part 2***: [Cognitively Plausible Morphophonological Generalization in Korean](https://github.com/sigmorphon/2023InflectionST/tree/main/part2/README.md)
+ ***Part 3***: [Models of Acquisition of Inflectional Noun Moprhology in Polish, Estonian, and Finnish](https://github.com/sigmorphon/2023InflectionST/tree/main/part3/README.md)

Please join our [Google Group](https://TBA) to stay up to date.

***Click here to [register for the task](https://forms.gle/TBA)!***


## Part 1: Typologically Diverse Morphological (Re-)Inflection


### Task Summary


In this shared task, participants will design a model that learns to generate morphological inflections from a lemma and a set of morphosyntactic features of the target form. Each language in the task has its own training, development, and test splits. Training and development splits contain triples, each consisting of a lemma, a target form, and a set of morphological features, provided in the UniMorph format (the “Data” section below provides an example of input format). Test splits only provide lemmas and morphological tags: your model will need to predict the missing target form.

The model should be general enough to work for natural languages of any typological patterning. For example, Tagalog verbs exhibit [circumfixation](https://en.wikipedia.org/wiki/Circumfix); thus, a model with a strong inductive bias towards suffixing will likely not work well for Tagalog.


### Task Details
This task will proceed in three phases: the ***Development Phase***, the ***Generalization Phase***, and the ***Evaluation Phase***. As the phases advance, more data and more languages will be released.

In the ***Development Phase***, we will provide training and development splits that should be used to *develop* your system.
We will refer to them as the *development languages*. The list of languages is below. There is a small training set for each languages and a large training set for languages with enough annotated paradigms.

In the ***Generalization Phase***, we will provide training and development splits for new languages where approximately half are genetically related (belong to the same family) and half are genetically *unrelated* (are isolates or belong to a different family) to the development languages.  We will also keep the genetically unrelated language *families* a surprise, though some languages will come from the same families as those in the Development Phase.

In the ***Evaluation Phase***, the participants’ models will be evaluated on held-out forms from all of the languages from the previous phases. The languages from the Development Phase and the Generalization Phase are evaluated simultaneously. The only difference is that there has been more time to construct a model for those languages released in the Development Phase. It follows that a model could easily overfit to or favor phenomena that are more frequent in languages presented in the Development Phase, especially if parameters are shared across languages. For instance, a model based on the morphological patterning of the Indo-European languages may end up with a bias towards suffixing and will struggle to learn prefixing or circumfixation, the degree to which only becomes apparent during experimentation on other languages whose inflectional morphology patterns differ. Of course, the model architecture itself could explicitly or implicitly favor certain word formation types (suffixing, prefixing, etc.).


#### Development Languages
#### Surprise Languages
## Timeline

### Data

## Evaluation

***Evaluation script available here https://github.com/sigmorphon/2022InflectionST/tree/main/evaluation***


### Submission Instructions 

Please submit your team's results to jordan.kodner@stonybrook.edu CCing your team mates by TBA


### Baselines

***Baseline results available here https://github.com/sigmorphon/2023InflectionST/tree/main/evaluation***

The organizers will provide one non-neural and one neural baseline for the participants’ consumption.
Its use is optional and is provided to help the participants develop their own models faster.
The neural baseline is a multilingual transformer ([Vaswani et al., 2017](https://papers.nips.cc/paper/7181-attention-is-all-you-need.pdf)). The version of this model adopted for character-level tasks currently holds the state-of-the-art on the 2017 SIGMORPHON shared task data. The transformer takes the lemma and morphological tags as input and outputs the target inflection. Given the low-resource setup, a single model will be trained on all languages. Additionally, we consider the data augmentation technique used by [Anastasopoulos and Neubig (2019)](https://www.aclweb.org/anthology/D19-1091/) as another baseline.

To run the non-neural baseline use command:
```bash
$ python baselines/nonneural/baseline.py --path part1/development_languages/
```

To run the neural baseline first download and augment [(Anastasopoulos and Neubig, 2019)](https://arxiv.org/abs/1908.05838) the data
```bash
$ mkdir part1/original
$ cp part1/development_languages/* part1/original

$ bash baselines/neural/example/sigmorphon2021-shared-tasks/augment.sh
$ python baselines/neural/example/sigmorphon2021-shared-tasks/task0-build-dataset.py all
```

Then, to run the transducer [(Wu et al, 2021)](https://arxiv.org/abs/2005.10213), one model per language.
```bash
$ bash baselines/neural/example/sigmorphon2021-shared-tasks/task0-launch.sh
```


### Organizers

**Task Logistics**: 

**Data Preparation**: 


## Part 2: Cognitively Plausible Morphophonological Generalization in Korean

### Task Description

### Data and Evaluation

### Timeline

### Submission Instructions 


### Organizers


### References


## Part 3: Models of Acquisition of Inflectional Noun Moprhology in Polish, Estonian, and Finnish

### Task Description

### Data and Evaluation

### Timeline

### Submission Instructions 


### Organizers


### References

# Participation Policy

We do not tolerate harassment in our shared task. Anyone who has been previously found to have harassed one of the organizers cannot participate in our task in any capacity. There are too few organizers for us to accomodate the harasser in a manner that ensures the safety of their victims. (This policy was written on June 22nd and cannot be applied retroactively, but will be in place for all future iterations of the task.)

