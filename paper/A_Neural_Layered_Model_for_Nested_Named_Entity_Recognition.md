# A Neural Layered Model for Nested Named Entity Recognition
## Information
- 2018 NAACL
- Ju, Meizhi, Makoto Miwa, and Sophia Ananiado

## Keywords
- NER
- Nested NER

## Contribution
- Use the dynamically stacked flat NER model to handle the nested NER problem.

## Summary
- Propose a novel neural model to identify nested entities by dynamically stacking flat NER layers(LSTM+CRF). 
- The model dynamically stacks the flat NER layers until no outer entities are extracted.
	![Architecture of MT-DNN model](pic/A_Neural_Layered_Model_for_Nested_Named_Entity_Recognition_fig1.PNG)
- Neural Layered Model:
	1. Embedding layer:
		Represent each word by concatenating character sequence embeddings and word embeddings for the first flat NER layer.
		![Architecture of Embedding layer](pic/A_Neural_Layered_Model_for_Nested_Named_Entity_Recognition_fig2.PNG)
	2. Flat NER layer:
		Consists of an LSTM layer and a CRF layer. The LSTM layer captures the bidirectional context representation of sequences and subsequently feeds it to the CRF layer to globally decode label sequences.
	3. Stacking flat NER layers:
		- Merge and average current context representation of the regions composed in the detected entities, as described in the following equation:
			![Merge context representation](pic/A_Neural_Layered_Model_for_Nested_Named_Entity_Recognition_fig3.PNG)
		- Dynamically stacks the flat NER layers until no outer entities are extracted.

- The Results:
	![The Results](pic/A_Neural_Layered_Model_for_Nested_Named_Entity_Recognition_fig4.PNG)

## Source Code
- [Nested-NER](https://github.com/meizhiju/layered-bilstm-crf)