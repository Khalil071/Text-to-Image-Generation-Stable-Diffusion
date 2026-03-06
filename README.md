Text-to-Image Generation using Stable Diffusion

Overview

This project builds a deep learning model that generates images from text descriptions using the Stable Diffusion model. Specifically, it utilizes the StableDiffusionPipeline from Hugging Face's Diffusers library with the pre-trained model dreamlike-art/dreamlike-photoreal-2.0 to produce high-quality photorealistic images.

Features

Convert textual descriptions into high-quality images

Utilize the dreamlike-art/dreamlike-photoreal-2.0 model for photorealistic results

Fine-tune generation parameters for optimal output

Save and visualize generated images

Technologies Used

Python

Hugging Face Diffusers

Transformers

PyTorch

PIL (Pillow) for image processing

Matplotlib for visualization

Installation

Clone the repository:

git clone https://github.com/yourusername/text-to-image-stablediffusion.git cd text-to-image-stablediffusion

Install dependencies:

pip install -r requirements.txt

Install Hugging Face Diffusers and PyTorch:

pip install diffusers transformers torch torchvision torchaudio

Model Usage

Load the pre-trained model:

from diffusers import StableDiffusionPipeline import torch

model_id = "dreamlike-art/dreamlike-photoreal-2.0" pipeline = StableDiffusionPipeline.from_pretrained(model_id).to("cuda" if torch.cuda.is_available() else "cpu")

Generate an image from text:

prompt = "A futuristic cityscape at sunset with flying cars" image = pipeline(prompt).images[0] image.show()

Save the generated image:

image.save("generated_image.png")

Future Improvements

Implement fine-tuning with custom datasets

Allow users to adjust generation parameters dynamically

Integrate with a web-based UI for easy text input and image generation

Deploy as an API for broader accessibility

License

This project is licensed under the MIT License.
