# Multilingual Knowledge Graph Embeddings for Cross-lingual Knowledge Alignment
## Information
- 2017 IJCAI
- Chen, Muhao, et al.

## Keywords
- Knowledge Graph
- Knowledge Alignment

## Contribution
- By encoding entities and relations of each language in a separated embedding space, MTransE provides transitions for each embedding vector to its cross-lingual counterparts in other spaces, while preserving the functionalities of monolingual embeddings.

## Summary
- Propose MTransE, a translation-based model for multilingual knowledge graph embeddings.
- MTransE learns the multilingual knowledge graph structure using a combination of two component models, namely knowledge model and alignment model.
	1. Knowledge Model:
		- Encodes entities and relations in a language-specific version of knowledge graph.
		- Adopts TransE as the knowledge model.
		- ![TransE Loss Function](pic/Multilingual_Knowledge_Graph_Embeddings_for_Cross-lingual_Knowledge_Alignment_fig1.PNG)
	2. Alignment Model:
		- Learn cross-lingual transitions for both entities and relations across different embedding spaces, where the following three representations of cross-lingual alignment are considered: 
		- ![Alignment Loss Function](pic/Multilingual_Knowledge_Graph_Embeddings_for_Cross-lingual_Knowledge_Alignment_fig2.PNG)
		1. Distance-based axis calibration
			- ![Distance-based Axis Calibration Loss Function1](pic/Multilingual_Knowledge_Graph_Embeddings_for_Cross-lingual_Knowledge_Alignment_fig3.PNG)
			- ![Distance-based Axis Calibration Loss Function2](pic/Multilingual_Knowledge_Graph_Embeddings_for_Cross-lingual_Knowledge_Alignment_fig4.PNG)
			- Assume analogous spatial emergence of items in each language.
		2. Translation vectors
			- ![Translation vectors Loss Function](pic/Multilingual_Knowledge_Graph_Embeddings_for_Cross-lingual_Knowledge_Alignment_fig5.PNG)
			- Consolidate alignment into graph structures and characterize cross-lingual transitions as regular relational translations.
			- v deployed as the entity-dedicated and relation-dedicated translation vectors.
		3. Linear transformations
			- ![Linear transformations Loss Function1](pic/Multilingual_Knowledge_Graph_Embeddings_for_Cross-lingual_Knowledge_Alignment_fig6.PNG)
			- ![Linear transformations Loss Function2](pic/Multilingual_Knowledge_Graph_Embeddings_for_Cross-lingual_Knowledge_Alignment_fig7.PNG)
			- Learn a k x k square matrix as a linear transformation on entity vectors from L<sub>i</sub> to L<sub>j</sub>.

- Results:
	![Results](pic/Multilingual_Knowledge_Graph_Embeddings_for_Cross-lingual_Knowledge_Alignment_fig8.PNG)

## Source Code
- [MTransE](https://github.com/muhaochen/MTransE)