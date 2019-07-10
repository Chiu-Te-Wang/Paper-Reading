# COMET: Commonsense Transformers for Automatic Knowledge Graph Construction
## Information
- 2019 ACL
- Bosselut, Antoine, et al.

## Keywords
- Knowledge Graph Construction
- Knowledge
- Transformer

## Contribution
- Develop a generative approach to knowledge base construction.
- Develop a framework for using large-scale transformer language models(GPT) to learn to produce commonsense knowledge tuples.

## Summary
- Propose **COM**mons**E**nse **T**ransformers(COMET) that learn to generate rich and diverse commonsense descriptions in natural language.
- COMET constructs commonsense KBs by using existing tuples as a seed set of knowledge on which to train. Using this seed set, a pre-trained language model learns to adapt its learned representations to knowledge generation, and produces novel tuples that are high quality.

- Model Structure with Transformer
	- ![Model Structure with Transformer](pic/COMET_-_Commonsense_Transformers_for_Automatic_Knowledge_Graph_Construction_fig1.PNG)
	- Transformer Block
	- Multi-headed Attention
	- Input Encoder:
		- As the input of the model, present a knowledge tuple {s, r, o} as a concatenated sequence of the words of each item of the tuple: **X** = {X<sup>s</sup>, X<sup>r</sup>, X<sup>o</sup>}
		- For any input word x<sub>t</sub> in **X**, the encoding h<sub>t</sub><sup>0</sup> of the input is the sum of its word embedding e<sub>t</sub>, with a position embedding p<sub>t</sub> encoding its absolute position in the sequence X: h<sub>t</sub><sup>0</sup> = e<sub>t</sub> + p<sub>t</sub>

- Traing Task:
	- Task Definition:
		- COMET is trained to learn to produce the phrase object o of a knowledge tuple given the tuple's phrase subject s and relation r.
		- More specifically, given the concatenation of the tokens of s and r : [X<sup>s</sup>, X<sup>r</sup>] as input, the model must learn to generate the tokens of o: X<sup>o</sup>.
	- Input token setup for training configurations:
		- ![Input token setup for training configurations](pic/COMET_-_Commonsense_Transformers_for_Automatic_Knowledge_Graph_Construction_fig2.PNG)
	- Loss Function:
		- COMET is trained to maximize the conditional log-likelihood of predicting the phrase object tokens, X<sup>o</sup>:
			- ![Loss Function of COMET Model](pic/COMET_-_Commonsense_Transformers_for_Automatic_Knowledge_Graph_Construction_fig3.PNG)

- Experiments:
	- ATOMIC Experiment Results:
		- Automatic evaluations
			- ![Automatic evaluations of COMET on ATOMIC](pic/COMET_-_Commonsense_Transformers_for_Automatic_Knowledge_Graph_Construction_fig4.PNG)
		- Human score
			- ![Human score of COMET on ATOMIC](pic/COMET_-_Commonsense_Transformers_for_Automatic_Knowledge_Graph_Construction_fig5.PNG)
	- ConceptNet Experiment Results:
		- ![ConceptNet Experiment Results](pic/COMET_-_Commonsense_Transformers_for_Automatic_Knowledge_Graph_Construction_fig6.PNG)

## Source Code
- [comet-commonsense](https://github.com/atcbosselut/comet-commonsense)

## Demo Link
- [COMeT](https://mosaickg.apps.allenai.org/)
