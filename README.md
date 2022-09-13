<div align="center">
 
# Reconstructing variation in Indo-European word order: a treebank-based quantitative study

</div>

## Description

In this repository we report queries employed for the paper 'Reconstructing variation in Indo-European word order: a treebank-based quantitative study', in which we analyze four word order patterns based on data extracted from treebanks of (ancient) Indo-European languages.

All emplyed treebanks are available on Surface [Syntactic Universal Dependencies](https://surfacesyntacticud.github.io ) (SUD) and were processed using the [Grew package](ttps://grew.fr), except for the Vedic Treebank ([Vedic_DCS](https://github.com/OliverHellwig/sanskrit/tree/master/papers/2020lrec/treebank )), the Homeric Dependency Treebank ([Gr_Hom](https://github.com/francescomambrini/katholou/tree/main/ud_treebanks/agdt)), and treebanks of Attic tragedies collected in the Daphne Treebank Repository ([Gr_Daph](https://github.com/francescomambrini/Daphne)). These treebanks follow the [Universal Dependency](https://universaldependencies.org) (UD) scheme, but their latest versions have not yet been released either in the UD website or in SUD. For querying them, we employed [Udapi](https://udapi.github.io), a framework for processing data annotated according to the UD format.

## Queries

### 1. Adpositions
SUD Treebanks: 
Non-SUD Treebanks: 
```
cat Vedic_DCS/Gr_Hom/Gr_Daph.conllu | udapy util.See node='node.deprel == "case" and node.upos == "ADP" and node.parent.upos in (“NOUN”, “PROPN”)' 
```

### 2. Genitive Modifiers
SUD Treebanks:
Non-SUD Treebanks: 
```
cat Vedic_DCS/Gr_Hom/Gr_Daph.conllu | udapy util.See node='node.deprel == "nmod" and node.upos == "NOUN" and node.feats["Case"] == "Gen" and node.parent.upos in (“NOUN”, “PROPN”)' 
```

### 3. Adjectival Modifiers
SUD Treebanks: 

Non-SUD Treebanks: 
```
cat Vedic_DCS/Gr_Hom/Gr_Daph.conllu | udapy util.See node='node.deprel == "amod" and node.upos == "ADJ" and node.parent.upos in (“NOUN”, “PROPN”)' 
```

### 4. Direct Objects (of finite verbs only)
SUD Treebanks:
Non-SUD Treebanks: 
```
cat Vedic_DCS/Gr_Hom/Gr_Daph.conllu | udapy util.See node='node.deprel == "obj" and node.upos in (“NOUN”, “PROPN”) and node.parent.upos == "VERB" and node.parent.feats[“Pers”] not == ""' 
```

## Contacts

- Erica Biagetti erica.biagetti@unipv.it
- Guglielmo Inglese guglielmo.inglese@unito.it
- Chiara Zanchi chiara.zanchi01@unipv.it
- Silvia Luraghi silvia.luraghi@unipv.it

