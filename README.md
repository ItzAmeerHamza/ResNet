# ResNet-Pytorch-Implementation

# Deep Residual Learning for Image Recognition

### 1. Introduction 

Numerous experiments have verified that deep convolutional neural net- works significantly increase the performance of various models in image classification. However, as networks goes deeper and deeper, a number of problem arises. First is the vanishing/exploding gradients. This can be solved through normalized initialization and intermediate normalization layers. Second is the degradation problem, which means the accuracy gets saturated and does not improve at some point and beyond.

This research shows that residual learning framework successfully solves the degradation problem and outperforms the original ‘plain’ deep networks in two ways. Deep residual nets not only optimizes easier but also signif- icantly increases accuracy over plain deep networks. This phenomenon is proven throughout the CIFAR-10 set, and ImageNet dataset. In addition, it also won 1st places on various competitions both on vision and non-vision tasks.

<img src="Residual.png" height="150"/>

### 2. Deep Residual Learning 

**Residual Learning**

Figure 1 shows the idea of residual function F(x). If H(x) is denoted as the desired underlying mapping, this research suggests to feed a different map- ping F(x), which is defined by F(x) = H(x) – x, hence the name ‘Residual learning Framework’. After the input x is fed through this mapping, identity mapping of x itself is directly added to the output by skipping layers – called ‘skip connections’. As a result, the final formulation becomes F(x) + x.

**Identity Mapping by Shortcuts**

The plus x denotes the short connection of the identity mapping. This map- ping does not lead to extra parameters or time complexity. One thing to keep in mind is that the dimensions of F and x must be equal. For cases when the input/output channels are changed, it is important to match the di- mensions manually. One way is to pad zeros into the input x, and the other is to multiply an independent square matrix Ws.

**Network Architectures / Implementation**

The base network architecture is inspired from VGG nets. One notable difference is that the residual model has much less filters and complexity. Figure 2 on the right shows the VGG net, 34-layer plain, and 34-layer resid- ual, respectively. The input image is randomly sampled from range [256, 480]. Then, it is randomly cropped into 224x224 image. Batch Normaliza- tion is implemented right after each convolution and before activation. Mini batch size of 256 is used along with SGD. Total of 60 ∗ 104 iterations are trained, and learning rate starts from 0.1 and drops by 10 when progress is slow.

<img src="Model.png" height="400"/>

