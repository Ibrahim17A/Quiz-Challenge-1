# Controlled E-Commerce Product Image Generation Using Stable Diffusion

## Overview
This project explores how Stable Diffusion can be used for controlled e-commerce product image generation. The system takes structured product metadata such as title, category, and attributes, converts it into prompts, and generates product images. The project compares baseline naive prompting with improved structured prompting and controlled prompting using negative prompts.

## Scenario
This project uses the e-commerce product image generation scenario. E-commerce platforms often need clean and consistent product images, and generative AI can help create these images from metadata. The goal of this project is to improve product image generation quality and consistency through prompt engineering and controlled generation.

## Dataset / Input Metadata
Instead of using a large external dataset, this project uses a small sample metadata set for three products:
- Men's Running Shoes
- Women's Leather Handbag
- Minimalist Ceramic Coffee Mug

Each product includes:
- title
- category
- attributes
- style
- background

This structured metadata is mapped into prompts for image generation.

## Methodology
We built a controlled image generation pipeline for e-commerce products using Stable Diffusion. Product metadata including title, category, and attributes was mapped into prompts. We compared three prompt strategies:
1. Naive prompt using only the product title
2. Structured prompt using title, category, attributes, style, and background
3. Controlled prompt using the structured prompt plus a negative prompt

The goal was to improve prompt alignment, visual quality, and consistency while preserving useful diversity across generated product images.

## Stable Diffusion Pipeline
The system was implemented in Google Colab using the Hugging Face Diffusers library with the Stable Diffusion v1.5 model.

Pipeline steps:
1. Define structured product metadata
2. Convert metadata into prompts
3. Generate images using naive prompts
4. Generate images using structured prompts
5. Generate images using structured prompts with negative prompts
6. Save outputs
7. Compare results
8. Evaluate outputs

## Prompt Strategies

### 1. Naive Prompt
A simple prompt using only the product title.

Example:
`Men's Running Shoes`

### 2. Structured Prompt
A richer prompt built from metadata fields.

Example:
`Men's Running Shoes, Footwear, black, white sole, sporty, mesh upper, studio product photography, clean white background, centered product shot, highly detailed`

### 3. Controlled Prompt
The structured prompt with a negative prompt to reduce low-quality details and unwanted artifacts.

Negative prompt example:
`blurry, distorted, extra objects, duplicate product, cropped, low quality, text, watermark, unrealistic proportions, messy background, bad lighting`

## Control Mechanism
This project uses two control mechanisms:
- structured prompt templates
- negative prompts

These controls improve alignment between the metadata and the generated image while reducing noise and unwanted artifacts.

## Evaluation
The generated outputs were evaluated using four criteria:
- Prompt alignment
- Consistency
- Diversity
- Quality

Prompt alignment measures how well the image matches the intended metadata.
Consistency measures whether product identity and style remain stable across prompt strategies.
Diversity measures variation in output appearance without losing the core product concept.
Quality measures realism, clarity, and suitability for e-commerce use.

The project includes a baseline versus improved comparison and also discusses failure cases.

## Results
Overall, the naive prompts produced usable but less consistent results. The structured prompts improved product detail and scene control. The controlled prompts with negative prompting produced the cleanest outputs by reducing clutter, distortion, and irrelevant objects.

## Findings and Insights
The structured prompts performed better because they added specific product attributes and scene descriptions. Negative prompts further improved image cleanliness and reduced common diffusion model artifacts. This shows that adding control improves reliability for real-world product image generation.

## Failure Cases and Limitations
Some failure cases included:
- extra objects
- unrealistic textures
- shape distortions
- backgrounds that did not fully match the intended setting

These problems were more common with naive prompts and less common with controlled prompts. However, even with improved prompt design, Stable Diffusion was not fully reliable in every case.

## Tools and Libraries
- Python
- Google Colab
- Hugging Face Diffusers
- Stable Diffusion v1.5
- PyTorch
- Pandas
- Matplotlib
- Pillow

## How to Run
1. Open the notebook in Google Colab
2. Install the required libraries
3. Load the Stable Diffusion model
4. Run the cells to generate images
5. Review the outputs saved in the outputs folder
6. Fill in the evaluation table
7. Export results for presentation

## GitHub URL
Add your GitHub repository link here.

## Demo Video URL
Add your demo video link here.

## AI Tool Disclosure
AI tools used:
- ChatGPT was used to assist with project planning, code structure, prompt design, evaluation wording, README drafting, and presentation content.
- Google Colab was used to run the notebook.
- Hugging Face Diffusers and Stable Diffusion were used for image generation.

All final outputs, comparisons, and analysis were reviewed and organized by the student.
