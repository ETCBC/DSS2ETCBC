# DSS2ETCBC
Contains scripts related to conversion of the DSS to ETCBC encoding. It is work in progress!

The main dependency is the package text-fabric, which can be installed with 

`pip install text-fabric`

Text-fabric is a framework for storing and processing text data. There is a variety of textual corpora available in text-fabric already. The scripts in this repository you can find three of them: 'bhsa' (the Hebrew Bible, prepared by the ETCBC), 'extrabiblical' (contains a number of Hebrew inscriptions,  Dead Sea Scrolls, and Rabbinic texts, prepared by the ETCBC) and 'dss' (all the Dead Sea Scrolls, prepared by Martin Abegg).

The dss package contains a variety of character and word level features, but we want to harmonize the package with the BHSA.

The features that we start with are:

#### Word level
- gender 
- number
- person
- lexeme
- part of speech

#### Phrase level
- phrase boundaries
- phrase types
- phrase function

#### Clause level
- clause boundaries

The conversion of these features is a long term process. We want to convert all the features automatically with a minimum accuracy of 90%. Depending on the feature and the text, we may even achieve an initial accuracy of 99%. That is not bad, but it also shows that additional (manual) corrections are necessary.

## How do we do this?
Good question. In the conversion of features we distinguish between biblical (defined as books included in the bhsa dataset) and non-biblical texts

## What has been done so far?




 
