# SIGMORPHON–UniMorph Shared Task on Typologically Diverse and Acquisition-Inspired Morphological Inflection Generation

SIGMORPHON’s eigth installment of its inflection generation shared task will be divided into three parts:

+ ***Part 1***: [Typologically Diverse Morphological (Re-)Inflection](https://github.com/sigmorphon/2023InflectionST/tree/main/part1)
+ ***Part 2***: [Cognitively Plausible Morphophonological Generalization in Korean](https://github.com/sigmorphon/2023InflectionST/tree/main/part2/README.md)
+ ***Part 3***: [Models of Acquisition of Inflectional Noun Moprhology in Polish, Estonian, and Finnish](https://github.com/sigmorphon/2023InflectionST/tree/main/part3)

***Click here to [register for the task](https://docs.google.com/forms/d/e/1FAIpQLSfA802Luvxn4oAadpmF1lHID_VERAonlDhQ6voY6tXVGEfQnQ/viewform)!***


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

| Language         | Family                       | code | UM                               |
|------------------|------------------------------|------|----------------------------------|
| Amharic          | Semitic (Afro-Asiatic)       | amh  | https://github.com/unimorph/kat/ |
| Arabic, Egyptian | Semitic (Afro-Asiatic)       | arz  | https://github.com/unimorph/arz/ |
| Danish           | Germanic (Indo-European)     | dan  | https://github.com/unimorph/dan/ |
| English          | Germanic (Indo-European)     | eng  | https://github.com/unimorph/eng/ |
| Finnish          | Finnic (Uralic)              | fin  | https://github.com/unimorph/fin/ |
| French           | Romance (Indo-European)      | fra  | https://github.com/unimorph/fra/ |
| Ancient Greek    | Helenic (Indo-European)      | grc  | https://github.com/unimorph/grc/ |
| Hebrew           | Semitic (Afro-Asiatic)       | heb  | https://github.com/unimorph/heb/ |
| Hungarian        | Ugric (Uralic)               | hun  | https://github.com/unimorph/hun/ |
| Armenian         | Armenian (Indo-European)     | hye  | https://github.com/unimorph/hye/ |
| Italian          | Romance (Indo-European)      | ita  | https://github.com/unimorph/ita/ |
| Japanese         | Japonic                      | jap  | TBA                              |
| Georgian         | Kartvelian                   | kat  | https://github.com/unimorph/kat/ |
| Macedonian       | Balto-Slavic (Indo-European) | mkd  | https://github.com/unimorph/mkd/ |
| Russian          | Balto-Slavic (Indo-European) | rus  | https://github.com/unimorph/rus/ |
| Spanish          | Romance (Indo-European)      | spa  | https://github.com/unimorph/spa/ |
| Swahili          | Bantu (Niger-Congo)          | swa  | https://github.com/unimorph/swa/ |
| Turkish          | Turkic                       | tur  | https://github.com/unimorph/tur/ |

#### Surprise Languages

| Language     | Family                        | code | UM                               |
|--------------|-------------------------------|------|----------------------------------|
| Navajo       | Southern Athabaskan (Na-Dené) | nav  | https://github.com/unimorph/nav/ |
| Arabic, Gulf | Semitic (Afro-Asiatic)        | afb  | https://github.com/unimorph/afb/ |
| Albanian     | Indo-European                 | sqi  | https://github.com/unimorph/sqi/ |
| German       | Germanic (Indo-European)      | deu  | https://github.com/unimorph/deu/ |
| Sami         | Finnic (Uralic)               | sme  | https://github.com/unimorph/sme/ |
| Belarusian   | Balto-Slavic (Indo-European)  | bel  | https://github.com/unimorph/bel/ |
| Khaling      | Kiranti (Sino-Tibetan)        | klr  | https://github.com/unimorph/klr/ |
| Sanskrit     | Indo-Aryan (Indo-European)    | san  | https://github.com/unimorph/san/ |


## Timeline

**Stage 1: Development Phase**
  * March 1, 2023: Training and development splits for development languages released; we invite participants to report errors
  * March 15, 2023: Neural and non-neural baselines for development languages released

**Stage 2: Generalization Phase**
  * April 7, 2023: Training and development splits for surprise languages released

**Stage 3: Evaluation Phase**
  * April 14, 2023: Test splits for all languages (both development and surprise) released
  * April 21, 2023: Participants submit test predictions on all languages
  * April 25, 2023: Results announced to participants

**Stage 4: Write-up Phase**
  * May 8, 2023: System papers due for review
  * May 22, 2023: Reviews back to participants
  * May 31, 2023: CR deadline; task paper due from organizers.

### Data

The training and development data are provided in a simple utf-8 encoded text format for both the development and surprise languages.
Each line in a file is an example that consists of a lemma, a word form and 
the corresponding morphosyntactic descriptions (MSDs) provided as a set of features, separated by semicolons.
Some features are complex and composed of sub-features seperated by commas inside parentheses.
Here we present an example from the Spanish training data (the Spanish verb “cancelar” means “to call off” in English):
```
cancelar	V;IMP;ACC(2,SG);NOM(INFM,2,SG)	cancélate
```
In this example features that pertain to a specific verb argument are treated as sub-features of the corresponding case feature.

In addition, case features for nominal and adjectival inflections are layered on top the other features as in this example from Turkish:
```
asimptot	N;NOM(PL;PSS(1,PL))	asimptotlarımız
```
(here, again, some features are sub-features of the possessor)

The training data for each language includes 10,000 examples, in addition to a validation and test set of 1,000 examples each.
The data is split such that there is no overlap in lemmas between the splits.

Validation data is provided in 2 versions: uncovered version that includes the target inflections similarly to the train set, 
and a covered version that do not include the target similarly to the test set. The test set will be released at the beginning of the test phase (see below). 


### Submission Instructions 

Please submit your team's results to omer.goldman@gmail.com CCing your team mates


### Baselines

***Baseline results will available at the end of the test phase, [here](https://github.com/sigmorphon/2023InflectionST/tree/main/part1/evaluation)***


The baselines models are [here](https://github.com/sigmorphon/2023InflectionST/tree/main/part1/baselines)

### Organizers

**Task Logistics**: 
Omer Goldman, Reut Tsarfaty, Khuyagbaatar Batsuren, Garrett Nicolai, David Yarowsky, Mans Hulden, Ryan Cotterell, Kat Vylomova

**Data Preparation**: 
Samopriya Basu, Aryaman Arora, Jungyeul Park, Seunghun Lee, Peter Dirix, Elena Klyachko, Andrew Krizhanovsky, Natalia Krizhanovsky, Karina Sheifer, Aso Mahmudi, Sina Ahmadi, Saliha Muradoglu, Mana Ashida, Salam Khalifa

## Part 2: Cognitively Plausible Morphophonological Generalization in Korean

### Task Description

This shared task focuses specifically on data that has been argued to be relevant to whether human language users generate language in a derivation-based (serial) or output-oriented  (parallel) manner. This question of cognitive architecture has clear parallels in computational models of language, where there is a range of statistical, mathematical, and neural methods that embody both the extreme ends, and wide middle, of this architectural range. We hope the challenge will be of interest to the SIGMORPHON community because it involves learning from sparse data, and trying to match human out-of-domain generalization to novel items (a wug-test). We think the challenge will be interesting for linguists because there is still uncertainty at the theoretical level about which tools are best equipped to model the knowledge that humans have of this process, and so the data we gather will be helpful for refining these cognitive questions.

We bring to bear data from the interaction of two variable processes in Korean, Post-Obstruent Tensification (POT) and Cluster Simplification (CS), which are active in the language broadly. When their conditioning environments overlap, we can observe crucial evidence about how (or whether) the processes are ordered (Kim-Renaud, 1974; Sohn, 1999, Kim, 2003).

CS targets underlying consonant clusters in coda position, yielding simplification when followed by a C-initial suffix, /anc-nɨn/ → [an-nɨn] ‘to sit-COMP’; /kulm-nɨn/ → [kum-nɨn] ‘to starve-COMP’. CS is variable depending on verb identity and final consonant place. POT causes a lenis consonant to tensify after an obstruent, e.g. /cap-ta/ → [cap-t\*a] ‘to hold-DECL’; /pat-ko/ → [pat-k\*o] ‘to receive-and’. When the first consonant of the cluster is /l/ and both processes are applicable, an opaque surface form can arise, e.g. in [nʌl-t\*a], we may see un-licensed post-liquid tensification, which is generally absent in the language (e.g. /cul-ta/ [cul-ta], *[cul-t\*a] ‘to decrease-DECL’). 

Both processes exhibit variation both within and across word types, and so speakers likely represent both item-specific and grammar-wide generalizations about how these processes interact. The learning data is also quite sparse: in a child-directed speech corpus of ~53,000 words, the environment crucial to learn an ordering appears only 12 times (The Ko Corpus, Ko et al. 2021). In a corpus of adult speech, the forms occur a total of about 1,000 times in ~900,000 phrases (The NIKL Korean Dialogue Corpus; National Institute of Korean Language, 2021). This poses a challenge for models that need large amounts of data to reliably learn linguistic patterns.

### Data and Evaluation

The task is as follows: predict human responses to a generalization task (_wug_-test), involving existing high-frequency, existing low-frequency, and novel verbs. 

Verbs come in two types, those which have a simplex coda, and so provide an environment to observe POT in the absence of the complex coda, and those which have a lC coda, where the environments for POT and CS can overlap. Each type has cases that are affixed with suffixes that start with a vowel (no POT or CS expected for lC verbs), suffixes that start with a sonorant (CS expected in lC verbs, POT not possible), or those that start with an obstruent (POT and CS applicable in lC verbs). 

The primary training data consists of the experimental responses of 15 subjects, plus 3 for development, and the models will be evaluated on how well they predict the vector of features corresponding to the answer given: POT, CS (two types possible, see explanatory notes), nasalization (orthogonal but present in nasal-initial suffixes), and lateralization (possible but unlikely). Depending on the type of stem and suffix, any of these features may be on (if the process applies), off (if not), or NA (if not applicable). Models will be evaluated using the likelihood they assign to held-out responses to the same experimental items from 5 unseen participants. Of particular interest are models that are based primarily on the lexical and corpus data and treat the experimental data as a learning target; learning purely based on the experimental data alone is perhaps of less linguistic interest, since it doesn't try to mimic what humans are doing (learning from sparse and gappy naturalistic data, and generalizing out of sample on the wug test).

Auxiliary training data is a list of all -lC verbs in a Korean dictionary, the distribution of words and their forms (featurized the same way as the experiment) in a corpus of adult-directed speech, and a corpus of infant-directed speech. You are not required to incorporate this info into the model, but you might find it helpful - this is our best current estimate of the type of learning data available to humans learning the same processes.

### Timeline

  * February 15, 2023: Task website is complete, and accepting registrations to the mailing
     list
  * February 17, 2023: Data preparation is complete, and training and evaluation data is released to participants
  * February 22, 2023: Baseline systems released to participants
  * March 31, 2023: Test data is available for participants
  * April 21, 2023: Final Submissions are due
  * April 25, 2023: Results announced to participants
  * May 8, 2023: System papers due for review
  * May 22, 2023: Reviews back to participants
  * May 31, 2023:  CR deadline; task paper due from organizers

### Submission Instructions 

Please submit your team's results to canaanbreiss1@gmail.com, CC'ing your team.

### Organizers

Canaan Breiss (primary), Jinyoung Jo

Contact: canaanbreiss1@gmail.com

### References

Kim, S. (2003). Phyocwun Palum Silthay Cosa II [A Survey of Standard Pronunciation II]. National Institute of Korean Language, Seoul.

Kim-Renaud, Y.-K. (1974). Korean Consonantal Phonology. PhD thesis, University of Hawaii.

Ko, E.-S., Jo, J., On, K.-W., and Zhang, B.-T. (2020). Introducing theKo corpus of Korean mother–child interaction. Frontiers in Psychology, 11:3698.

National Institute of Korean Language (2021). NIKL Korean Dialogue Corpus (audio) 2020(v.1.3).

Sohn, H.-M. (1999). The Korean Language. Cambridge University Press, Cambridge, UK.



## Part 3: Models of Acquisition of Inflectional Noun Morphology in Polish, Estonian, and Finnish

### Task Description
We propose a cross-linguistic modelling of child language acquisition to mediate between the theories of the acquisition of inflectional morphology. This will also allow for a more fine-grained analysis of generalizations made by contemporary connectionist models.
***The model’s task here is to simulate kids’ performance in our elicited production experiment***, and we deliberately chose nouns that young kids would know. Here, ***the aim is to build a model that shows childlike item-by-item error rates. So this involves NOT building the best model, but building a model with some flaws that are supposed to simulate “flaws” in child learners*** – i.e., high rates of forgetting, high rates of interference from other forms of the same noun, “slow” learning, slow/low generalization”.

Children produce a range of errors (or more neutrally, non-adult-like productions) during development, but these productions are not distributed uniformly. Some broad trends emerge. First, there is a strong asymmetry between over-regularization errors and over-irregularization (Pinker and Prince, 1994) where over-production of productive patterns (e.g., "go-goed") is relatively common, while the over-production of potentially reasonable but non-productive patterns such as vowel mutation in English (e.g., "fry-\*frew" cf. "fly-flew") is quite rare. Studies estimate the rate of over-regularizations in child English past tense productions to be between 8\% and 10\%  (Maratsos, 2000; Maslen et al., 2004) while over-irregularization is under 0.2\% (Xu and Pinker, 1995). Similar patterns emerge when measuring German, Spanish, and Inuktitut learners' productions (Clahsen et al., 1992; Clahsen et al., 1993; Allen et al., 1996; Mayol et al., 2007). Another type of common error is the production of a higher-frequency form instead of a lower-frequency form (resulting in a different grammatical feature, e.g. case or gender).
See Lignos and Yang (2018) and Dąbrowska and Marcin Szczerbiński (2018) for more discussion. 

Still, the ``regular--irregular'' dichotomy comes from theories developed on the basis of languages with relatively impoverished morphology. Such languages present clear distinctions between regular and irregular word paradigms as in English past tense or German plural noun formation. However, in highly inflected languages this is often not the case. In this shared task, we aim to focus on noun case marking in three morphologically rich languages: Estonian, Finnish, and Polish. We aim to inspect the key factors accounting for the production of target forms: surface-form frequency (frequent target forms are more quickly and accurately retrieved or recognized as a whole unit), phonological neighborhood density (PND; forms having higher number of similar initial and target form neighbors are retrieved/produced quicker and more accurately), and interaction of these two factors.
(the PND effect is greater for low-frequency forms). Connectionist models should be able to predict the effects of surface-form frequency and PN size while rule-based approaches only present the latter. It is important to note that rule-based accounts identify PND classes (conjugation or declension) in which the behaviour is defined by the whole morphological paradigm. On the other hand, connectionist and exemplar-based approaches consider PND forms instead, i.e. focus on patterns emerging from initial-to-target form transformations. The latter is also in line with children's language acquisition since they are unlikely to observe the whole paradigm, as mentioned earlier. In this task, we will consider both PND form and class.

### Data

For the current shared task iteration, we use the data collected in Grandlund et al. (2019).
The data contains lemmas, word forms, their corresponding case, the lemma frequency, and the form frequency. Both lemma and word form are represented in orthographically and phonetically (IPA). 

The study only focuses on singular forms and is restictied to most commonly used cases in each language.
Each class (out of 10 (Polish), 9 (Finnish) or 8 (Estonian)) is represented by three nouns. In addition, the case system has been restricted to 5 (Polish) or 6 (Finnish and Estonian) most commonly used cases. The lemma and form frequencies were derived from child-directed speech corpora: Polish (Haman et al., 2011), Finnish (Kirjavainen et al., 2017), Estonian (Argus, 1998; Vija, 2007).

An example of training data (for the Polish lemma "zdrowie", "health"):

```
zdrowie GEN     zdrowia zdrɔvjɛ zdrɔvja 6
```
The data comes in the TSV format. The training data has the following columns: the lemma, the target case, the target form, the lemma IPA, the form IPA, the form frequency

The test data provides the lemma, the target case, the correct target form, their IPA and the form frequency in the child speech corpus, and also the ratio of correct predictions among children. You will see the correct target forms in the training data. ***The task does not require predicting the correct target form! Instead, the systems need to make predictions about the forms that children are more likely to produce based on the provided training data.*** More specifically, for each test sample the systems need to provide ***the top 10 most likely forms with their probabilities***. The forms should be provided in IPA.

### Evaluation

Models will be evaluated in their ability to generalize in a child-like way. Word-level accuracy and Levenshtein distance as in Part 1 provide standard measures for performance. We will also calculate a model-child correlation on the proportion of correct vs error responses by item (sample).
The predicted IPA form will be scored as correct vs error and this proportion (from multiple runs of the same model) will be correlated against the same proportion for kids.

We will also compare the error types. Child learners generalize in particular ways, and we do want the models’ errors to be qualitatively similar to those produced by kids. It would be a bad model if, for example, all its errors were just repeating the nominative form, as this isn’t what kids do. B
Systems will be evaluated according to how well they generalize and analyzed to determine in what ways they generalize similarly or differently to humans. For that, we will identify common error types and compare them against those produced by children. We will also evaluate the effects of the token frequency, type frequency, and phonological neighborhood density.

### Timeline
  * February 15, 2023: Task website is complete, and accepting registrations to the mailing
     list
  * February 17, 2023: Data preparation is complete, and training and evaluation data is released to participants
  * February 22, 2023: Baseline systems released to participants
  * March 31, 2023: Test data is available for participants
  * April 21, 2023: Final Submissions are due
  * April 25, 2023: Results announced to participants
  * May 22, 2023: System papers due for review
  * May 31, 2023:  CR deadline; task paper due from organizers

### Submission Instructions 
Please submit your team's results to evylomova@gmail.com CCing your team


### Organizers
Kat Vylomova, Tiago Pimentel, Jordan Kodner, Ryan Cotterell, Ben Ambridge

### References
Sonia Granlund, Joanna Kolak, Virve Vihman, Felix Engelmann, Elena VM Lieven, Julian M Pine, Anna L Theakston, and Ben Ambridge. Language-general and language-specific phenomena in the acquisition of inflectional noun morphology: A cross-linguistic elicited-production study of Polish, Finnish and Estonian. Journal of Memory and Language, 107:169–194, 2019

Steven Pinker and Alan Prince. Regular and irregular morphology and the psychological status of rules of grammar. The reality of linguistic rules, 321:51, 1994

Michael Maratsos. More overregularizations after all: New data and discussion on Marcus, Pinker, Ullman, Hollander, Rosen & Xu. Journal of Child Language, 27(1):183–212, 2000

Robert JC Maslen, Anna L Theakston, Elena VM Lieven, and Michael Tomasello. A dense corpus study of past tense and plural overregularization in English. Journal of Speech, Language, and Hearing Research, 47(1319-1333), 2004.

Fei Xu and Steven Pinker. Weird past tense forms. Journal of Child Language, 22(3):531–556, 1995

Harald Clahsen, Monika Rothweiler, Andreas Woest, and Gary Marcus. Regular and irregular inflection in the acquisition of German noun plurals. Cognition, 45:225–255, 1992

Harald Clahsen and Monika Rothweiler. Inflectional rules in children’s grammars: Evidence from German participles. In Yearbook of morphology. 1992, pages 1–34. Springer, 1993

Shanley Allen. Aspects of argument structure acquisition in Inuktitut, volume 13. John Benjamins Publishing, 1996

Laia Mayol. Acquisition of irregular patterns in Spanish verbal morphology. In Ville Nurmi and Dmitry Sustretov, editors, Proceedings of the 12th ESSLLI Student Session, pages 1–11, Dublin, 2007

Constantine Lignos and Charles Yang. Morphology and language acquisition. Cambridge handbook of morphology, pages 765–791, 2018

Ewa Dąbrowska and Marcin Szczerbiński. Polish children’s productivity with case marking: the role of regularity, type frequency, and phonological diversity. Journal of child language, 33(3):559–597, 2006

Ewa Haman, Bartłomiej Etenkowski, Magdalena Łuniewska, Joanna Szwabe, Ewa Dąbrowska, Marta Szreder, and Marek Łaziński. The polish cds corpus. talkbank, 2011.

Minna Kirjavainen, Evan Kidd, and Elena Lieven. How do language-specific characteristics affect the acquisition of different relative clause types? Evidence from finnish. Journal of child language, 44(1):120–157, 2017

Reili Argus. Childes’i eesti andmepank ja selle suhtluskeskne analüüs (hendrik, 1.6-2.6). Tallinn: Tallinna Pedagoogikaülikool, 1998

Maigi Vija. Pronoomenid lapsekeeles: mõnda mina ja sina omandamisest. Eesti Rakenduslingvistika Ühingu aastaraamat, 3:373–384, 2007

# Participation Policy

We do not tolerate harassment in our shared task. Anyone who has been previously found to have harassed one of the organizers cannot participate in our task in any capacity. There are too few organizers for us to accomodate the harasser in a manner that ensures the safety of their victims. (This policy was written on June 22nd and cannot be applied retroactively, but will be in place for all future iterations of the task.)

