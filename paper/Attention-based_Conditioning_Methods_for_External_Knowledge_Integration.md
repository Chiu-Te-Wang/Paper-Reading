# Attention-based Conditioning Methods for External Knowledge Integration
## Information
- 2019 ACL
- Margatina, Katerina, Christos Baziotis, and Alexandros Potamianos.

## Keywords
- NLU
- Attention

## Contribution
- Propose an alternative way for incorporating external lexicon features into the self-attention mechanism of RNN-based architectures.

## Summary
- Propose a novel way of utilizing word-level prior information encoded in linguistic, sentiment, and emotion lexicons, to improve classification performance.
- Enable the self-attention mechanism of RNN-based architectures to identify the most informative words, by directly conditioning on their additional lexicon features.

- Proposed Model:
	- Network Architecture
		- Word Embedding Layer:
			- Initialize the weights of the embedding layer with pretrained word embeddings.
		- LSTM Layer:
			- Takes as input the words of a sentence and produces the word annotations h<sub>1</sub>, h<sub>2</sub>, ..., h<sub>T</sub>
		- Self-Attention Layer:
			- The attention mechanism assigns a score a<sub>i</sub> to each word annotation h<sub>i</sub> .
			- Compute the fixed representation r of the input sequence, as the weighted sum of all the word annotations.
			- ![Self-Attention](pic/Attention-based_Conditioning_Methods_for_External_Knowledge_Integration_fig1.PNG)
	- External Knowledge(Lexicon Features)
		- Leverage lexica containing psycho-linguistic, sentiment and emotion annotations.
		- Construct a feature vector c(w<sub>i</sub>) for every word in the vocabulary by concatenating the word's annotations.
	- Conditional Attention Mechanism
		- Use as input to the self-attention layer both the word annotation h<sub>i</sub>, as well as the lexicon feature c(w<sub>i</sub>) of each word.
		- Replace f(h<sub>i</sub>) in Self-Attention Layer with f(h<sub>i</sub>, c(w<sub>i</sub>))
		1. Attentional Concatenation (conc.)
			- ![Attentional Concatenation](pic/Attention-based_Conditioning_Methods_for_External_Knowledge_Integration_fig2.PNG)
			- ![Attentional Concatenation Equation](pic/Attention-based_Conditioning_Methods_for_External_Knowledge_Integration_fig5.PNG)
		2. Attentional Feature-based Gating (gate)
			- ![Attentional Feature-based Gating](pic/Attention-based_Conditioning_Methods_for_External_Knowledge_Integration_fig3.PNG)
			- A gate mechanism with a sigmoid activation function, generates a mask-vector from each c(w<sub>i</sub>) with values between 0 and 1.
			- ![Attentional Feature-based Gating Equation](pic/Attention-based_Conditioning_Methods_for_External_Knowledge_Integration_fig6.PNG)
		3. Attentional Affine Transformation (affine)
			- ![Attentional Affine Transformation](pic/Attention-based_Conditioning_Methods_for_External_Knowledge_Integration_fig4.PNG)
			- Adopted from the work of [Perez et al. (2017)](https://arxiv.org/abs/1709.07871) and applies a feature-wise affine transformation to the latent space of the hidden states.
			- ![Attentional Affine Transformation Equation](pic/Attention-based_Conditioning_Methods_for_External_Knowledge_Integration_fig7.PNG)

- Results:
	- Datasets:
		- ![Datasets](pic/Attention-based_Conditioning_Methods_for_External_Knowledge_Integration_fig8.PNG)
	- Results:
		- Baselines:
			- baseline:
				- An LSTM-based architecture augmented with a selfattention mechanism with no external knowledge.
			- emb. conc.
				- Incorporates lexicon information by concatenating the c(w<sub>i</sub>) vector to the word representations in the embedding layer.
		- ![Results](pic/Attention-based_Conditioning_Methods_for_External_Knowledge_Integration_fig9.PNG)

## Source Code
- [affective-attention](https://github.com/mourga/affective-attention)