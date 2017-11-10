# PCFG
Developed PCFG for a small subset of English.  
There will be just one part, writing grammar rules, with no option for programming.  
Focused on the part that writes CFG rules and ignore the probabilities of the rules, except for the Start symbol. 
 
The grammar rules will be written in two files-
one for a grammar called S1 (and whose start symbol is S1) and one to assign non-terminal symbols for the words in the vocabulary of this limited language, where these symbols can be thought of as POS tags, but are not required to be. 
There is a second grammar, S2, which we do not have to write and which will generate all word strings as a linear sequence with no structure if there is no rule in S1 that will apply.  This grammar is a convenience for the scoring function.  Essentially S2 is a backoff model. 
 
The rules will be written in simple text files, ending in the file extension “.gr”.  
The set of sentences to parse is given in a file called dev.sen.  There is a java program provided that tries to parse these sentences with the PCFG in S1.gr, S2.gr and Vocab.gr.  It scores the resulting parse trees with a perplexity measure, but in our assignment we are going to ignore these scores.  (The perplexity measure is lower if your grammar models the sentences well;  that is, it is not surprised/perplexed by the sentences.) 
 
Goal is to produce as many parse trees as possible that use your rules from S1, instead of the backoff rules from S2. 

#Run Configurations
 1. Navigate to the PCFG directory
 2. $  python S2generator.py > S2.gr 
 3. $  java -jar pcfg.jar parse -t dev.sen *.gr  
