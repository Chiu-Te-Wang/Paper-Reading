# Slot-Gated Modeling for Joint Slot Filling and Intent Prediction
## Information
- 2018 NAACL-HLT (Short Papers)
- Goo, Chih-Wen, et al.

## Keywords
- NLU
- Intent Detection
- Slot Filling

## Contribution
- The proposed slot-gated approach achieves better performance than the attention-based models.

## Summary
- Propose the **Slot-Gated Mechanism** to learn the relationship between intent and slot attention vectors in order to  obtain better semantic frame results by the global optimization
	![Model Structure](pic/Slot-Gated_Modeling_for_Joint_Slot_Filling_and_Intent_Prediction_fig1.PNG)
- Slot-Gated Mechanism:
	![Slot-Gated Mechanism](pic/Slot-Gated_Modeling_for_Joint_Slot_Filling_and_Intent_Prediction_fig2.PNG)
	- Slot context vector c<sub>i</sub><sup>S</sup> and intent context vector c<sup>I</sup> are combined(c<sup>I</sup> broadcasts in time dimension to have the same shape with c<sub>i</sub><sup>S</sup>) to pass through the slot gate.
		![Slot-Gated Mechanism Equation](pic/Slot-Gated_Modeling_for_Joint_Slot_Filling_and_Intent_Prediction_fig3.PNG)
	- Then, use g to weight between h<sub>i</sub> and c<sub>i</sub><sup>S</sup> to derive output y<sub>i</sub><sup>S</sup>
		![Weighted output Equation](pic/Slot-Gated_Modeling_for_Joint_Slot_Filling_and_Intent_Prediction_fig4.PNG)

- Results:
	![Results](pic/Slot-Gated_Modeling_for_Joint_Slot_Filling_and_Intent_Prediction_fig5.PNG)

## Source Code
- [SlotGated-SLU](https://github.com/MiuLab/SlotGated-SLU)