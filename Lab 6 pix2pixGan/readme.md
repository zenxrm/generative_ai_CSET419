# Image-to-Image Translation using Pix2Pix GAN

This repository contains experiments with **Pix2Pix Conditional GANs** for image-to-image translation tasks. Two problems were explored:

#### **Edges → Shoes translation** using the Edges2Shoes dataset
- file name : lab6 _complete.ipynb
  
#### **Sketch → Face generation** using the CUHK Face Sketch dataset
- file name : sketch to face.ipynb

The goal of these experiments is to understand how conditional GANs learn mappings between paired images and how they compare to traditional CNN-based approaches.


# Edges to Shoes Translation

## Overview

This experiment implements **Pix2Pix**, a conditional Generative Adversarial Network used for paired image translation. The objective is to convert **edge maps of shoes into realistic shoe images**.

A **baseline CNN encoder–decoder model** is also used for comparison to observe the difference between traditional CNN approaches and GAN-based models.

## Dataset

Dataset used: **Edges2Shoes**
Dataset link : https://www.kaggle.com/datasets/balraj98/edges2shoes-dataset


Each image contains two parts:

- Left side: edge map of a shoe  
- Right side: real shoe image  

During preprocessing the paired image is split into two halves where the edge map becomes the input and the real shoe image becomes the target.

## Architecture

Pix2Pix consists of two networks.

**Generator (U-Net)**  
The generator uses an encoder–decoder structure with skip connections that help preserve spatial information while reconstructing the image.

**Discriminator (PatchGAN)**  
The discriminator evaluates small image patches instead of the entire image. This encourages sharper textures and better local realism.

## Loss Function

Pix2Pix combines two losses:

Generator Loss = Adversarial Loss + λ × L1 Loss

The adversarial loss encourages realism while L1 loss ensures the generated image remains structurally similar to the ground truth.

## Results

**Baseline CNN**
- Produces smooth but blurry outputs  
- Lacks fine texture details  

**Pix2Pix GAN**
- Generates sharper textures  
- Produces more realistic images  

Due to limited training time and the unstable nature of GAN training, some generated images may contain artifacts.

---

# Sketch to Face Generation

## Overview

This experiment implements a **Sketch → Face image translation model** using Pix2Pix. The goal is to generate a realistic face image from a given facial sketch.

## Dataset

Dataset used: **CUHK Face Sketch Database (CUFS)**.
dataset link : https://www.kaggle.com/datasets/arbazkhan971/cuhk-face-sketch-database-cufs?select=photos

Each sample contains:
- A hand-drawn facial sketch
- The corresponding real face photograph

After preprocessing and pair validation, approximately **134 aligned sketch-photo pairs** were used for training.

## Model

The Pix2Pix architecture was used with:

- **U-Net Generator** to translate sketches into face images  
- **PatchGAN Discriminator** to evaluate local image patches and improve realism  

## Training Objective

The generator is trained using both adversarial loss and reconstruction loss:

Generator Loss = GAN Loss + λ × L1 Loss

This encourages the generated face to look realistic while preserving the structure of the original sketch.

## Observed Results

#### at starting epochs :-
<img width="539" height="817" alt="Screenshot 2026-03-08 155851" src="https://github.com/user-attachments/assets/18e91780-7868-4942-bbbc-36de0e5d4531" />


#### after good number of epochs:-
<img width="552" height="817" alt="Screenshot 2026-03-08 155902" src="https://github.com/user-attachments/assets/0f136a7d-aa4b-4a03-b674-e57fa56e5088" />


## Limitations

Several factors limited performance:

- Very small dataset (~134 training pairs)  
- Limited diversity in faces and lighting conditions  
- Sketches drawn in a single artistic style  
- L1 reconstruction loss leading to blurred outputs
- not giving good result on different sketches as differnt type of shadings in real world sketches

