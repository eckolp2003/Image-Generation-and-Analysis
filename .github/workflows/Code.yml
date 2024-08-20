!pip install diffusers transformers accelerate gradio torch
!pip install git+https://github.com/salesforce/BLIP # Latest BLIP version

import torch
from diffusers import StableDiffusionPipeline
from transformers import BlipProcessor, BlipForConditionalGeneration
from PIL import Image
import gradio as gr

# Load Models
pipe = StableDiffusionPipeline.from_pretrained("stabilityai/stable-diffusion-2-1-base", torch_dtype=torch.float16)
pipe = pipe.to("cuda")

processor = BlipProcessor.from_pretrained("Salesforce/blip-image-captioning-large")
model = BlipForConditionalGeneration.from_pretrained("Salesforce/blip-image-captioning-large")

# Define Generation and Analysis Functions
def generate_and_analyze(prompt):
    image = pipe(prompt).images[0]

    # Use BLIP for image captioning
    inputs = processor(image, return_tensors="pt")
    out = model.generate(**inputs)
    caption = processor.decode(out[0], skip_special_tokens=True)

    return image, caption

# Create Gradio Interface
with gr.Blocks() as demo:
    gr.Markdown("## Image Generation and Analysis")

    with gr.Row():
        with gr.Column():
            prompt_input = gr.Textbox(label="Enter your prompt")
            generate_button = gr.Button("Generate")
        with gr.Column():
            image_output = gr.Image(label="Generated Image")
            caption_output = gr.Textbox(label="Image Caption")

    generate_button.click(fn=generate_and_analyze, inputs=prompt_input, outputs=[image_output, caption_output])

demo.launch(debug=True)
