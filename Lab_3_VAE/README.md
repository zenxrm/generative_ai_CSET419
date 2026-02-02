# Variational Autoencoder (VAE) on MNIST

### Dataset
- **MNIST Dataset**

## Model Architecture

### Encoder
- Input: Flattened image (28 × 28 = 784)
- Fully connected layer with ReLU activation
- Outputs:
  - Mean (μ) of latent distribution
  - Log-variance (log σ²) of latent distribution

### Reparameterization Trick
To allow backpropagation through stochastic sampling, latent vectors are sampled using:
- z = μ + ε × σ , where ε ~ N(0, I)

  
### Decoder
- Input: Latent vector `z`
- Fully connected layers with ReLU activation
- Output layer with Sigmoid activation to reconstruct the image


## Experiments Performed

### 1. Autoencoder-like Training (MSE Only)
- Reconstruction loss: Mean Squared Error (MSE)
- No KL-divergence applied
- Acts as a standard Autoencoder
- Results in lower reconstruction loss and sharper images
- Latent space is not regularized and not suitable for sampling

<img width="715" height="571" alt="Screenshot 2026-01-27 193909" src="https://github.com/user-attachments/assets/d39b5981-1ae8-45c9-8013-74f23a8d6f13" />

<img width="624" height="650" alt="Screenshot 2026-01-27 193853" src="https://github.com/user-attachments/assets/599c2945-82da-4015-b093-7b96ee771b93" />


### 2. Variational Autoencoder Training (MSE + KL)
- Reconstruction loss: Mean Squared Error (MSE)
- Regularization loss: KL-divergence
  
- Total loss: Loss = MSE + KL-divergence

  - Encourages latent space to follow a standard normal distribution
- Enables generative sampling
- Slightly higher loss due to regularization
- Reconstructions appear smoother, which is expected behavior in VAEs
<img width="774" height="583" alt="Screenshot 2026-01-27 195014" src="https://github.com/user-attachments/assets/8437988d-b0ae-49b4-ab88-2ad7dc06804d" />

<img width="686" height="672" alt="Screenshot 2026-01-27 195044" src="https://github.com/user-attachments/assets/1291d87f-24fb-4b1d-a7e7-c82a740f02c7" />


## Training Details
- Optimizer: Adam
- Learning rate: 0.001
- Epochs:
  - 50 epochs for both experiments
- Batch size: 128


## Results

- Both loss curves show stable convergence, indicating successful training.
- MSE-only training converges faster and reaches a lower loss.
- MSE + KL training converges more slowly due to the additional KL regularization.
- Generated samples from the VAE demonstrate meaningful digit-like structures.
- Slight blurriness in generated images is an inherent characteristic of VAEs.


