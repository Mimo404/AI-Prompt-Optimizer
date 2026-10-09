# 🚀 AI Prompt Optimizer

### Tips Hindawi Internship — August–October 2026

🎓 This project was developed during the [Tips Hindawi](https://www.tipshindawi.com/) Internship (August–October 2026) as part of the Large Language Models (LLMs) Training Program at [Edrak for AI](https://edrak4ai.com/en).

---

## 👤 Participant

| Field            | Value                                   |
| ---------------- | --------------------------------------- |
| Full Name        | Mahmoud Ali Abdullah                    |
| Project Name     | AI Prompt Optimizer                     |
| GitHub Username  | Mimo404                                 |
| Internship Batch | August–October 2026                     |
| Training Program | Large Language Models (LLMs) Program    |
| Organization     | [Edrak for AI](https://edrak4ai.com/en) |

---

## 📖 Project Overview

The **AI Prompt Optimizer** is an AI-powered application that transforms simple, vague prompts into clearer, more structured, and more effective instructions for large language models (LLMs).

Writing effective prompts can be challenging, especially for users who are unfamiliar with prompt engineering. This project aims to simplify that process by allowing users to enter a basic instruction and receive an improved version organized into clearly defined components.

The application uses **Mistral Nemo Instruct 2407** to generate optimized prompts and **Retrieval-Augmented Generation (RAG)** to retrieve relevant examples of professional prompts. These examples are converted into vector embeddings using Sentence Transformers and stored in a FAISS index for semantic similarity search.

The application also uses LangChain for prompt templating and structured output parsing, FastAPI for the backend, and Streamlit for the interactive user interface.

### 🎯 Project Goal

To make prompt engineering more accessible by helping users transform basic instructions into well-structured prompts without requiring advanced prompt-writing skills.

---

## ✨ Features

* **AI-Powered Prompt Optimization:** Uses Mistral Nemo to rewrite simple prompts into clearer, more detailed instructions.
* **Retrieval-Augmented Generation (RAG):** Retrieves relevant prompt examples to guide the generation process.
* **Semantic Search:** Uses Sentence Transformers and FAISS to find prompt examples based on semantic similarity.
* **Structured Output:** Organizes the generated result into five components:

  * Improved Prompt
  * Role
  * Context
  * Constraints
  * Expected Output
* **RAG Toggle:** Allows users to enable or disable reference retrieval.
* **Interactive Web Interface:** Provides a user-friendly interface built with Streamlit.
* **REST API:** Uses FastAPI to expose the prompt optimization functionality.
* **JSON Response:** Returns the optimized prompt and its components in a structured format.
* **Output Validation and Retry:** Attempts to parse the generated response and retries when the expected JSON format cannot be extracted or parsed.

---

## 🛠️ Technologies Used

| Technology                 | Purpose                                                             |
| -------------------------- | ------------------------------------------------------------------- |
| Python                     | Main programming language                                           |
| PyTorch                    | Model inference                                                     |
| Mistral Nemo Instruct 2407 | Large language model for prompt optimization                        |
| Hugging Face Transformers  | Loading the language model and generating text                      |
| Hugging Face Datasets      | Loading the prompt dataset                                          |
| Sentence Transformers      | Generating semantic embeddings                                      |
| FAISS                      | Vector indexing and similarity search                               |
| LangChain                  | Prompt templates and structured output parsing                      |
| FastAPI                    | Backend API                                                         |
| Pydantic                   | API request validation                                              |
| Streamlit                  | Interactive web interface                                           |
| Uvicorn                    | Running the FastAPI application                                     |
| ngrok                      | Exposing the application through a public URL during demonstrations |
| Kaggle                     | Development and execution environment                               |

### 📚 Models and Dataset

**Language Model**

[Mistral Nemo Instruct 2407](https://huggingface.co/mistralai/Mistral-Nemo-Instruct-2407)

Used to generate improved prompts from user input.

**Prompt Dataset**

[fka/prompts.chat](https://huggingface.co/datasets/fka/prompts.chat)

Used as a source of reference prompts. The implementation filters the dataset to use text-based examples.

**Embedding Model**

`sentence-transformers/all-MiniLM-L6-v2`

Used to convert reference prompts and user queries into vector embeddings for semantic similarity search.

---

## ⚙️ Installation

### Prerequisites

* A [Kaggle](https://www.kaggle.com/) account.
* An internet connection to download the required models and dataset.
* Access to the required Kaggle notebook resources.

**Note:** Mistral Nemo is a relatively large language model. This project was developed using Kaggle as the execution environment.

### 1. Open the Notebook

Open the project notebook in Kaggle or upload it to your Kaggle environment.

### 2. Install Dependencies

Run the notebook cells that install the required Python packages.

### 3. Configure ngrok (Optional)

To expose the Streamlit application through a public URL, configure an ngrok authentication token using Kaggle Secrets.

Store your token as a secret named `NGROK_TOKEN`. Never include your actual token in the notebook or GitHub repository.

### 4. Run the Application

Execute the notebook cells in order to:

1. Load the Mistral Nemo language model.
2. Initialize the prompt dataset, embeddings, and FAISS index.
3. Start the FastAPI backend.
4. Launch the Streamlit interface.
5. Create the ngrok tunnel if you want public access.

Once the tunnel is established, open the generated URL to access the application.

**Note:** The public URL is temporary, and the application is accessible only while the relevant processes and execution environment remain active.

## 🚀 Usage

1. Launch the Streamlit application.
2. Enter a prompt in the input field.
3. Choose whether to enable RAG.
4. Click **Optimize Prompt**.
5. Wait for the model to process your input.
6. Review the improved prompt and its structured components.
7. Expand the JSON section to inspect the complete response.

### 💡 Example

**Input Prompt**

```text
Explain AI
```

**Example of an Improved Prompt**

```text
You are a patient teacher. Explain artificial intelligence
to [AUDIENCE] in simple language.

Use [NUMBER] everyday examples and avoid technical jargon.

Structure the answer as:
1. A short introduction
2. Key points
3. A brief summary
```

This example illustrates the intended output style. The actual response may vary between runs.

### 📋 Output Structure

The application generates a structured result containing the following fields:

| Field             | Description                                          |
| ----------------- | ---------------------------------------------------- |
| `improved_prompt` | The complete rewritten prompt                        |
| `role`            | The role the AI should adopt                         |
| `context`         | Background information and audience details          |
| `constraints`     | Rules governing tone, length, and other requirements |
| `expected_output` | The expected format and structure of the response    |

---

## 📸 Demo

Watch the AI Prompt Optimizer in action!

🎥 **Live Demo:** [Watch the project demonstration on LinkedIn](https://lnkd.in/p/gYPrkrdP)


---

## 📈 Results

The project demonstrates an end-to-end prompt optimization workflow combining a large language model, Retrieval-Augmented Generation (RAG), semantic search, structured output parsing, and an interactive web interface.

The application accepts a user's prompt and generates an improved version with a defined role, context, constraints, and expected output.

Users can also enable or disable RAG to explore prompt optimization with or without retrieved reference examples.

Formal quantitative evaluations of prompt quality and retrieval performance remain future work.


## 🔮 Future Improvements

* **Prompt Quality Evaluation:** Develop an evaluation framework to measure the quality and usefulness of optimized prompts.
* **RAG Evaluation:** Compare the quality of generated prompts with and without retrieved references.
* **Improved Retrieval:** Experiment with retrieval thresholds, the number of references, and alternative embedding models.
* **Prompt History:** Allow users to review and reuse previous optimizations.
* **Export Functionality:** Add options to copy or download optimized prompts.
* **Error Handling:** Improve feedback for generation failures, invalid model outputs, and API connection issues.
* **Performance Optimization:** Explore quantization and other inference optimizations to reduce memory usage.
* **Deployment:** Host the application in an environment capable of running the model so that users can access it without manually starting a Kaggle session.

---

## 📚 About the Internship

This project was developed as part of the [Tips Hindawi](https://www.tipshindawi.com/) Internship (August–October 2026), within the Large Language Models (LLMs) Training Program at [Edrak for AI](https://edrak4ai.com/en).

Tips Hindawi is the internships department of Edrak for AI. The internship encourages participants to build practical projects, apply their technical skills, and showcase their work through GitHub.

For more information about the internship, training programs, and upcoming batches, visit the [official Tips Hindawi website](https://www.tipshindawi.com/).

---

## 📄 License

This project is shared for educational and portfolio purposes.

No formal open-source license has been specified yet. Please check the internship's requirements and the licenses of the project's dependencies and datasets before distributing or reusing the project.

---
