<h1 align="center">
  <img src="images/agent_s.png" alt="Logo" style="vertical-align:middle" width="60"> Agent S:<br>
  An Open Agentic Framework that Uses Computers Like a Human
</h1>

<p align="center">
  🌐<a href="https://www.simular.ai/agent-s">[Website]</a>
  📄<a href="https://arxiv.org/abs/2410.08164">[Paper]</a>
  🎥<a href="https://www.youtube.com/watch?v=OBDE3Knte0g">[Video]</a>
</p>

## 💡 Introduction

<p align="center">
    <img src="./images/teaser.png" width="800">
</p>

<p>
Welcome to **Agent S**, an open-source framework designed to enable autonomous interaction with computers through a Graphical User Interface (GUI). Our mission is to build intelligent agents that can learn from past experiences and perform complex tasks autonomously on your computer. 

Whether you're interested in AI, automation, or contributing to cutting-edge agent-based systems, we're excited to have you here!
</p>

## 🎯 Current Results

<p align="center">
    <img src="./images/results.png" width="600">
    <br>
    Results of Successful Rate (%) on the OSWorld full test set of all 369 test examples using Image + Accessibility Tree input.
</p>


## 🛠️ Installation

Clone the epository
```
git clone https://github.com/simular-ai/Agent-S.git
```

We recommend using Anaconda or Miniconda to create a virtual environment and install the required dependencies. We used Python 3.9 for development and experiments.
```
conda create -n agent_s python=3.9
conda activate agent_s
```

Install the agent_s package and dependencies
```
pip install -e .
```

Set your LLM API Keys and other environment variables. You can do this by adding the following lines to your .bashrc (Linux), or .zshrc (MacOS) file. We support OpenAI, Azure OpenAI, Anthropic, and vLLM models.

1. OpenAI
```
export OPENAI_API_KEY=<YOUR_API_KEY>
```
2. Anthropic
```
export ANTHROPIC_API_KEY=<YOUR_API_KEY>
```
3. OpenAI on Azure
```
export AZURE_OPENAI_API_BASE=<DEPLOYMENT_NAME>
export AZURE_OPENAI_API_KEY=<YOUR_API_KEY>
```
4. vLLM for Local Models
```
export vLLM_ENDPOINT_URL=<YOUR_DEPLOYMENT_URL>
```

### Setup Retrieval from Web using Perplexica

1. Ensure Docker is installed and running on your system.
2. Clone the Perplexica repository:

   ```bash
   git clone https://github.com/ItzCrazyKns/Perplexica.git
   ```

3. After cloning, navigate to the directory containing the project files.

4. Rename the `sample.config.toml` file to `config.toml`. For Docker setups, you need only fill in the following fields:

   - `OPENAI`: Your OpenAI API key. **You only need to fill this if you wish to use OpenAI's models**.
   - `OLLAMA`: Your Ollama API URL. You should enter it as `http://host.docker.internal:PORT_NUMBER`. If you installed Ollama on port 11434, use `http://host.docker.internal:11434`. For other ports, adjust accordingly. **You need to fill this if you wish to use Ollama's models instead of OpenAI's**.
   - `GROQ`: Your Groq API key. **You only need to fill this if you wish to use Groq's hosted models**.
   - `ANTHROPIC`: Your Anthropic API key. **You only need to fill this if you wish to use Anthropic models**.

     **Note**: You can change these after starting Perplexica from the settings dialog.

   - `SIMILARITY_MEASURE`: The similarity measure to use (This is filled by default; you can leave it as is if you are unsure about it.)

5. Ensure you are in the directory containing the `docker-compose.yaml` file and execute:

   ```bash
   docker compose up -d
   ```
For a more detailed setup and usage guide, refer to the [Perplexica Repository](https://github.com/ItzCrazyKns/Perplexica.git)

### Setup Paddle-OCR Server

Run the ocr_server.py file code to use OCR-based bounding boxes.

```
cd agent_s
python ocr_server.py
```

Switch to a new terminal where you will run Agent S. Set the OCR_SERVER_ADDRESS environment variable as shown below. For a better experience, add the following line directly to your .bashrc (Linux), or .zshrc (MacOS) file.

```
export OCR_SERVER_ADDRESS=http://localhost:8000/ocr/
```

You can change the server address by editing the address in [agent_s/ocr_server.py](agent_s/ocr_server.py) file

## 🚀 Usage

### OSWorld

To deploy Agent S in OSWorld, follow the [OSWorld Deployment instructions](OSWorld.md).

### WindowsAgentArena

To deploy Agent S in WindowsAgentArena, follow the [WindowsAgentArena Deployment instructions](WindowsAgentArena.md).

### Run Locally on your Own Computer

We support running Agent S directly on your own system through [OpenACI](https://github.com/simular-ai/OpenACI). To run Agent S on your own system run: 
```
python examples/cli_app.py --model <MODEL>
```
This will show a user query prompt where you can enter your query and interact with Agent S. 

NOTE: We currently support running Agent-S on local system only for MacOS and Ubuntu through OpenACI. 

## 🙌 Contributors

We’re grateful to all the amazing people who have contributed to this project. Thank you! 🙏  
[Contributors List](https://github.com/simular-ai/Agent-S/graphs/contributors)

## 💬 Citation
```
@misc{agashe2024agentsopenagentic,
      title={Agent S: An Open Agentic Framework that Uses Computers Like a Human}, 
      author={Saaket Agashe and Jiuzhou Han and Shuyu Gan and Jiachen Yang and Ang Li and Xin Eric Wang},
      year={2024},
      eprint={2410.08164},
      archivePrefix={arXiv},
      primaryClass={cs.AI},
      url={https://arxiv.org/abs/2410.08164}, 
}
```

