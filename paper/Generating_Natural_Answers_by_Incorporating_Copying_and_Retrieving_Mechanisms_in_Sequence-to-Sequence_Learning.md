# Generating Natural Answers by Incorporating Copying and Retrieving Mechanisms in Sequence-to-Sequence Learning
## Information
- 2017 ACL
- Shizhu He, Cao Liu, Kang Liu, and Jun Zhao.

## Keywords
- NLG
- QA
- KBQA

## Contribution
- Propose a neural network based model, named as COREQA, by incorporating copying and retrieving mechanism in Seq2Seq learning.

## Summary
- Propose a Seq2Seq model called COREQA, which incorporates copying and retrieving mechanisms to generate natural answers within an encoder-decoder framework.
![Example of QA with copying and retrieving mechanisms](pic/Generating_Natural_Answers_by_Incorporating_Copying_and_Retrieving_Mechanisms_in_Sequence-to-Sequence_Learningn_fig1.PNG)
- COREQA:
	![Overall diagram of COREQA](pic/Generating_Natural_Answers_by_Incorporating_Copying_and_Retrieving_Mechanisms_in_Sequence-to-Sequence_Learningn_fig2.PNG)
	COREQA is an encoder decoder framework plugged with a KB engineer
	1. Knowledge (facts) Retrieval:
		- Utilizes the gold topic entities to retrieve the related facts from the corresponding KB.
	2. Encoder:
		1. Question Encoding:
			- Bi-RNN is used to transform the question sequence into a sequence of concatenated hidden states.
		2. Knowledge Base Encoding:
	3. Decoder:
		COREQA predicts SUs(Sematic Units) based on a mixed probabilistic model of three modes, namely the predict-mode, the copy-mode and the retrieve-mode.
		![Mixture Probabilistic Function of Decoder](pic/Generating_Natural_Answers_by_Incorporating_Copying_and_Retrieving_Mechanisms_in_Sequence-to-Sequence_Learningn_fig3.PNG)
		1. Predict-mode:
			Predicts words with the vocabulary.
		2. Copy-mode:
			Predicts words from the source questions.
		3. Retrieve-mode:
			Predicts words from matched KB.

- Results:
	- Automatic evaluation (AE) on synthetic test data:
		![AE on synthetic test data](pic/Generating_Natural_Answers_by_Incorporating_Copying_and_Retrieving_Mechanisms_in_Sequence-to-Sequence_Learningn_fig4.PNG)
	- AE on real world test data:
		![AE on real world test data](pic/Generating_Natural_Answers_by_Incorporating_Copying_and_Retrieving_Mechanisms_in_Sequence-to-Sequence_Learningn_fig5.PNG)
	- Manual evaluation (ME) sampled mixed test data:
		![ME on sampled mixed test data](pic/Generating_Natural_Answers_by_Incorporating_Copying_and_Retrieving_Mechanisms_in_Sequence-to-Sequence_Learningn_fig6.PNG)
	- Examples of the generated natural answers by COREQA:
		![Examples of the generated natural answers by COREQA](pic/Generating_Natural_Answers_by_Incorporating_Copying_and_Retrieving_Mechanisms_in_Sequence-to-Sequence_Learningn_fig7.PNG)

## Source Code
not found