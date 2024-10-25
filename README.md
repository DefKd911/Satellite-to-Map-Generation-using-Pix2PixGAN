# Satellite-to-Map-Generation-using-Pix2PixGAN 🛰️🗺️
This project implements a Pix2PixGAN to generate maps from satellite images using Keras/TensorFlow. The model is trained on satellite images paired with their corresponding maps, learning to perform image-to-image translation.

![image](https://github.com/user-attachments/assets/bd3026d5-59ca-4752-8fcb-ecfd7eab47e3)  

Pix2PixGAN is a conditional Generative adversarial network that learns to map input images to output images. In this project, we use it to convert satellite imagery into map-style representations. The implementation is based on the original Pix2Pix paper and adapted for the satellite-to-map use case.

# 🏗️ Pix2Pix GAN Architecture

![image](https://github.com/user-attachments/assets/9006f37e-d009-4bdf-9991-b65d7cc8737f)  
The Generator tries to minimize the L1 loss to produce output images close to the ground truth,  
while the Discriminator enhances the realism of the generated maps using adversarial loss.   

**Generator (U-Net)**
- Encoder-decoder architecture
- Skip connections between layers
Input: 256x256x3 satellite image
Output: 256x256x3 map image

**Discriminator (PatchGAN)**
- Classifies 70x70 overlapping patches
- Promotes high-frequency structure
- determines whether the generated image is real or fake
-  focuses on patches of the image rather than the whole image.
Input: Concatenated satellite and map images
Output: Patch-level real/fake classifications

![image](https://github.com/user-attachments/assets/12c7c327-92e2-49ae-9c99-ee5c2cfeefab)



# Training 

**Key Parameters :**  
epochs: Number of training epochs (default: 200)  
batch_size: Images per batch (default: 1)  
lr: Learning rate (default: 0.0002)  
beta1: Adam optimizer beta1 (default: 0.5)  
lambda_l1: L1 loss weight (default: 100)  


**📦 Requirements**  
TensorFlow >= 2.8.0  
Keras >= 2.8.0  
Streamlit >= 1.8.0  
NumPy >= 1.21.0  
Pillow >= 9.0.0  
OpenCV >= 4.5.0  


# Web Interface
The project includes a Streamlit web interface for easy model inference:

-> Upload satellite image  
-> Automatic preprocessing   
-> Generate corresponding map   
-> Download or display results  

![image](https://github.com/user-attachments/assets/52d27030-7267-49d7-9f5b-50ed7f4cedcd)

# Applications
This project can be used for several practical applications, including:  

- **Urban Planning**: Visualize maps generated from satellite images to aid in urban development planning.  
- **Disaster Management**: Rapidly generate maps from satellite images to assess geographical changes during natural disasters.  
- **Geospatial Analysis**: Automate the process of converting satellite data into human-readable maps for geospatial studies.  
- **Cartography**: Automate the creation of map overlays based on satellite imagery.
