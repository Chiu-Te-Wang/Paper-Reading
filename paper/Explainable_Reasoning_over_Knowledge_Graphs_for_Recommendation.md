# Explainable Reasoning over Knowledge Graphs for Recommendation
## Information
- 2019 AAAI
- Wang, Xiang, et al.

## Keywords
- KG
- Recommendation

## Summary
1. Extract all the interact paths within 6 hops between entities
![Knowledge Graph](/pic/Explainable_Reasoning_over_Knowledge_Graphs_for_Recommendation_fig1.PNG)
2. Train a LSTM with entities and relations of these paths as input sequences
	- The embedding include entity, entity type, and relation embedding
3. Train a **Weighted Pooling Layer** to predict the probability of the user-item by using the path embedding from step2 as the features
![Model Structure](/pic/Explainable_Reasoning_over_Knowledge_Graphs_for_Recommendation_fig2.PNG)

## Source Code
### [Knowledge-aware Path Recurrent Network(KPRN)](https://github.com/eBay/KPRN)


