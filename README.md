[![Python](https://img.shields.io/badge/Python-3.11-blue?style=for-the-badge&logo=python)](https://www.python.org/downloads/release/python-3126/)
[![Dify](https://img.shields.io/badge/Dify-AI-green?style=for-the-badge&logo=openaigym)](https://dify.ai/)

## Table of Contents

- [Set Up](#set-up)
  - [set up python environment](#set-up-python-environment)
  - [set up ollama server locally](#set-up-ollama-server-locally)

## Set Up

### Set up python environment

- MacOS and Linux

    ```bash
        # create a virtual environment
        python3 -m venv venv

        # activate the virtual environment
        source venv/bin/activate

        # install the required packages
        pip install -r requirements.txt
    ```

- Windows

    ```bash
        # Create a virtual environment
        python -m venv venv

        # Activate the virtual environment
        venv\Scripts\activate

        # Install the required packages
        pip install -r requirements.txt
    ```


### Set up ollama server locally

- **Step1. Install Ollama**

  For macOS & Linux:
  <span style="opacity: 0.32">Runing the following command in your terminal:</span>

  ```shell
  curl -sSL https://ollama.ai/install.sh | bash
  ```

  For Windows: <br><br>
  <span style="opacity: 0.32">Go to </span>[Ollama's official website](https://ollama.com/) <span style="opacity: 0.32">and download the Windows installer (.exe file).</span>

- **Step2. Verify Installation**

  ```shell
  ollama
  ```

- **Step 3: Download a Model**
  <span style="opacity: 0.32">Ollama needs a model to run. Download a model like Deepseek, Llama 3, or others by running:</span>

  ```shell
  ollama run deepseek-r1:7b
  ```

  OR <span style="opacity: 0.32">directly run the model and ollama will check if the model is installed and download it if it's not:</span>

  ```shell
  ollama run deepseek-r1:7b
  ```

- **Step 4: 🎉 You're Done!**
  <span style="opacity: 0.32">Open Terminal 🖥️ and run the following command:</span>

  ```shell
  ollama serve
  ```

  OR <span style="opacity: 0.32">simply run the Ollama application.</span>
