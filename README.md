# Visual Question Answering (VQA) with BLIP-CLIP

## Project Overview
This project explores the challenges of Visual Question Answering (VQA) by integrating visual and textual data to enhance comprehension of complex educational content, such as machine learning lectures. By developing tailored datasets and advanced multimodal VQA models, the project aims to advance academic question-answering systems and contribute to AI research.

## Objectives

1. **Dataset and Model Development**  
   Create a comprehensive dataset and develop advanced multimodal VQA models tailored to analyze textual and visual data effectively.

2. **Addressing Educational Challenges**  
   Enhance VQA systems to handle complex educational content, improving comprehension of intricate materials such as deep learning lectures.

3. **Advancing AI Research**  
   Explore innovative techniques for integrating visual and linguistic data, focusing on challenging academic scenarios.

---

## Data Creation

### Image Collection
- Extracted images from deep learning lecture slides.
- Resized all images to 224x224 pixels for consistency.

### Transcript Collection
- Utilized tools like Deepgram and Google Speech-to-Text API for transcription.
- Manually reviewed and corrected transcription errors due to noisy recordings.

### Query and Response Formulation
- Generated 10 question-answer pairs based on slide content.
- Ensured contextual relevance and completeness.

---

## Data Preprocessing

1. **Integration and Organization**  
   Merged datasets containing question-answer pairs, transcripts, and images based on attributes like week and page numbers. Renamed columns for clarity (e.g., "instruction" to "question," "response" to "answer").

2. **Dataset Partitioning**  
   Split data into training (90%) and validation (10%) sets.

3. **Dataset Preparation**  
   - Resized images to 224x224 pixels.  
   - Combined questions and transcripts into textual prompts.  
   - Trimmed text exceeding model token limits.  
   - Formatted responses for model training and validation.

---

## Methodology: BLIP-CLIP

### Workflow
1. **Input**  
   - Accepts both instruction (text) and image as inputs.

2. **Text Processing**  
   - Tokenizes and normalizes text using BLIP Text Processor.  
   - Encodes instruction with BLIP Text Encoder to generate text features.

3. **Image Processing**  
   - Processes images with CLIP Processor (resizing and normalization).  
   - Encodes images with CLIP Image Encoder to generate image features.

4. **Multimodal Fusion**  
   - Combines text and image features through a Cross-modal Interaction Module.

5. **Output Generation**  
   - Processes combined features through a Multimodal Classification Head to produce the predicted response.

### Highlight
Leverages both BLIP and CLIP models for robust text-image understanding and response generation.

---

## Results
| Model      | ROUGE-1 | ROUGE-2 | ROUGE-L | BLEU   | Cosine |
|------------|---------|---------|---------|--------|--------|
| BLIP       | 0.2350  | 0.0408  | 0.1884  | 0.0138 | 0.3414 |
| BLIP-CLIP  | 0.393   | 0.19137 | 0.34126 | 0.1207 | 0.42   |

---

## Future Work
- Develop an interactive user interface (UI).
- Achieve higher accuracy using large language models (LLMs).

---

## How to Run the Project

1. **Install Dependencies**  
   - Ensure Python and Jupyter Notebook are installed.  
   - Install required libraries using `requirements.txt`.

   ```bash
   pip install -r requirements.txt
   ```

2. **Run the Notebook**  
   Open the `Blip_clip.ipynb` file in Jupyter Notebook and execute the cells in order.

3. **Train and Evaluate**  
   Follow the notebook instructions to preprocess data, train the model, and evaluate results.

---
