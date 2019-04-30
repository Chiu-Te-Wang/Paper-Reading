# SGM: Sequence Generation Model for Multi-label Classification
## Information
- 2018 COLING
- Yang, Pengcheng, et al.

## Keywords
- Multi-label Classification
- Text Classification


## Contribution
- Propose to view the Multi-label Classification(MLC) task as a sequence generation problem to take the correlations between labels into account.
- Propose a sequence generation model with a novel decoder structure, which not only captures the correlations between labels, but also selects the most informative words automatically when predicting different labels.

## Summary
- Propose to view the multi-label classification task as a sequence generation problem, and apply a sequence generation model with a novel decoder structure to solve it.
- The decoder uses an LSTM to generate labels sequentially, and predicts the next label based on its previously predicted labels. Therefore, the proposed model can consider the correlations between labels by processing label sequence dependencies through the LSTM structure.
- Novel decoder structure with global embedding is proposed to further improve the performance of the model by incorporating overall informative signals.

- Model Overview
	![Model Overview](pic/SGM_-_Sequence_Generation_Model_for_Multi-label_Classification_fig1.PNG)
	1. Encoder:
		1. Embed w<sub>i</sub> to a dense embedding vector x<sub>i</sub>
		2. Use a bidirectional LSTM to obtain the final hidden representation h<sub>i</sub>
	2. Attention:
		- When the model predicts different labels, not all text words make the same contribution.
		- The final context vector c<sub>t</sub>:
			![Attention Mechanism](pic/SGM_-_Sequence_Generation_Model_for_Multi-label_Classification_fig2.PNG)
			![Context Vector](pic/SGM_-_Sequence_Generation_Model_for_Multi-label_Classification_fig3.PNG)
	3. Decoder:
		- The hidden state s<sub>t</sub> of the decoder at time-step t is computed as follows:
			![Hidden State](pic/SGM_-_Sequence_Generation_Model_for_Multi-label_Classification_fig4.PNG)
		- y<sub>t</sub> is the probability distribution over the label space at time-step t:
			![Label Distribution](pic/SGM_-_Sequence_Generation_Model_for_Multi-label_Classification_fig5.PNG)
		- I<sub>t</sub> is the mask vector that is used to prevent the decoder from predicting repeated labels.
			![Mask Vector](pic/SGM_-_Sequence_Generation_Model_for_Multi-label_Classification_fig6.PNG)
		- Employ the beam search algorithm to find the top-ranked prediction path at inference time.
		- The prediction paths ending with the eos are added to the candidate path set.

- Global Embedding
	- Let e denotes the embedding of the label which has the highest probability under the distribution y<sub>t-1</sub>
	- e is the weighted average embedding at time t, which is calculated as follows:
		![Weighted Average Embedding](pic/SGM_-_Sequence_Generation_Model_for_Multi-label_Classification_fig7.PNG)
	- Global embedding g(y<sub>t-1</sub>):
		![Global Embedding](pic/SGM_-_Sequence_Generation_Model_for_Multi-label_Classification_fig8.PNG)
	- H is the transform gate controlling the proportion of the weighted average embedding:
		![Global Embedding](pic/SGM_-_Sequence_Generation_Model_for_Multi-label_Classification_fig9.PNG)
		, where W<sub>1</sub>, W<sub>2</sub> are weight matrices.
	- By considering the probability of every label, the model is capable of reducing damage caused by mispredictions made in the previous time steps.

- Results:
	![Results](pic/SGM_-_Sequence_Generation_Model_for_Multi-label_Classification_fig10.PNG)

## Source Code
- [SGM](https://github.com/lancopku/SGM)