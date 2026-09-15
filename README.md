# RAG-based-Enterprise-Knowledge-Base-Q-A-Assistant
# 1. Set up Python environment
 
I have already given you two setup files: `pyproject.toml` and `uv.lock`. In this case, you could use `uv` as the Python package manager.
 
If you do not have `uv` on your computer, you can download it from [this link](https://docs.astral.sh/uv/getting-started/installation/). After you click the link, you will go to the uv website. Scrolling down the page, you will see below the picture which asks you to select OS platform and download.
 
## Installation
 
Install `uv` with our official standalone installer:
 
**macOS and Linux**
 
```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```
 
**Windows**
 
```powershell
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
```
 
After installing `uv`, download all of my code in this repository. Then open the folder in VScode, type this command in terminal
 
```bash
uv sync
```
 
to install all of the python package.
# 2. Import API key
 
Create a `.env` file in the root of the project, and import the API key of the LLM you want to use.
 
For example, if you want to use OpenAI's models, create a `.env` file and add:
 
```bash
OPENAI_API_KEY=your_api_key_here
```
 
If you want to use another provider (such as Anthropic or DeepSeek), add the corresponding key instead:
 
```bash
ANTHROPIC_API_KEY=your_api_key_here
```
 
```bash
DEEPSEEK_API_KEY=your_api_key_here
```
 
Make sure the `.env` file is placed in the same directory as the project's config file, so that it can be loaded correctly when the program starts.

Readme setup en step3 · MD
# 3. Build the vector store
 
Run `ingest.py` to build the vector store.
 
```bash
uv run ingest.py
```
# 4. Evaluate model performance
 
Adjust the `chunk_size`, choose a suitable LLM, and modify the prompt as needed. Then run the following command:
 
```bash
uv run evaluator.py
```
# 5. Run the AI assistant
 
Once you are satisfied with these metrics, run the following command to launch the AI assistant.
 
```bash
uv run app.py
```
 
In addition, if you want to build a different AI assistant, you can replace the files under the `knowledge-base` folder and repeat steps 2, 3, and 4.
