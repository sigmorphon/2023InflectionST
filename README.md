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

For 2023, we implement the novel UniMorph annotation schema that incorporates Anderson's layering approach (Guriel et al,2022). We continue to focus on \emph{interpretability} of morphological reinflection models while bringing more languages from different sources of data. 

In addition, this year we put a special focus on the diversity of writing systems.

### Task Details
This task will proceed in three phases: the ***Development Phase***, the ***Generalization Phase***, and the ***Evaluation Phase***. As the phases advance, more data and more languages will be released.

In the ***Development Phase***, we will provide training and development splits that should be used to *develop* your system.
We will refer to them as the *development languages*. The list of languages is below. There is a small training set for each languages and a large training set for languages with enough annotated paradigms.

In the ***Generalization Phase***, we will provide training and development splits for new languages where approximately half are genetically related (belong to the same family) and half are genetically *unrelated* (are isolates or belong to a different family) to the development languages.  We will also keep the genetically unrelated language *families* a surprise, though some languages will come from the same families as those in the Development Phase.

In the ***Evaluation Phase***, the participants’ models will be evaluated on held-out forms from all of the languages from the previous phases. The languages from the Development Phase and the Generalization Phase are evaluated simultaneously. The only difference is that there has been more time to construct a model for those languages released in the Development Phase. It follows that a model could easily overfit to or favor phenomena that are more frequent in languages presented in the Development Phase, especially if parameters are shared across languages. For instance, a model based on the morphological patterning of the Indo-European languages may end up with a bias towards suffixing and will struggle to learn prefixing or circumfixation, the degree to which only becomes apparent during experimentation on other languages whose inflectional morphology patterns differ. Of course, the model architecture itself could explicitly or implicitly favor certain word formation types (suffixing, prefixing, etc.).


#### Development Languages

| Language | Family| code | UM | Contributors |
|---|---|---|---|---|
| Arabic, Modern Standard | Semitic (Afro-Asiatic) | ara | https://github.com/unimorph/ara/ara_atb | Salam Khalifa, Nizar Habash |
| Georgian | Kartvelian | kat | https://github.com/unimorph/kat/ | Simon Guriel, Silvia Guriel-Agiashvili & Nona Atanelov |
| Hebrew | Semitic (Afro-Asiatic) | heb | https://github.com/unimorph/heb/ | Omer Goldman |
| Karelian | Finnic (Uralic) | krl | https://github.com/unimorph/krl/ | (Wiktionary, [VepKar](http://dictorpus.krc.karelia.ru/en)) |
| Sanskrit | Indo-Aryan | san | https://github.com/unimorph/san/ | Aryaman Arora |
| Tibetan | Sino-Tibetan | bod | https://github.com/unimorph/bod/ | Kat Vylomova |
| Japanese | TBA | TBA | TBA | Mana Ashida |
| Korean | TBA | TBA | TBA | Seunghun Lee, Jungyeul Park |
| Afrikaans | TBA | TBA | TBA | Peter Dirix |


#### Surprise Languages

| Language | Family| code | UM | Contributors |
|---|---|---|---|---|
| Central Kurdish | TBA | TBA | TBA | Aso Mahmudi, Sina Ahmadi |
| Ossetian | TBA | TBA | TBA | Samopriya Basu |
| Khanty | TBA | TBA | TBA | Karina Sheifer |
| Kullui | TBA | TBA | TBA | Elena Klyachko |
| Munda | TBA | TBA | TBA | Elena Klyachko |


## Timeline
  * February 15, 2023: Task website is complete, and accepting registrations to the mailing list

**Stage 1: Development Phase**
  * February 17, 2023: Training and development splits for development languages released; we invite participants to report errors
  * February 22, 2023: Neural and non-neural baselines for development languages released

**Stage 2: Generalization Phase**
  * March 24, 2023: Training and development splits for surprise languages released

**Stage 3: Evaluation Phase**
  * March 31, 2023: Test splits for all languages (both development and surprise) released
  * April 14, 2023: Participants submit test predictions on all languages
  * April 21, 2023: Results announced to participants

**Stage 4: Write-up Phase**
  * May 8, 2023: System papers due for review
  * May 22, 2023: Reviews back to participants
  * May 31, 2023: CR deadline; task paper due from organizers.

### Data

## Evaluation

***Evaluation script available here https://github.com/sigmorphon/2022InflectionST/tree/main/evaluation***


### Submission Instructions 

Please submit your team's results to omer.goldman@gmail.com CCing your team mates


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
Omer Goldman, Reut Tsarfaty, Khuyagbaatar Batsuren, Garrett Nicolai, David Yarowsky, Mans Hulden, Ryan Cotterell, Kat Vylomova

**Data Preparation**: 
Samopriya Basu, Aryaman Arora, Jungyeul Park, Seunghun Lee, Peter Dirix, Elena Klyachko, Andrew Krizhanovsky, Natalia Krizhanovsky, Karina Sheifer, Aso Mahmudi, Sina Ahmadi, Saliha Muradoglu, Mana Ashida, Salam Khalifa

## Part 2: Cognitively Plausible Morphophonological Generalization in Korean

### Task Description

### Data and Evaluation

### Timeline

### Submission Instructions 


### Organizers


### References


## Part 3: Models of Acquisition of Inflectional Noun Moprhology in Polish, Estonian, and Finnish

### Task Description
We propose a cross-linguistic modelling of child language acquisition to mediate between the theories of the acquisition of inflectional morphology. This will also allow for a more fine-grained analysis of generalizations made by contemporary connectionist models.

Children produce a range of errors (or more neutrally, non-adult-like productions) during development, but these productions are not distributed uniformly. Some broad trends emerge. First, there is a strong asymmetry between over-regularization errors and over-irregularization (Pinker and Prince, 1994) where over-production of productive patterns (e.g., "go-goed") is relatively common, while the over-production of potentially reasonable but non-productive patterns such as vowel mutation in English (e.g., "fry-\*frew" cf. "fly-flew") is quite rare. Studies estimate the rate of over-regularizations in child English past tense productions to be between 8\% and 10\%  (Maratsos, 2000; Maslen et al., 2004) while over-irregularization is under 0.2\% (Xu and Pinker, 1995). Similar patterns emerge when measuring German, Spanish, and Inuktitut learners' productions (Clahsen et al., 1992; Clahsen et al., 1993; Allen et al., 1996; Mayol et al., 2007). Another type of common error is the production of a higher-frequency form instead of a lower-frequency form (resulting in a different grammatical feature, e.g. case or gender).
See Lignos and Yang (2018) and Dąbrowska and Marcin Szczerbiński (2018) for more discussion. 

Still, the ``regular--irregular'' dichotomy comes from theories developed on the basis of languages with relatively impoverished morphology. Such languages present clear distinctions between regular and irregular word paradigms as in English past tense or German plural noun formation. However, in highly inflected languages this is often not the case. In this shared task, we aim to focus on noun case marking in three morphologically rich languages: Estonian, Finnish, and Polish. We will inspect the key factors accounting for the production of target forms: surface-form frequency (frequent target forms are more quickly and accurately retrieved or recognized as a whole unit), phonological neighborhood density (PND; forms having higher number of similar initial and target form neighbors are retrieved/produced quicker and more accurately), and interaction of these two factors.
(the PND effect is greater for low-frequency forms). Connectionist models should be able to predict the effects of surface-form frequency and PN size while rule-based approaches only present the latter. It is important to note that rule-based accounts identify PND classes (conjugation or declension) in which the behaviour is defined by the whole morphological paradigm. On the other hand, connectionist and exemplar-based approaches consider PND forms instead, i.e. focus on patterns emerging from initial-to-target form transformations.
The latter is also in line with children's language acquisition since they are unlikely to observe the whole paradigm, as mentioned earlier. In this task, we will consider both PND form and class.

For the current shared task iteration, we would like to use the data collected in Grandlund et al. (2019) which is available at [https://osf.io/bmncq/](https://osf.io/bmncq/). 
The data contains lemmas, their classes, word forms, their corresponding case, the form frequency, the number of phonological neighbors, the age and gender of each participant. Both lemma and word form are represented in orthographically and phonetically (IPA). Each class (out of 10 (Polish), 9 (Finnish) or 8 (Estonian)) is represented by three nouns. In addition, the case system has been restricted to 5 (Polish) or 6 (Finnish and Estonian) most commonly used cases. The form frequencies and PND counts were derived from child-directed speech corpora: Polish (Haman et al., 2011), Finnish (Kirjavainen et al., 2017), Estonian (Argus, 1998; Vija, 2007).

### Data and Evaluation

Models will be evaluated in two ways, by measuring accuracy and ability to generalize in a human-like way. Word-level accuracy and Levenshtein distance as in Part 1 provide standard measures for performance. Controlling for the confounds described above will facilitate cross-language comparison. 

Child learners generalize in particular ways. Systems will be evaluated according to how well they generalize and analyzed to determine in what ways they generalize similarly or differently to humans. For that, we will identify error types and compare them against those produced by children. We will also evaluate the effects of the token frequency, type frequency, and phonological neighborhood density.

### Timeline
  * February 15, 2023: Task website is complete, and accepting registrations to the mailing
     list
  * February 17, 2023: Data preparation is complete, and training and evaluation data is released to participants
  * February 22, 2023: Baseline systems released to participants
  * March 31, 2023: Test data is available for participants
  * April 14, 2023: Final Submissions are due.
  * April 21, 2023: Results announced to participants
  * May 8, 2023: System papers due for review
  * May 22, 2023: Reviews back to participants
  * May 31, 2023:  CR deadline; task paper due from organizers

### Submission Instructions 


### Organizers
Kat Vylomova, Tiago Pimentel, Jordan Kodner, Ryan Cotterell, Ben Ambridge

### References

# Participation Policy

We do not tolerate harassment in our shared task. Anyone who has been previously found to have harassed one of the organizers cannot participate in our task in any capacity. There are too few organizers for us to accomodate the harasser in a manner that ensures the safety of their victims. (This policy was written on June 22nd and cannot be applied retroactively, but will be in place for all future iterations of the task.)

