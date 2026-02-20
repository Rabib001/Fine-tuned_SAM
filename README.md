# Fine-Tuning Segment Anything Model (SAM) for Mitochondrial Segmentation

Google Colab Notebook:  
YOUR_COLAB_LINK_HERE

---

## Project Overview

This project focuses on fine-tuning Meta AI’s Segment Anything Model (SAM) for domain-specific biomedical image segmentation. While SAM performs well on natural images using zero-shot prompting, it is not optimized for microscopy images. To address this limitation, SAM was fine-tuned on labeled mitochondrial microscopy datasets to improve segmentation accuracy.

The objective is to enable automated and accurate identification of mitochondria in microscopy images for downstream biomedical analysis.

---

## Model Architecture

SAM consists of three main components:
- Image Encoder: Vision Transformer (ViT-H) pretrained on large-scale image datasets  
- Prompt Encoder: Encodes point or mask prompts into embeddings  
- Mask Decoder: Transformer-based decoder that predicts segmentation masks  

This project adapts the model by training it with supervised ground-truth mitochondrial masks rather than relying solely on zero-shot prompts.

---

## Technologies Used

- Python  
- PyTorch  
- CUDA (GPU acceleration)  
- Segment Anything Model (SAM)  
- Computer Vision  
- Deep Learning  
- Google Colab (GPU runtime)  

---

## Training Pipeline

- Preprocessed microscopy images and corresponding ground-truth masks  
- Generated approximately 2,000 training samples from 165 labeled images  
- Fine-tuned SAM using Dice + Cross Entropy (DiceCE) loss  
- Trained for 10 epochs  
- Utilized CUDA-enabled GPUs for accelerated training and inference  
- Implemented end-to-end pipelines for data loading, training, evaluation, and visualization  

---

## Evaluation

Performance was evaluated using the Intersection over Union (IoU) metric.

Average results:

| Model          | IoU Score |
|----------------|-----------|
| Base SAM       | ~0.09     |
| Fine-tuned SAM | ~0.76     |

Fine-tuning resulted in more than an eightfold improvement in segmentation accuracy.

---

## Sample Results

The fine-tuned model is able to:
- Accurately identify mitochondrial structures  
- Reduce over-segmentation observed in the base SAM model  
- Generate refined segmentation masks and probability maps  

---

## Potential Applications

- Automated cellular structure analysis  
- Disease correlation studies based on mitochondrial morphology  
- Extension to segmentation of other organelles (nuclei, membranes)  
- Biomedical research and diagnostic support tools  

---

## Key Contributions

- Fine-tuned a large vision foundation model for domain-specific segmentation  
- Implemented GPU-accelerated training and inference using CUDA  
- Developed reproducible data pipelines for biomedical imaging  
- Benchmarked zero-shot versus domain-adapted model performance  

---

## Repository Structure

