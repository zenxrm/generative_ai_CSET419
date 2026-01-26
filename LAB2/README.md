 
## Lab–2: Generative Adversarial Networks (GANs)


## Files

- **`GAN_minsit.ipynb`**  
  Basic GAN trained on the **MNIST** handwritten digits dataset.

- **`WGAN_fashion.ipynb`**  
  **WGAN-GP** trained on the **Fashion-MNIST** dataset.


---

##  Part 1: GAN on MNIST
-File name: GAN_minsit.ipynb
- Dataset: MNIST (28×28 grayscale images)  
- Normalization: `[-1, 1]`

### Model
- **Generator**: Generates fake digit images from noise  
- **Discriminator**: Classifies images as real or fake  

## Part 2: WGAN-GP on Fashion-MNIST
-File name: WGAN_fashion.ipynb

### Dataset
- Fashion-MNIST  
- Image size: 64×64  
- Normalization: `[-1, 1]`

### Why WGAN-GP?
- Improves training stability  
- Reduces mode collapse  
- Handles vanishing gradients better than basic GAN  

<img width="1464" height="735" alt="image" src="https://github.com/user-attachments/assets/c5b10291-17b9-44ea-83d3-55e8eceaa4ad" />

<img width="1480" height="729" alt="image" src="https://github.com/user-attachments/assets/4113a7ce-3edd-458c-9261-2a05405175bb" />
