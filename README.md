<div align="center">
 
# Reconstructing variation in Indo-European word order: a treebank-based quantitative study

</div>

## Description

In this repository we report queries employed for the paper 'Reconstructing variation in Indo-European word order: a treebank-based quantitative study', in which we analyze four word order patterns based on data extracted from treebanks of (ancient) Indo-European languages. 
All emplyed treebanks are available on Surface Syntactic Universal Dependencies (SUD) and were processed using the Grew package, except for the Vedic Treebank (Vedic_DCS), the Homeric Dependency Treebank (Gr_Hom), and treebanks of Attic tragedies collected in the Daphne Treebank Repository (Gr_Daph). These treebanks follow the Universal Dependency (UD) scheme, but their latest versions have not yet been released either in the UD website or in SUD. For querying them, we employed Udapi, a framework for processing data annotated according to the UD format.

## Links

SUD: https://surfacesyntacticud.github.io
Grew: https://grew.fr
Vedic_DCS: https://github.com/OliverHellwig/sanskrit/tree/master/papers/2020lrec/treebank
Gr_Hom: https://github.com/francescomambrini/katholou/tree/main/ud_treebanks/agdt
Gr_Daph: https://github.com/francescomambrini/Daphne
UD: https://universaldependencies.org
Udapi: https://udapi.github.io

## Queries

1. Adpositions
SUD Treebanks: 
Non-SUD Treebanks: cat Vedic_DCS/Gr_Hom/Gr_Daph.conllu | udapy util.See node='node.deprel == "case" and node.upos == "ADP" and node.parent.upos in (“NOUN”, “PROPN”)'

2. Genitive Modifiers
SUD Treebanks: 
Non-SUD Treebanks: cat Vedic_DCS/Gr_Hom/Gr_Daph.conllu | udapy util.See node='node.deprel == "nmod" and node.upos == "NOUN" and node.feats["Case"] == "Gen" and node.parent.upos in (“NOUN”, “PROPN”)'

3. Adjectival Modifiers
SUD Treebanks: 
Non-SUD Treebanks: cat Vedic_DCS/Gr_Hom/Gr_Daph.conllu | udapy util.See node='node.deprel == "amod" and node.upos == "ADJ" and node.parent.upos in (“NOUN”, “PROPN”)'

4. Direct Objects (of finite verbs only)
SUD Treebanks: 
Non-SUD Treebanks: cat Vedic_DCS/Gr_Hom/Gr_Daph.conllu | udapy util.See node='node.deprel == "obj" and node.upos in (“NOUN”, “PROPN”) and node.parent.upos == "VERB" and node.parent.feats[“Pers”] not == ""'

## Contacts

- Erica Biagetti erica.biagetti@unipv.it
- Guglielmo Inglese guglielmo.inglese@unito.it
- Chiara Zanchi chiara.zanchi01@unipv.it
- Silvia Luraghi silvia.luraghi@unipv.it

