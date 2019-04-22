# Unsupervised Machine Translation Using Monolingual Corpora Only
## Information
- 2018 ICLR
- Lample, Guillaume, et al.

## Keywords
- Unsupervised Learning
- Machine Translation

## Contribution
- This paper propose a machine translation encoder-decoder structure trained without any parallel data, i.e. an unsupervised method.

## Summary
- Concepts:
	![Model Illustration](pic/Unsupervised_Machine_Translation_Using_Monolingual_Corpora_Only_fig1.PNG)
	- Propose a model that takes sentences from monolingual corpora in two different languages and maps them into the same latent space.
	- By learning to reconstruct in both languages from this shared feature space, the model effectively learns to translate without using any labeled data.

- Model Structure:
	![Model Structure](pic/Unsupervised_Machine_Translation_Using_Monolingual_Corpora_Only_fig2.PNG)
	1. Denoising Auto-encoding:
		![Objective Function of Denoising Auto-encoding](pic/Unsupervised_Machine_Translation_Using_Monolingual_Corpora_Only_fig3.PNG)
		- To prevent simple copy from input sequence with attentioned Seq2Seq model, adopt the same strategy of Denoising Auto-encoders.
		- The reconstruction of the corrupted version of x (x_hat) should be close to the origin x.
		- Noise model C(x):
			1. Drop every word in the input sentence with a probability p<sub>wd</sub>.
			2. Slightly shuffle the input sentence.
	2. Cross Domain Training:
		- This objective is to constrain the model to be able to map an input sentence from a the source/target domain to the target/source domain.
		![Objective Function of Cross Domain Training](pic/Unsupervised_Machine_Translation_Using_Monolingual_Corpora_Only_fig4.PNG)
		1. Apply the current translation model denoted M to x, y=M(x)
		2. Obtain the corrupted version C(y)
		3. Objective is thus to learn the encoder and the decoder such that they can reconstruct x from C(y)
	3. Adversarial Training:
		- Let the encoder to output features in the same space regardless of the actual language of the input sentence.
		1. Train a neural network as the discriminator to classify between the encoding of source sentences and that of target sentences.
			![Objective Function of the discriminator](pic/Unsupervised_Machine_Translation_Using_Monolingual_Corpora_Only_fig5.PNG)
		2. The encoder is trained instead to fool the discriminator.
			![Objective Function of the encoder](pic/Unsupervised_Machine_Translation_Using_Monolingual_Corpora_Only_fig6.PNG)
	- Final Objective function:
		 ![Final Objective function](pic/Unsupervised_Machine_Translation_Using_Monolingual_Corpora_Only_fig7.PNG)

- Unsupervised Model Selection Criterion
	- In order to select hyper-parameters, need a criterion correlated with the translation quality.
	![Unsupervised Model Selection Criterion](pic/Unsupervised_Machine_Translation_Using_Monolingual_Corpora_Only_fig8.PNG)
	- The quality of the model is evaluated by computing the BLEU score over the original inputs and their reconstructions via this two-step translation process
	- M is the translation model.

- Results:
	![Results](pic/Unsupervised_Machine_Translation_Using_Monolingual_Corpora_Only_fig9.PNG)

## Source Code
not found