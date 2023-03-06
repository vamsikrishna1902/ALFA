## ALFA: Active Learning for Graph Neural Network-Based Semantic Schema Alignment

The techniques implemented in ALFA are being patented. BANK-KAFS dataset contains sensitive data and is proprietary. Hence both the source code for ALFA and the BANK-KAFS dataset cannot be made available at this time.

However, in order to help with reproducibility of our proposed solution, we are making the pre-processed input files, input embeddings and the output logs corresponding to three other datasets used in our paper, CMT-CONF, HUMAN-MOUSE anatomy and FMA-NCI available. The original ontologies for the schema pairs in CMT-CONF and HUMAN-MOUSE are available as .owl files at http://oaei.ontologymatching.org/2021/conference/ and http://oaei.ontologymatching.org/2021/anatomy/ respectively. The FMA-NCI ontologies were borrowed from https://github.com/KRR-Oxford/BERTMap.

Following is a description of the items available on our GitHub Repository.

1. /datasets/cmt-conf, /datasets/human-mouse and /datasets/fma-nci
  - *Ontology_Node_Id_Label_Mappings* - This file contains the Node IDs and labels for all the schema concepts which include numerical (measures) and categorical (dimensions) attributes as well as the data properties within the unified ontology graph that combines both the input ontologies into a single graph. All the concepts and data properties in the unified ontology graph are further annotated by the values 1 and 2 respectively to distinguish between them.
  - *Ontology_Edge_List* - This file contains all the edges between the nodes that correspond to the object properties in the unified ontology graph. 
  - *Ontology_Node_Embeddings* - This file contains the Universal Sentence Encodings (USE) for all the nodes in the unified ontology graph. The ontology graph annotated with the USE embeddings for its nodes is fed as input to the GNN, along with the training data consisting of a progressively increasing subset of oracle-labeled node pairs in each active learning iteration.
  - *pos_neg_pairs* - This file contains the ground truth labels for the node pairs in the unified ontology graph. All the matching node pairs referring to the same ontology concept are labeled 1 and the non-matching pairs are labeled 0. We used negative sampling to shortlist challenging mis-matching pairs that are hard-to-classify, in an offline step.
  - *seed_pairs* - These are the seed pairs used to train the initial GNN model prior to active learning. 
  - *remaining_pairs* - These are the remaining pairs treated as the unlabeled set for the purpose of active learning. 

2. /logs/cmt-conf, /logs/human-mouse and /logs/fma-nci
  - The log filenames are self-explanatory and contain the active learning progressive F1-scores and latencies in each iteration for all the approaches compared in the paper.
