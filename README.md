# NutriGuide: Your Personal AI Nutrition Agent

**A Capstone Project for the IBM SkillsBuild AICTE Internship - July 2025**
**Author:** Soumya Agnihotri

## 1. Overview

**NutriGuide** is an advanced AI-powered agent designed to function as a 24/7 personal nutritionist. It addresses the critical gap between generic, one-size-fits-all diet apps and the high cost and limited scalability of human nutritionists.

The agent delivers highly personalized, adaptive, and explainable dietary advice by considering an individual's unique health profile, including medical conditions, lifestyle, cultural preferences, and evolving fitness goals.

### The Problem

* **Generic diet apps** lack real-time personalization and fail to adapt to a user's changing needs.
* **Human nutritionists** provide excellent, tailored advice but cannot scale their services to a broad audience affordably.
* Users require **holistic plans** that account for their complete health picture, from allergies and health conditions to personal goals and daily food intake.

### The Solution

NutriGuide is engineered to think, learn, and advise like a human expert. It provides:

* **Deep Personalization:** Generates meal plans based on health goals (weight loss, muscle gain), medical conditions (diabetes, hypertension), dietary restrictions, and fitness routines.
* **Explainable AI:** Clearly explains its recommendations (e.g., "I suggest quinoa over white rice because its lower glycemic index will help maintain stable blood sugar levels.").
* **Dynamic Adaptation:** Continuously refines its advice through user feedback and future integrations with wearables.
* **Multimodal Interaction:** Understands user needs through natural language text queries.

## 2. System Architecture & Technology Stack

NutriGuide is built on the robust and scalable **IBM Cloud** platform, leveraging a suite of powerful AI and serverless technologies from **IBM Watsonx.ai**.

| Component                   | Technology                                   | Purpose                                                                                                             |
| --------------------------- | -------------------------------------------- | ------------------------------------------------------------------------------------------------------------------- |
| **AI Agent & Foundation Model** | **IBM Watsonx.ai Agent** with **Mistral-large** | Serves as the core intelligence, understanding user requests and generating human-like responses and meal plans.      |
| **LLM Orchestration** | **IBM Granite** | Manages the complex reasoning workflows, chaining prompts, and integrating data to generate coherent and context-aware advice. |
| **Dialog Management** | **IBM Watson Assistant** | Handles the conversational flow, managing user intents and entities to ensure a smooth, interactive text-based dialogue. |
| **Backend & Tool Integration**| **IBM Cloud Functions** | Provides the serverless backend logic for processing data and integrating external tools for real-time information retrieval. |
| **Data Storage** | **IBM Cloudant / Db2** | Securely stores user profiles, dietary preferences, meal plan history, and feedback data.                           |
| **External Tools** | **Google Search, DuckDuckGo, etc.** | The agent uses web crawling and search tools to fetch the latest nutritional information, recipes, and scientific data to support its recommendations. |

## 3. How It Works: Algorithm & Workflow

The agent follows a sophisticated, multi-step process to deliver its recommendations.

1.  **Input Processing:** The user's text query is ingested. **Watson Assistant** identifies the core intent (e.g., "request_meal_plan") and extracts key entities (e.g., "vegetarian," "weight loss").
2.  **Profile-Enhanced Prompting:** The system retrieves the user's profile from IBM Cloudant. This data is used to construct a detailed prompt template for the LLM.
3.  **Reasoning & Generation:** The prompt is sent to **IBM Granite**, which orchestrates the reasoning process. It instructs the **Mistral-large** model to generate a personalized meal plan that aligns with the user's profile and the extracted intent. If needed, IBM Cloud Functions trigger external searches to gather supplementary data.
4.  **Explanation Engine:** The agent generates not only the meal plan but also a clear, easy-to-understand explanation for its choices, leveraging both rule-based nutrient comparisons and LLM-powered summarization.
5.  **Feedback Loop:** The user's interactions and feedback are logged back to their profile, allowing the agent to learn and incrementally improve the quality of future recommendations.

## 4. Deployment

The agent is deployed on IBM Cloud, following these general steps:

1.  **Login** to an IBM Cloud account.
2.  Create a **Watsonx.ai sandbox project** and a new **AI Agent**.
3.  **Associate** the Watsonx Runtime service and select the **Mistral-large** model.
4.  **Integrate Tools** by adding Watson Assistant for dialogue and configuring IBM Cloud Functions for backend logic and web searches.
5.  **Build & Test** the agent within the Watsonx.ai environment.
6.  **Deploy** the agent to a new deployment space to generate an API key for integration into applications.

## 5. Future Scope

NutriGuide is a foundational platform with significant potential for growth. Future enhancements include:

* **Wearable Integration:** Automatically ingest fitness, sleep, and biometric data from wearables (e.g., Apple Watch, Fitbit) for hyper-personalized, real-time adjustments.
* **Grocery Shopping Assistant:** An in-app feature to scan product barcodes, analyze nutritional content, and suggest healthier alternatives on the spot.
* **Voice-Only Mode:** Enable hands-free interaction for users who are cooking or multitasking.
* **Reinforcement Learning (RL):** Implement RL from human feedback (RLHF) to optimize suggestions based on measured health outcomes and user satisfaction.
* **Multi-Language Support:** Expand the agent's capabilities to serve a diverse, global user base.
