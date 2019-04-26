# Competence-based Curriculum Learning for Neural Machine Translation
## Information
- 2019 NAACL
- Platanios, Emmanouil Antonios, et al.

## Keywords
- Machine Translation
- Curriculum Learning

## Contribution
- Propose a curriculum learning framework for NMT that reduces training time, reduce the need for specialized heuristics or large batch sizes, and results in overall better performance.

## Summary
- Propose competence-based curriculum learning, a training framework based on the idea that training algorithms can perform better if training data is presented in a way that picks examples appropriate for the model's current competence.
	![Framework Overview](pic/Competence-based_Curriculum_Learning_for_Neural_Machine_Translation_fig1.PNG)

- Central Concepts of the Framework:
	![Example](pic/Competence-based_Curriculum_Learning_for_Neural_Machine_Translation_fig2.PNG)
	![Example illustration of the training data "filtering"](pic/Competence-based_Curriculum_Learning_for_Neural_Machine_Translation_fig3.PNG)
	- The training examples are ranked according to their difficulty and the learner is only allowed to use the top c(t) portion of them at time t.
	1. Difficulty:
		- A value that represents the difficult of a training sample and that may depend on the current state of the learner.
		1. Sentence Length:
			Longer sentences are intuitively harder to translate due to the propagation of errors made early on when generating the target language sentence.
		2. Word Rarity: 
			Another aspect of language that can affect the difficulty of translation is the frequency with which words appear.
	2. Competence:
		- A value between 0 and 1 that represents the progress of a learner during its training.
		- Define the competence, c(t) at time t (measured in terms of training steps), of a learner as the proportion of training data it is allowed to use at that time.
		1. Linear:
			- ![Linear Competence](pic/Competence-based_Curriculum_Learning_for_Neural_Machine_Translation_fig5.PNG)
			,where T denotes the time after which the learner is fully competent.
		2. Root:
			- ![Root Competence](pic/Competence-based_Curriculum_Learning_for_Neural_Machine_Translation_fig6.PNG)

- Competence-based curriculum learning algorithm:
	![Competence-based curriculum learning algorithm](pic/Competence-based_Curriculum_Learning_for_Neural_Machine_Translation_fig4.PNG)

- Results:
	![Results](pic/Competence-based_Curriculum_Learning_for_Neural_Machine_Translation_fig7.PNG)

## Source Code
- not found