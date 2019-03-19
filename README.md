# Phrase Detectives Corpus 2.1.4

Jon Chamberlain, Silviu Paun, Juntao Yu, Udo Kruschwitz and Massimo Poesio
Release date: January 2019

This is a corpus of anaphorically annotated documents, consisting of
all the  documents completely annotated as of 12th October 2018 using
the  Phrase Detectives game-with-a-purpose: 

	   https://www.phrasedetectives.org

# Download

The corpus is avaliable at this [link](https://drive.google.com/file/d/1WJP5DAoe5n5Azu6qPTPG4ZWC2VzyAzP5/view?usp=sharing).

# The Documents

A total of 542 documents are included, for a total of 408K tokens and
108K markables. The documents are divided in:

* a 'gold' subset of 45 documents (23K tokens, 6K markables) annotated
  both by Phrase Detectives players and by two experts. This subset is
  a cleaned-up version of the Phrase Detectives 1.0 corpus released in
  2016. In addition to the gold annotation, a 'silver' annotation is
  included, extracted using the Mention Pair Annotation (MPA) probabilistic
  aggregation method for coreference discussed in the paper:

  Silviu Paun, Jon Chamberlain, Udo Kruschwitz, Juntao Yu and Massimo
  Poesio, 2018. [A Probabilistic Annotation Model for Crowdsourcing
  Coreference](https://aclanthology.coli.uni-saarland.de/papers/D18-1218/d18-1218). In Proc. of EMNLP. 
  

* a 'silver' subset of 497 documents (384 tokens, 101K markables) for
  which only the silver MPA annotation is provided.

The silver subset consists of documents  from two separate genres:

* Wikipedia pages (350 documents, 218K tokens, 57678 markables)
* fiction from the Project Gutenberg collection (145 documents, 158739
                   tokens, 41898 markables)

The gold subset consists of documents from three genres:

* Wikipedia pages (35 docs, 15287 tokens, 3957 markables)
* fiction from the Project Gutenberg collection (5 documents, 7536
                   tokens, 1947 markables)
* art history texts from the GNOME corpus (5 documents, 989 tokens,
                   274 markables)		   

A document is considered `complete' is all its markables have at least
8 annotations, and each interpretation has been validated by at least
4 players. On average, 20.6 annotations per markable are present.

# Markup formats

The documents are provided in three different formats: MAS-XML, CONLL,
and CRAC.

MAS-XML

This is the format used for the original release of the corpus. It is
an inline XML format, in which each markable is identified with an
\<ne\> element, and anaphoric annotation is stored using \<PDante\>
elements containing in turn \<anchor\> elements specifiying annotations
and validations (all annotations and validations are provided) and
\<comment\> elements with additional information provided by the
players. Details for \<PDante\> and \<anchor\> are as follows: 

\<PDante\>  
id = id of the markable  
visibility = whether the administrator marked this to be "hidden"  
start_chr = the markable span was edited and the new start character is this  
end_chr = the markable span was edited and the new end character is this  

\<anchor\>  
timestamp = time the annotation was created  
interface = interface the annotation was created on (0 = standalone PD, 1 = Facebook PD)  
mode = mode of annotation (a = annotation, v = validation, e = expert)  
agree = was this annotation in agreement with the interpretation  
annotation_time = time to create the annotation response from page load  
user_rating = rating of the user  
user_id = encrypted user_id  
type = interpretation type (DN = Discourse New, DO = Discourse Old, NR = Non-referring, PR = Property, SE = same entitiy)  
ante = antecedent markable id  
favoured = the expert indicates whether this is the best interpretation (y) or another might be better  

\<comment\>  
type/type_id = the type of error detected:  

1. not_selectable
2. out_of_context_window
3. parse_error
4. discourse_diexis
5. ambiguous
6. non_referring
7. nearest_mention_embedding
8. bridge
9. quantifier

CONLL

This is the format used in the CONLL 2011 and 2012 Shared Tasks on
Coreference. Unlike the MAS-XML format, where all interpretations
produced by players are included, only one interpretation is provided
for each markable in a doc in this format. For the docs in the silver
subset, this is the silver interpretation. For the docs in the gold
subset, both the gold and the silver interpretations are included, in
separate versions of each document.

CRAC

This is the format used in the CRAC 2018 Shared Task on Anaphora
Resolution with the ARRAU corpus. As in the case of the CONLL format,
only one interpretation is provided for each markable. 

# Annotation scheme

Markables are annotated according to a scheme including the following
labels:

* NR: non-referring. Used for expletives, as in '[It] rains'.
* PR: used for predicatives NPs, as in 'John is [a policeman]'
* DN: Used for discourse-new mentions.
* DO: Used for discourse-old mentions.

Split-antecedent plurals are marked.

# Folder structure

The gold and silver subsets are contained in subfolders called 'gold'
and 'silver', respectively. 

# Document Guide

Source files are included in this corpus release including files appended:

No appending or -no_headder = The original file  
.filtered = Coverted to an input format  
-masxml_xsd = Original MASXML file  
-masxml = File converted to MASXML format for the game  
-sgf = File converted to SGF format to imported into the game  

Export files are appended -game.


# Papers

Full documentation and preliminary analysis of the data has been
published in a submitted paper. Earlier papers on the corpus include:

Chamberlain, J., and Poesio, M., and Kruschwitz, U. (2016). Phrase
Detectives Corpus 1.0: Crowdsourced Anaphoric Coreference.  In
Proceedings of the 2016 Language Resources and Evaluation Conference
(LREC'16). 

Poesio, M., Chamberlain, J., Kruschwitz, U., Robaldo, L., and
Ducceschi, L. (2013). Phrase Detectives: Utilizing collective
intelligence for internet-scale language resource creation.  ACM
Transactions on Interactive Intelligent Systems. 

# Contact

Please report any errors or issues to jchamb@essex.ac.uk

# Change Log

January 2019: Version 2.1 created.


