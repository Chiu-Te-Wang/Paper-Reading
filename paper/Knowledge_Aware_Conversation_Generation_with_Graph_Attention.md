# Commonsense Knowledge Aware Conversation Generation with Graph Attention
## Information
- 2018 IJCAI
- Zhou, Hao, et al.

## Keywords
- Knowledge
- Conversation Model
- NLG

## Contribution
- This work is the first attempt that uses large-scale commonsense knowledge in neural conversation generation.
- Instead of treating knowledge triples (or entities) separately and independently, we devise static and dynamic graph attention mechanisms to treat the knowledge triples as a graph, from which we can better interpret the semantics of an entity from its neighboring entities and relations.

## Summary
This paper presents a novel open-domain conversation generation model(Commonsense Conversational Model(CCM)) to demonstrate how large-scale commonsense knowledge can facilitate language understanding and generation.
![Model Structure of Commonsense Conversational Model(CCM)](pic/Knowledge_Aware_Conversation_Generation_with_Graph_Attention_fig1.PNG)
1. Knowledge Interpreter:
	![Model Structure of Knowledge Interpreter](pic/Knowledge_Aware_Conversation_Generation_with_Graph_Attention_fig2.PNG)
	1. Get the embedding of head , relation, and tail in the knowledge by TransE model.
	2. Use the words in input sequence to retrive the graphs that contain the word.
	3. Get the Graph embedding g<sub>i</sub> by the **Static Graph Attention Mechanism**(use relation to attend head and tail)
		![Static Graph Attention Mechanism](pic/Knowledge_Aware_Conversation_Generation_with_Graph_Attention_fig3.PNG)
	4. Concatenate graph embedding g<sub>i</sub> and word embedding as the input of the Encoder

2. Knowledge Aware Generator:
	Apply Dynamic Graph Attention Mechanism to get the word for generation.
	![Dynamic Graph Attention Mechanism](pic/Knowledge_Aware_Conversation_Generation_with_Graph_Attention_fig4.PNG)
	1. Attend on the graphs that retrive from step1-1
		![Dynamic Graph Attention that Attend on graphs](pic/Knowledge_Aware_Conversation_Generation_with_Graph_Attention_fig5.PNG)
	2. Attend on the knowledge triples k<sub>j</sub> that in the graph of step2-1
		![Dynamic Graph Attention that Attend on triples](pic/Knowledge_Aware_Conversation_Generation_with_Graph_Attention_fig6.PNG)

![Results of automatic evaluation](pic/Knowledge_Aware_Conversation_Generation_with_Graph_Attention_fig7.PNG)
![Results of manual evaluation](pic/Knowledge_Aware_Conversation_Generation_with_Graph_Attention_fig8.PNG)


## Source Code
- [Commonsense Conversational Model(CCM)](https://github.com/tuxchow/ccm)
