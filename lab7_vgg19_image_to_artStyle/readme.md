# Neural Style Transfer (NST) using VGG19
<img width="1264" height="407" alt="Screenshot 2026-03-08 170520" src="https://github.com/user-attachments/assets/debf95ed-c04c-478d-9e17-d26336a3cb23" />


<img width="1181" height="391" alt="Screenshot 2026-03-08 165309" src="https://github.com/user-attachments/assets/fc6066e1-2a9d-43e6-b46a-81b9e139fe08" />


## Overview
This project implements **Neural Style Transfer (NST)** to generate an artistic image by combining:

- **Content** from one image
- **Style** from another image

The technique uses a pretrained **VGG19 convolutional neural network** to extract feature representations from both images.  
A generated image is optimized so that it preserves the **structure of the content image** while adopting the **texture and artistic patterns of the style image**.

---

# Objective

The objective of this lab is to implement **Neural Style Transfer** and generate a stylized image by combining:

- Content from a real-world image (scenery)
- Artistic style from an artwork image

The output image should:

- Preserve the **structure of the content image**
- Transfer **textures, colors, and artistic patterns** from the style image

---

# Input Images

Two images were used as input for the experiment.

## Content Image
- Represents the structural layout of the final output.
- Provides objects, shapes, and spatial arrangement.

## Style Image
- Represents the artistic style.
- Provides texture patterns, brush strokes, and color palette.

Both images are resized and normalized before being processed by the neural network.

---

# Model Used

The model used for feature extraction is **VGG19**, a pretrained convolutional neural network trained on the **ImageNet dataset**.

Important characteristics:

- The network weights are **frozen**
- The network acts as a **feature extractor**
- Only the **generated image is optimized**


---

## 1. Image Preprocessing

Images are prepared before passing them into the network.

Steps performed:

- Resize images to a fixed resolution
- Convert images to tensors
- Normalize using ImageNet mean and standard deviation

Normalization ensures compatibility with the pretrained VGG19 model.

---

## 2. Feature Extraction

VGG19 extracts feature maps from selected convolutional layers.

### Content Layer

```
conv4_2
```

This deeper layer captures the **high-level structure and layout** of the content image.

---

### Style Layers

Multiple layers are used to capture style information at different scales.

```
conv1_1
conv2_1
conv3_1
conv4_1
conv5_1
```

Lower layers capture:

- edges
- colors
- simple textures

Higher layers capture:

- complex patterns
- artistic structures

---

## 3. Style Representation using Gram Matrix

Style is represented using the **Gram Matrix**.

The Gram Matrix measures correlations between feature maps and captures:

- texture
- color relationships
- brush stroke patterns

It ignores spatial layout and focuses on **statistical patterns of the style image**.

---

## 4. Loss Functions

Three loss functions are used during optimization.

### Content Loss

Measures the difference between feature maps of the content image and generated image.

```
Content Loss = MSE(Content Features − Generated Features)
```

This ensures the output image preserves the **structure of the content image**.

---

### Style Loss

Measures the difference between Gram matrices of the style image and generated image.

```
Style Loss = MSE(Gram(Generated) − Gram(Style))
```

This transfers the **artistic style and texture**.

---

### Total Loss

The final loss combines both losses.

```
Total Loss = Content Weight × Content Loss
           + Style Weight × Style Loss
```

Adjusting these weights controls the balance between content preservation and style transfer.

---

## 5. Image Optimization

Instead of training the network, the algorithm **optimizes the pixels of the generated image**.

Process:

```
Content Image
      ↓
Initialize Generated Image
      ↓
Extract Features using VGG19
      ↓
Compute Content Loss
Compute Style Loss
      ↓
Combine Losses
      ↓
Backpropagation
      ↓
Update Generated Image
```

The **L-BFGS optimizer** is used because it works well for image optimization tasks.




# Applications

Neural Style Transfer is widely used in:

- AI-generated artwork
- Photo stylization
- Film and animation effects
- Creative design tools
- Generative AI art applications


