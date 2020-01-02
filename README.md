# DSS2ETCBC
Contains scripts related to conversion of the DSS to ETCBC encoding as part of the CACCHT project. It is work in progress!

The main dependency is the package text-fabric, which can be installed with 

`pip install text-fabric`

For some of the scripts tensorflow is a dependency. These scripts can be run on a GPU, which speeds up the training process considerably. 

Text-fabric is a framework for storing and processing text data. There is a variety of textual corpora available in text-fabric already. The scripts in this repository you can find three of them: 'bhsa' (the Hebrew Bible, prepared by the ETCBC), 'extrabiblical' (contains a number of Hebrew inscriptions,  Dead Sea Scrolls, and Rabbinic texts, prepared by the ETCBC) and 'dss' (all the Dead Sea Scrolls, prepared by Martin Abegg).

The dss package contains a variety of character and word level features, but we want to harmonize the package with the BHSA.

The features that we start with are:

#### Word level
- gender 
- number
- person
- state
- lexeme
- part of speech
- verbal stem
- verbal tense
- language

#### Phrase level
- phrase boundaries
- phrase types
- phrase function

#### Clause level
- clause boundaries

These features will be added to the dss dataset as extra features.
The conversion of these features is a long term process. We want to convert all the features automatically with a minimum accuracy of 90%. Depending on the feature and the text, we may even achieve an initial accuracy of 99%. That is not bad, but it also shows that additional (manual) corrections are necessary.


## How do we do this?
Good question. In the conversion of features we distinguish between biblical (defined as books included in the bhsa dataset) and non-biblical texts. This distinction is made, because the encoding in the BHSA can help the conversion of the biblical DSS in a direct way. 
There are roughly two approaches for encoding the DSS in the ETCBC way: For the biblical text sequence alignment is used, and for the other texts we use machine learning, sequence 2 sequence (seq2seq) models in particular. Of course, this is only the first step. It is very well possible that the encoding will take place in a number of steps.

## What is the order for the conversion of the DSS to ETCBC conventions?

A new app will be made, because the differences in conventions if word boundaries between the dss and etcbc may lead to confusion. The name of the app will be DSSA, analogous to BHSA.
First we will convert the biblical scrolls, there is support from the BHSA for those texts.


1. Convert feature language, important to know what the language of a word is.
2. What are the words: some cases differ from etcbc conventions: in Aramaic ‘>’ at the end of a word (emphatic state) is a distinct word, various place names consisting of two words have a distinct lexeme in the BHSA, and are one word in the dss data.
3. Convert ETCBC lexemes.
4. Convert POS.
5. Convert verbal stem and verbal tense.
6. Convert gender, number, person
7. Add clause boundaries
8. Add phrase boundaries
9. Phrase type and function






 
