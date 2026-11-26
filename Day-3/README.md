# LangChain Restaurant Assistant

A conversational restaurant assistant built with **LangChain** and **Groq**. It answers menu questions, recommends dishes, remembers recent conversation context, runs simple CSV-based checks, and demonstrates a LangChain agent.

## Features

- Answers menu and price questions using the sample menu in the system prompt.
- Recommends vegetarian and non-vegetarian dishes based on customer preferences.
- Maintains conversation history during the session.
- Responds in friendly English or Telugu, matching the customer.
- Includes a simple CSV test runner.
- Demonstrates `create_agent` with no external tools.

## Technologies

- Python
- LangChain
- `langchain-groq`
- Groq API
- Pandas
- Google Colab

## Setup and Run

1. Open `Langchain_Restaurant_Assistant.ipynb` in Google Colab.
2. In Colab, open **Secrets** (key icon in the left sidebar).
3. Add a secret named `GROQ_API_KEY` and paste your Groq API key as its value.
4. Enable notebook access to that secret.
5. Run the notebook cells from top to bottom.

The notebook installs `langchain` and `langchain-groq` in its first cell.

## Sample Menu

| Item | Sample price |
|---|---:|
| Veg Biryani | Rs. 180 |
| Paneer Butter Masala | Rs. 220 |
| Chicken Biryani | Rs. 240 |
| Masala Dosa | Rs. 80 |
| Veg Fried Rice | Rs. 150 |
| Chicken Noodles | Rs. 190 |
| Gulab Jamun | Rs. 60 |
| Fresh Lime Soda | Rs. 50 |

These are demonstration menu values defined in the notebook. Update the `SYSTEM` prompt to match the restaurant's actual menu and prices before using it.

## Main Components

- `SYSTEM`: Defines the restaurant assistant's role, menu facts, and response rules.
- `prompt`: Combines the system prompt, conversation history, and current question.
- `chain`: Runs the prompt through the Groq model and converts the response to text.
- `ask(question)`: Sends a question and stores the conversation in `history`.
- `run_tests(path)`: Reads test questions from a CSV file and checks for required phrases.
- `agent_order`: Demonstrates creating and invoking a LangChain agent.

## Example Questions

- "Can you recommend a vegetarian dish?"
- "What is the price of Veg Biryani?"
- "I prefer spicy food. What do you recommend?"
- "Do you have takeaway?"

## Important Limitations

- The menu and prices are sample information stored in the prompt.
- The notebook does not connect to live inventory, a POS system, delivery tracking, or payment services.
- It cannot actually place orders or reservations.
- The CSV checks are basic phrase checks; model responses can vary, so test results may not always be deterministic.
- Allergy and ingredient information must be confirmed with restaurant staff.

## Customization

Edit the `SYSTEM` variable to change the restaurant name, menu, prices, available services, and response rules. For real deployment, connect trusted restaurant data and authenticated order-management tools rather than relying on prompt text alone.
