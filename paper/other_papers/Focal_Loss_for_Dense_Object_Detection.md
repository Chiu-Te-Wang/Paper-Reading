# Focal Loss for Dense Object Detection
## Information
- 2017 ICCV
- Tsung-Yi Lin, Priya Goyal, Ross Girshick, Kaiming He, and Piotr Doll´ar

## Keywords
- Focal Loss
- Object Detection

## Contribution
- Identify class imbalance as the primary obstacle preventing one-stage object detectors from surpassing top-performing, two-stage methods.
- Propose the focal loss which applies a modulating term to the cross entropy loss in order to focus learning on hard negative examples.

## Summary
- Propose a reshaping the standard cross entropy loss such that it down-weights the loss assigned to well-classified examples to address class imbalance(hard or imbalance class).

- The Normal Cross Entropy (CE) Loss: (binary classification for example)
	![The Normal CE Loss](other_papers/pic/Focal_Loss_for_Dense_Object_Detection_fig1.PNG)
- The Balanced Cross Entropy Loss:
	![The Balanced CE Loss](other_papers/pic/Focal_Loss_for_Dense_Object_Detection_fig2.PNG)
	, where α<sub>t</sub> represent that the weighting factor α∈[0,1] for class 1, and 1-α for class -1
- The Focal Loss:
	![The Focal Loss](other_papers/pic/Focal_Loss_for_Dense_Object_Detection_fig3.PNG)
	, where γ is the focusing parameter γ >= 0(in this paper γ use 2)
	- The focusing parameter γ smoothly adjusts the rate at which easy examples are downweighted.
	- γ = 0, FL is equivalent to CE
- The Balanced CE + Focal Loss:
	![The Balanced CE + Focal Loss](other_papers/pic/Focal_Loss_for_Dense_Object_Detection_fig4.PNG)

- Results:
	![Results](other_papers/pic/Focal_Loss_for_Dense_Object_Detection_fig5.PNG)

## Source Code
- [Detectron](https://github.com/facebookresearch/Detectron)