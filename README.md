# Google ADK OpenAI Agent

A minimal Google Agent Development Kit (ADK) agent configured to use OpenAI's
`gpt-4o` model through LiteLLM.

## Requirements

- Python 3.10 or newer
- An OpenAI API key

## Setup

From the repository root, create and activate a virtual environment, then
install the dependencies:

```bash
python -m venv .venv
source .venv/bin/activate
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
```

On Windows PowerShell, activate the environment with:

```powershell
.venv\Scripts\Activate.ps1
```

Create the agent's environment file and add your API key:

```bash
cp agent1/.env.example agent1/.env
```

Edit `agent1/.env` and set `OPENAI_API_KEY`. Never commit this file or put real
credentials in `.env.example`.

## Run

Run the agent in the terminal:

```bash
adk run agent1
```

Or launch the ADK web interface:

```bash
adk web
```

Then open the local URL printed by the command and select `agent1`.

## Configuration

The agent configuration is in [`agent1/agent.py`](agent1/agent.py). It uses
`openai/gpt-4o`, a temperature of `0.3`, and a maximum output length of 800
tokens. Update the `LiteLlm` model string to use another LiteLLM-supported
provider or model, and set that provider's credentials in `agent1/.env`.

`GOOGLE_API_KEY` is included in the example environment file for optional
Google model configurations; the current OpenAI model uses `OPENAI_API_KEY`.
