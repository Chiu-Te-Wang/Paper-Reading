# Neural Segmental Hypergraphs for Overlapping Mention Recognition
## Information
- 2018 EMNLP
- Bailin Wang and Wei Lu

## Keywords
- NER
- Mention Recognition
- Overlapping Mention(Entity)

## Contribution
- Propose a novel segmental hypergraph representation that is capable of modeling arbitrary combinations of (potentially overlapping) mentions in a given sentence.

## Summary
- Propose a hypergraph representation to handle the overlapping mentions in sentences.

1. The Hypergraph Representation:
	![The Hypergraph Representation](pic/Neural_Segmental_Hypergraphs_for_Overlapping_Mention_Recognition_fig1.PNG)
	- Symbols:
		- A<sub>i</sub> : encodes all such mentions that start with the i-th or a later word
		- E<sub>i</sub> : encodes all mentions that start exactly with the i-th word
		- T<sub>i</sub><sup>k</sup> : represents all mentions of type k starting with the i-th word
		- I<sub>i,j</sub><sup>k</sup> : represents all mentions of type k that contain the j-th word and start with the i-th word
		- X : marks the end of a mention
2. Learn the Probability of Each Hyperpath:
	- Objective : Negative log likelihood of all instances in the training set D
		![Objective](pic/Neural_Segmental_Hypergraphs_for_Overlapping_Mention_Recognition_fig2.PNG)
	- Probability of Each Hyperpath:
		![Probability of Each Hyperpath](pic/Neural_Segmental_Hypergraphs_for_Overlapping_Mention_Recognition_fig3.PNG)
	- Score Function:
		![Score Function](pic/Neural_Segmental_Hypergraphs_for_Overlapping_Mention_Recognition_fig4.PNG)
		, where e is hyperedge and x is input sentence
		![Score](pic/Neural_Segmental_Hypergraphs_for_Overlapping_Mention_Recognition_fig5.PNG)
	- Feature Function:
		- Use two bidirectional LSTMs to learn word level and span level feature representations that can be used in feature function.
		- The representation for i-th word v<sub>i</sub> is the concatenation of pre-trained word embedding e<sub>i</sub> and POS tag to its embedding p<sub>i</sub>
		- Word level feature representations:
			![Word level feature representations](pic/Neural_Segmental_Hypergraphs_for_Overlapping_Mention_Recognition_fig7.PNG)
		- Span level feature representations:
			![Span level feature representations](pic/Neural_Segmental_Hypergraphs_for_Overlapping_Mention_Recognition_fig8.PNG)
		- Feature Function: use a linear layer to compute
			![Feature Function](pic/Neural_Segmental_Hypergraphs_for_Overlapping_Mention_Recognition_fig9.PNG)

- Results:
	![Results](pic/Neural_Segmental_Hypergraphs_for_Overlapping_Mention_Recognition_fig6.PNG)
 

## Source Code
- [Overlapping NER](https://github.com/berlino/overlapping-ner-em18)
