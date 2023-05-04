Here is the key to the column headers in the dataset. 

* Morphology_R - morphological parse, romanization. Consists of more or less the URs for each morpheme
* Morphology_H - morphological parse, Hangul.
* Production_R - production, romanization. Represents the option chosen by the participant, in phonemic detail (ie, representing the actual assumed segmental targets, the "SR", with phonological processes applied)
* Production_H - production, Hangul.
* UR - segmental sequence surrounding the morpheme juncture (noted "-")
* SR - segmental sequence of how the UR was produced in the Production
* simplify_delete_obstruent - did the speaker delete an obstruent in the UR? (1 = yes, 0 = no, NA = not applicable)
* simplify_delete_lateral - did the speaker delete a lateral in the UR? 
* nasalize - did the speaker nasalize the coda of the stem? Nasal assimilation is regressive across the morpheme boundary from the suffix, targeting an obstruent. 
* lateralize - did the speaker lateralize the onset of the affix? In l-final stems, lateralization is progressive across the morpheme boundary. This is rare in this dataset, but can arise if the speaker simplifies an lC cluster by deleting the obstruent, which may then feed lateralization of a following C.
* tensify	- did the speaker tensify the onset of the affix?
* Type - type of juncture.

[Here](https://github.com/sigmorphon/2023InflectionST/blob/main/part2/Korean_data_slides.pdf) is a slide deck describing the data, modeled on a talk from the 2023 LSA Annual Meeting.

A note on the file names:

* the Ko file contains the extracts from the infant-directed speech corpus
* the NILK files contain the extracts from the adult-directed speech corpus
* the dictionary used for the Dictionary file is:  Kang, B.-M., & Kim, H.-G. (2004). Hankwuke hyengtayso mich ehwi sayong pintouy pwunsek2 [Frequency analysis of Korean morpheme and word usage2]. Seoul: Institute of Korean Culture, Korea University

A note on LanguageBackgroundInfo.csv columns:

* The first column indexes the subject ID in the experiment (the column name is the same in the experimental data files)
* The second column is the age at which they started speaking Korean in some context (home, school, with certain relatives, etc.)
* The third column is a 7-point Likert-scaled question asking about which language they prefer to use on a daily basis, with 7 indicating a strong preference for Korean, and 1 indicating a strong preference for another language. This was meant to get at how Korean-dominant they are. 

Please feel free to reach out if you have any questions, clarifications, or if you spot any errors - I'd love to hear from you! --> canaanbreiss1@gmail.com

**Update! Test data released!**
* file test_with_right_answers.csv includes the missing columns in the previous test_no_answers.csv file
* file new_data_with_right_answers.csv includes data from six brand-new subjects! 
* the LanguageBackgroundInfo.csv file has been updated with the info for the six new subjects.
