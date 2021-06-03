# [Understanding deep learning requires rethinking generalization](https://arxiv.org/pdf/1611.03530.pdf)
* **Tags**: Generalization
* **ICLR 2017 (Oral)**
## Abstract
1. CNNs can fit random labelling on training data.
2. This is unaffected by regularization techniques.
3. They can also fit completely unstructured noise.

## Key points
1. Important question: What differentiates neural networks that generalize well from those that don't?
2. Deep Neural Networks can easily fit random labels. (Hence, by randomizing labels, generalization error increases)
3. The capacity of neural networks is sufficient to fit to training set.
4. Optimization on random labels remains easy. (Not much increase in time)
5. CNNs can fit random noise. (Replace true images by random pixels)
6. Explicit regularization may improve generalization performance, but is neither necessary nor by itself sufficient for controlling generalization error.

