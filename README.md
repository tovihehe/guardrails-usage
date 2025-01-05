# Guardrails framework 🧱
Guardrails is a Python framework designed to build reliable AI applications by performing two critical functions:

1. **Input/Output Guarding**: Detecting, quantifying, and mitigating specific risks in inputs to and outputs from large language models (LLMs) or agents.
2. **Structured Data Generation**: Enabling the generation of structured and reliable data from LLMs or agents.

Guardrails utilizes pre-built measures called **validators** to check for various types of risks. These validators are combined into **Input Guards** and **Output Guards** that ensure the safety and reliability of AI models.

### Features
- **Guardrails Hub**: A collection of pre-built validators for different types of risks, such as toxic language, profanity, and sensitive data exposure.
- **Customizable Actions**: Define actions (e.g., fixing or rejecting responses) when a validation fails.
- **Seamless Integration**: Works with raw LLM outputs and can be easily added to your AI applications.

## Installation and Setup

To set up Guardrails and the necessary hubs, follow these steps:

### Step 1: Install Guardrails
```bash
pip install guardrails-ai
```

### Step 2: Configure Guardrails
Run the following command to configure Guardrails:
```bash
guardrails configure
```
Add your **Guardrails API Key** and **OpenAI API Key** to a `.env` file.

### Step 3: Install Required Hubs and Dependencies
Install specific hubs and dependencies required for validations:

```bash
# Install Guardrails hubs
!guardrails hub install hub://guardrails/profanity_free --quiet
!guardrails hub install hub://guardrails/toxic_language --quiet
!guardrails hub install hub://guardrails/secrets_present --quiet

# Install additional dependencies
pip install presidio-analyzer presidio-anonymizer -q
python -m spacy download en_core_web_lg -q

# Install additional hubs for specific use cases
!guardrails hub install hub://guardrails/detect_pii --quiet
!guardrails hub install hub://tryolabs/restricttotopic --quiet
```

## Usage Example

### Purpose of the Code
The provided code demonstrates the application of Guardrails to ensure that outputs/inputs from LLMs and agents are:
- Free from toxic or profane language.
- Secure from exposure of sensitive information (e.g., secrets, API keys).
- Free of personally identifiable information (PII).
- Relevant to the defined topic.

![image](https://github.com/user-attachments/assets/525135bd-6580-4f60-8143-747921ec5512)

## Resources used
- [Guardrails Documentation]([https://docs.guardrails.ai/](https://github.com/guardrails-ai/guardrails)
- [Guardrails Hub](https://hub.guardrailsai.com/)

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.


