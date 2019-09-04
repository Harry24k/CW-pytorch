# CW-pytorch
**A pytorch implementation of "[Towards Evaluating the Robustness of Neural Networks](https://arxiv.org/abs/1608.04644)"**

## Summary
This code is a pytorch implementation of **CW attack**.   
In this code, I used above methods to fool [Inception v3](https://arxiv.org/abs/1512.00567).   
'[Giant Panda](http://www.image-net.org/)' used for an example.   
You can add other pictures with a folder with the label name in the 'data/imagenet'.    

## Requirements
* python==3.6   
* numpy==1.14.2   
* pytorch==1.0.1   

## Important results not in the code
- This paper suggested new approach to the adversarial attack.(p.6-7)
    - Compared 7 new objective functions(*f*) for generating adversarial images.
    - Used *tanh* for solving box constraints.
- Three new attack algorithms proposed.(p.9-10)
    - They are L_2, L_0, L_inf. (Among these, L_2 is implementd in this code)
- These attacks made the [defensive distillation](https://arxiv.org/abs/1511.04508) helpless.(p.12-14)
    - All of new attack methods succeed with 100% success.

## Notice
- This Repository won't be updated.
- Please check [the package of adversarial attacks in pytorch](https://github.com/Harry24k/adversairal-attacks-pytorch)
