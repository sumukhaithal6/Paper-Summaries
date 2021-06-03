# [Why Adam Beats SGD for Attention Models](https://openreview.net/pdf?id=SJx37TEtDH)
* **Tags**: Optimization, Adam, SGD, Gradient Clipping

## Abstract
1. Adam outperforms SGD in tasks like attention. 
2. Heavy tail distribution of the noise in stochastic gradients is the main reason of SGD's poor performance.
3. Proposed Method - Adaptive Coordinate wise clipping.
4. Understand Adam through the lens of clipping.

## Key Points
1. Distribution of stochastic gradients:(norm of gradients of minibatch)\
	ImageNet - Gaussian\
	BERT - Heavy Tail 
2. Clipping magnitude of stochastic gradients sufficient to ensure convergence.
3. Adam implicitly performs coordinate wise gradient clipping and hence can tackle heavy tailed noise.
4. ‖g−∇f(x)‖ - gradient noise norm where g is the gradient of the minibatch.
5. **Key idea** - by clipping SGD, we can control the variance.
6. Smaller threshold values means simply smaller variance, but also higher bias. If the noise distribution is very heavy-tailed, one could compensate by picking a smaller threshold.
7. GClip updates scale down magnitude and preserve direction.\
CClip may not preserve the direction.
Therefore, if noise distribution is heavy tailed, CClip may take advantage of this and converge faster.
8. The noise pattern is from the interaction of both architecture and data distribution.
9. The distribution of gradient noise is non-stationary during BERT training, while it remains almost unchanged for ResNet training on ImageNet.
