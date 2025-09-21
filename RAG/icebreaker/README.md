# LinkedIn Icebreaker Bot

An AI-powered tool that generates personalized icebreakers and conversation starters based on LinkedIn profiles. This project uses IBM watsonx.ai and LlamaIndex to create a tool that helps make introductions more personal and engaging.

## Project Overview

Imagine you're heading to a big networking event, surrounded by potential employers and industry leaders. You want to make a great first impression, but you're struggling to come up with more than the usual, "What do you do?"

This AI icebreaker bot does the research for you. You input a name, and within seconds, the bot searches LinkedIn, generating personalized icebreakers based on someone's career highlights, interests, and even fun facts.

## Features

- Extract LinkedIn profile data using ProxyCurl API or mock data
- Process and index the data using LlamaIndex and IBM watsonx embeddings
- Generate interesting facts about a person's career or education
- Answer specific questions about the LinkedIn profile
- Interact with the bot through a command-line interface or a Gradio web UI

## Project Structure

```
icebreaker_bot/
├── requirements.txt           # Dependencies
├── config.py                  # Configuration settings
├── modules/
│   ├── __init__.py
│   ├── data_extraction.py     # LinkedIn profile data extraction
│   ├── data_processing.py     # Data splitting and indexing
│   ├── llm_interface.py       # LLM setup and interaction
│   └── query_engine.py        # Query processing and response generation
├── app.py                     # Gradio interface
└── main.py                    # Main script to run without Gradio
```

## Getting Started

### Prerequisites

- Python 3.11+
- A ProxyCurl API key (optional - you can use mock data)

### Installation

1. Clone the repository:
```bash
git clone https://github.com/HaileyTQuach/icebreaker.git
cd icebreaker
```

2. Create a virtual environment:
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. Install dependencies:
```bash
pip install -r requirements.txt
```

4. Add your ProxyCurl API key to `config.py` (optional)

### Usage

#### Command Line Interface

Run the bot using the command line:

```bash
python main.py --mock  # Use mock data
# OR
python main.py --url "https://www.linkedin.com/in/username/" --api-key "your-api-key"
```

#### Web Interface

Launch the Gradio web interface:

```bash
python app.py
```

Then open your browser to the URL shown in the terminal (typically http://127.0.0.1:7860).

## Development Tasks

This is a starter template with placeholder functions. Your task is to implement the following components:

1. In `config.py`:
   - Define the prompt templates for facts generation and question answering

2. In `modules/data_extraction.py`:
   - Implement the `extract_linkedin_profile` function

3. In `modules/data_processing.py`:
   - Implement the `split_profile_data` function
   - Implement the `create_vector_database` function
   - Implement the `verify_embeddings` function

4. In `modules/llm_interface.py`:
   - Implement the `create_watsonx_embedding` function
   - Implement the `create_watsonx_llm` function
   - Implement the `change_llm_model` function

5. In `modules/query_engine.py`:
   - Implement the `generate_initial_facts` function
   - Implement the `answer_user_query` function

6. Update `modules/__init__.py` to import your implemented functions

7. In `main.py`:
   - Implement the `process_linkedin` function
   - Implement the `chatbot_interface` function

8. In `app.py`:
   - Implement the `process_profile` function
   - Implement the `chat_with_profile` function

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgments

- IBM watsonx.ai for providing the LLM and embedding models
- LlamaIndex for the data indexing and retrieval framework
- ProxyCurl for LinkedIn profile data extraction