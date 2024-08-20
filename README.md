# AI-Powered Image Generation and Captioning

This project leverages the power of Stable Diffusion and BLIP to generate images from textual prompts and provide insightful captions for the generated images.

## Features

* **Image Generation:** Uses Stable Diffusion to create images based on your textual descriptions.
* **Image Captioning:** Employs BLIP to generate meaningful captions that describe the generated images.
* **Interactive Interface:** Provides a user-friendly Gradio interface for seamless interaction.

## Requirements

* Python 3.x
* Libraries:
    * `diffusers`
    * `transformers`
    * `accelerate`
    * `gradio`
    * `torch`

Install the required libraries using:

```bash
pip install diffusers transformers accelerate gradio torch
pip install git+[https://github.com/salesforce/BLIP](https://github.com/salesforce/BLIP) # Latest BLIP version
```

## Usage

1. **Clone the repository:**

   ```bash
   git clone [https://github.com/](https://github.com/)<your-username>/<your-repository-name>.git
   ```

2. **Navigate to the project directory:**

   ```bash
   cd <your-repository-name>
   ```

3. **Run the application:**

   ```bash
   python app.py 
   ```

4. **Access the Gradio interface:**

   * Open your web browser and go to the URL displayed in the terminal (usually `http://127.0.0.1:7860/`).

5. **Generate and analyze:**

   * Enter a descriptive prompt in the textbox.
   * Click the "Generate" button.
   * The application will generate an image based on your prompt and display it along with a generated caption.

## Examples

* **Prompt:** "A majestic castle perched on a cliff overlooking the ocean at sunset."
* **Prompt:** "A photorealistic image of a cat wearing a tiny hat."
* **Prompt:** "A vibrant abstract painting with swirling colors and bold lines."

## Notes

* Ensure you have a CUDA-enabled GPU for optimal performance.
* Experiment with different prompts to explore the capabilities of the models.
* The quality of the generated images and captions may vary depending on the complexity of the prompt.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

