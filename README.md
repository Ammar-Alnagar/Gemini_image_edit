# Gemini for Image Editing with Gradio

This Gradio application leverages the Gemini API to perform image editing tasks based on text prompts.  It allows you to upload an image and provide a text instruction (prompt) to modify the image.

## Features

*   **Image Editing with Gemini:** Utilizes the Google Gemini API for image editing capabilities.
*   **User-Friendly Interface:**  Built with Gradio for a simple and intuitive web interface.
*   **Image and Text Output:**  Returns the modified image (if successful) or a text response from the Gemini API.
*   **API Key Configuration:** Allows users to configure their own Gemini API key for enhanced reliability and control.
*   **Usage Instructions:** Provides clear instructions on how to use the application.
*   **Example Prompts:** Offers pre-defined examples to quickly demonstrate the application's capabilities.
*   **Custom CSS:** Enhances the visual appearance with custom CSS styles.
*   **Image Format:** Input limited to PNG images only.



## Get an API Key

[https://aistudio.google.com/apikey](https://aistudio.google.com/apikey)

## Installation

To run this application locally, follow these steps:

1.  **Clone the repository:**

    ```bash
    git clone <repository_url> #Replace <repository_url> with url of the repo
    cd <repository_directory> # Navigate into project
    ```

2.  **Install dependencies:**

    ```bash
    pip install -r requirements.txt
    ```
    Create a `requirements.txt` file and include the following libraries:
    ```txt
        gradio
        pillow
        google-generativeai
    ```

3.  **Set up your Gemini API key:**

    *   Obtain a Gemini API key from [https://aistudio.google.com/apikey](https://aistudio.google.com/apikey).
    *   Set the `GEMINI_API_KEY` environment variable or enter it directly in the Gradio interface.

## Usage

1.  **Run the Gradio application:**

    ```bash
    python your_script_name.py # Replace with the python file to run
    ```

2.  **Access the web interface:**
    Open your web browser and navigate to the address provided by Gradio (usually `http://localhost:7860`).

3.  **Use the application:**

    *   Upload an image in PNG format using the "Upload Image" component.
    *   Enter a text prompt in the "Prompt" textbox describing the desired image modification.
    *   Optionally, enter your Gemini API key in the "Gemini API Key" textbox. If left blank, the application will attempt to use the `GEMINI_API_KEY` environment variable.
    *   Click the "Generate" button.

4.  **View the output:**

    *   If the Gemini API successfully generates a modified image, it will be displayed in the "Generated Outputs" gallery.
    *   If the API returns a text response instead of an image, the text will be displayed in the "Gemini Output" textbox.

## Important Notes

*   **API Key Required:**  A valid Gemini API key is required for the application to function correctly.
*   **PNG Image Format:** The application only accepts images in PNG format.
*   **NSFW Content:**  Do not upload or use prompts that involve NSFW (Not Safe For Work) content.
*   **Image or Text Response:** The Gemini API may return either a modified image or a text response depending on the prompt and the model's capabilities. If a text response is received, it will be displayed in the "Gemini Output" textbox.
*   **Configuration Issues:** Sometimes the model returns text instead of image due to API configurations and model selection.

## Interface Details

*   **Header:**  Displays the application title, links to the Gemini logo, Gradio, repository duplication, API key acquisition, and the author's Twitter.
*   **API Configuration Accordion:** Provides instructions on how to configure the Gemini API key.
*   **Usage Instructions Accordion:**  Outlines the steps to use the application, including input image format and NSFW content restrictions.
*   **Image Input:**  Allows users to upload a PNG image for editing.
*   **API Key Input:**  Enables users to enter their Gemini API key.
*   **Prompt Input:**  Provides a textbox for users to enter the text prompt for image modification.
*   **Generate Button:** Triggers the image editing process.
*   **Output Gallery:**  Displays the generated image output.
*   **Output Textbox:**  Shows the text response from the Gemini API, if no image is generated.
*   **Examples Grid:**  Offers a set of example images and prompts to demonstrate the application's features.

## Code Explanation

*   **`generate(text, file_name, api_key, model)`:** This function interacts with the Gemini API to generate image or text output based on the provided text prompt and image file.
*   **`process_image_and_prompt(composite_pil, prompt, gemini_api_key)`:** This function processes the image and prompt, calls the `generate` function, and handles the output (either an image or text).
*   **Gradio Interface:** The `with gr.Blocks() as demo:` block defines the structure and functionality of the Gradio web interface.

