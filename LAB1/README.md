
## 1: Synthetic Data Generation using a Pre-trained Generative Model 

### Notebook name: pretrained_GenAI_no_op.ipynb

### Random Image Generation
First, we generated five images using different text prompts to see how text is converted into images.

generated image :
<img width="1258" height="697" alt="Screenshot 2026-01-14 164350" src="https://github.com/user-attachments/assets/0efa191d-92ab-4dd7-a85c-b8432bc85c8e" />

---

### Cat Species Dataset Creation
then a synthetic image dataset was created for cat species classification.

Details of the dataset:
- Total number of cat species: 40  
- Number of images per species: 10  
- Total images generated: 400  


### Cat Species Included
The dataset includes the following cat species:
Abyssinian, American Bobtail, American Curl, American Shorthair, American Wirehair, Balinese, Bengal, Birman, Bombay, British Shorthair, Burmese, Chartreux, Cornish Rex, Devon Rex, Egyptian Mau, Havana Brown, Himalayan, Japanese Bobtail, Korat, LaPerm, Maine Coon, Manx, Norwegian Forest, Ocicat, Oriental Shorthair, Persian, Ragdoll, Russian Blue, Scottish Fold, Selkirk Rex, Siamese, Siberian, Singapura, Snowshoe, Somali, Sphynx, Tonkinese, Turkish Angora, and Turkish Van.

generated sample :

#### Turkish Van Cat
<img width="512" height="512" alt="Turkish_Van_cat_9" src="https://github.com/user-attachments/assets/b01adf65-beb4-4e04-8edf-0bb9a6455e7a" />


#### Russian Blue Cat
<img width="512" height="512" alt="Russian_Blue_cat_1" src="https://github.com/user-attachments/assets/4f4c897d-a816-487c-a470-de949d8e5ba7" />

---

### Classification using a Pre-trained Model
The synthetic dataset was used to train a pre-trained convolutional neural network for image classification.

- Model used: EfficientNet-B0 model 
- Number of classes: 40  
- Final accuracy achieved: 95.25 percent  

---

## 2: Custom CNN Training with Data Augmentation  

### Notebook name: custom_cnn_lab1.ipynb

### Dataset 
The synthetic dataset from pretrained_GenAI_no_op.ipynb was loaded from Google Drive .Then we agumented the dataset

---

### Custom CNN Model
A custom Convolutional Neural Network was designed and trained from scratch without using any pre-trained weights.

---

### Training Summary
Total classes: 40  
Total images after augmentation: 6000  
Final accuracy achieved: 91.67 percent  

 ###model prediction
<img width="795" height="569" alt="Screenshot 2026-01-14 161411" src="https://github.com/user-attachments/assets/e4234e35-08b0-409a-88f6-6c0ccebe903a" />

---
<img width="710" height="612" alt="Screenshot 2026-01-14 161639" src="https://github.com/user-attachments/assets/7b385f64-c54a-45b4-b01d-b3bdac4f52a7" />


---

## Resources and Links
Original synthetic dataset:  
https://drive.google.com/drive/folders/1gRwaZ4tz-2pil6dC0-7aqjRn71pOzDQG?usp=drive_link

Augmented dataset:  
https://drive.google.com/drive/folders/1d-45UhEp0AVWor9zh5jWv4ltStwbz2ok?usp=drive_link

Trained model files:  
https://drive.google.com/drive/folders/1Yj046vLzzCbNNZ84fjdL-GcyUxSjfYbL?usp=drive_link

