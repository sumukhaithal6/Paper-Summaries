# [Intriguing Properties of Vision Transformers](https://arxiv.org/pdf/2105.10497.pdf)
* **Tags**: Vision Transformers, Robustness, Shape-texture
* **Year**: 2021

## Abstract:
1. Transformers are highly robust to severe occlusions, perturbations and domain shifts
2. ViTs are significantly less biased towards textures compared to CNNs.
3. Using ViTs to encode shape representation leads to an interesting consequence of accurate semantic segmentation without pixel-level supervision.
4. Off-the-shelf ViT features from ImageNet pretrained models generalize exceptionally well to new domains

## Key Points
1. Analysis on three Transformer families - [ViT](https://arxiv.org/pdf/2010.11929.pdf) (Vision Transformers), [DeiT](https://arxiv.org/pdf/2012.12877.pdf) and [T2T](https://arxiv.org/pdf/2101.11986.pdf).
2. Vision Transformers show excellent robustness to the foreground (salient) and background (non-salient) content removal. Even after randomly dropping 50% of the data, ViT has 70% accuracy whereas ResNet-50 has 0.1% accuracy.
3. Shape Vs. Texture: Can Transformer Model Both Characteristics?
	* ViT models trained on ImageNet exhibit higher shape bias in comparison to similar capacity CNN models.
	* DeiT-S (trained on Stylized Image Net (SIN)) reaches human-level performance when trained on a SIN dataset but has lower top-1 accuracy.
	* Shape Distillation - Propose an addition of shape token and shape distillation. (A SIN trained ResNet-50 is used).
	* Shape-biased ViT Offers Automated Object Segmentation.
4. Does Positional Encoding preserve the Global Image Context?
	* Transformers are permutation invariant. Thus positional encoding is added to preserve some structure.
	* The effect of positional encoding towards injecting structural information of images to ViT models is limited. The dependence on positional encodings to perform well under occlusions is inaccurate.
	* DeiT models retain accuracy to a much higher extent in comparison to their CNN counterparts when spatial structure of input images is disturbed. (Eg. 2x2 patch shuffle, 4x4 patch shuffle)
5. Robustness of Vision Transformers to Adversarial & Natural Perturbations
	* Convolutional and transformer models trained without augmentations on ImageNet or SIN are more vulnerable to image corruptions (irrespective of shape bias).
6. Optimal Off-the-shelf Tokens for Vision Transformer
	* Concatenate the class tokens from different blocks and train a linear classifier to transfer the features to downstream tasks - ensemble.
	* Using ensemble works better than standard DeiT model and CNNs in transfer learning and few shot learning.
