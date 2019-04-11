# R+FGSM-pytorch
**A pytorch implementation of "[Ensemble Adversarial Training : Attacks and Defences](https://arxiv.org/abs/1705.07204)"**

## Summary
This code is a pytorch implementation of **R+FGSM**   
In this code, I used above methods to fool [Inception v3](https://arxiv.org/abs/1512.00567).   
'[Giant Panda](http://www.image-net.org/)' used for an example.   
You can add other pictures with a folder with the label name in the 'data/imagenet'.    

## Requirements
* python==3.6   
* numpy==1.14.2   
* pytorch==1.0.1   

## Important results not in the code
- This paper showed that adverarial training with single-step methods admits a degenerate global minimum. At least two substantially different global minima exists. (p.4)
  - If there is no adversarial examples near the traning examples, then a hypothesis is robust to all infinity norm distance bounded perturbations.
  - If a model is the approximation method underlying the specific attack, then other attacks are possible.
- It suggest to use **R+FGSM** (p.5-6)
  - The **[gradient masking](https://seclab.stanford.edu/AdvML2017/slides/17-09-aro-aml.pdf)** may results adversarial methods can't produce the best adversarial example.
  - This is caused by the highly curved loss in the vicinity of the data point.
  - Thus we need a random step in attack methods.

- Ensemble adversarial training is needed(p.7-8)
  - With pretrained models, we are able to generate variety adversarial examples. And we can use it for adversarial training a new model.
  - They use "**Pre-trained Models**(Inception v3, IncRes v2, ResNet v2)" to extract adversarial exampels and use it for adversarial training "**Trained model**(Inception v3, IncRes v2)". Finally, test with adversarial examples from "**Holdout Models**(Inception v4, ResNet v1, ResNet v2)"