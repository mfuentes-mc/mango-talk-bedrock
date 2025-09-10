# 🥭 Mango Talk: Exploring Amazon Bedrock

This repository contains the materials for the internal presentation "Exploring Amazon Bedrock: Capabilities and Use Cases". Its purpose is to serve as a practical resource for understanding and replicating the generative AI demonstrations performed with Amazon Bedrock.

## 🚀 What is Amazon Bedrock?

Amazon Bedrock is a fully managed service that provides access to high-performing Foundation Models (FMs) from various providers (Anthropic, Meta, Amazon, etc.) through a unified API. It allows you to build and scale generative AI applications securely and under control, without managing infrastructure.

## 🎯 Objective of this Repository

- To store prompts, system prompts, and configurations for the demos.
- To provide the document content for the Knowledge Bases (RAG) demonstrations.
- To serve as a starting point for experimenting with Bedrock.

## 📁 Repository Structure

├── README.md
├── 01_Playground_Demos/                # Chat and text generation demos
│   ├── ... (content for prompts and system prompts, for example)
└── 02_Knowledge_Bases_Demos/           # RAG demos (retrieving information from documents)
├── docs_for_s3/                    # PDF documents for the Knowledge Bases
│   ├── Guia_Arquitectura_Pagos.pdf
│   ├── Politica_Vacaciones_2024.pdf
│   └── Procedimiento_Deploy_Lambda.pdf
└── ... (specific prompts and configurations)


## 🛠️ Prerequisites

- AWS account with permissions for Amazon Bedrock and Amazon S3.
- Enabled access to Anthropic Claude 3 Sonnet in Amazon Bedrock (from "Model access").

## 🚀 How to Replicate the Demos

The demos are divided into two main sections:

### Part 1: Playground Demos (Text Generation)

1.  Navigate to the AWS console > Amazon Bedrock > Playgrounds > Chat.
2.  Select the **Anthropic Claude 3 Sonnet** model.
3.  The `system_prompt.txt` and `user_prompt.txt` for each example are located in `01_Playground_Demos/`. Copy and paste the content into the corresponding fields in the Playground.
4.  Adjust the **Temperature** and **Maximum output tokens** according to the instructions for each example.

### Part 2: Knowledge Bases Demos (RAG with Documents)

1.  **Prepare Documents:**
    - Create an S3 bucket.
    - Upload the PDFs from `02_Knowledge_Bases_Demos/docs_for_s3/` to this bucket.

2.  **Create Knowledge Base:**
    - Navigate to the AWS console > Amazon Bedrock > Knowledge bases.
    - Follow the wizard to create a new Knowledge Base, pointing to the S3 bucket where you uploaded the documents.
    - Make sure to sync the Knowledge Base once it is created.

3.  **Perform Query:**
    - Once the KB is synced (status: **Active**), click on it and go to the "Test" tab.
    - Select **Anthropic Claude 3 Sonnet** as the model.
    - The `user_prompt.txt` for this demo is located in `02_Knowledge_Bases_Demos/2.1_Internal_Docs_Expert/`. Copy and paste it.
    - The **Temperature** should be `0.0` and adjust **Maximum output tokens** to `2048`.
    - Click "Run" to see the response based on multiple documents.

---

Start experimenting and transforming the future with generative AI!