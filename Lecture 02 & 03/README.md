### ✨ PIAIC Lecture 2 and 3: Sunday Session Recap by Warda Rehman

Welcome to theclass of **PIAIC (Presidential Initiative for Artificial Intelligence and Computing)**, held at **Sindh Boy Scouts Association**. This class is designed to introduce you to **Google's Gemini 2.0 Flash model, APIs, SDKs, and Prompt Engineering**. Throughout this session, we will explore how AI-powered chatbots work, how to integrate AI models into applications, and the fundamental differences between APIs and SDKs.

In this lecture we will go through key concepts such as **Google Generative AI Python SDK, stateful vs. stateless chats, tokens, and temperature settings in AI models**. By the end of this class, we will have a solid understanding of how AI-powered chatbots function and how to integrate AI into real-world applications.

---


### 1️⃣ Introduction to the Experimental Gemini 2.0 Flash Model 🚀

#### **What is Gemini 2.0 Flash?**
Gemini 2.0 Flash is an **experimental AI model** by Google, accessible through the **[Gemini Developer API](https://ai.google.dev/)** and **Google AI Studio**. This model is an enhancement over its predecessors, featuring **faster response times, improved accuracy, and multimodal capabilities** (processing text, images, and audio in real-time).

#### 🔑 **Key Features:**
- **Multimodal API:** Supports **real-time text, vision, and audio interactions**. 👁️🔊
- **Enhanced Speed:** Generates responses faster, reducing latency. ⚡️
- **Superior Quality:** Outperforms previous Gemini versions in processing efficiency. 🏆
- **Agentic Capabilities:** Excels in handling **images, audio, and code generation** tasks. 💻💬
- **New Modalities:** Supports **image generation and text-to-speech conversion**. 🖼️🎙️

---

### 2️⃣ Understanding APIs and GUIs 🔌🖥️

#### **What is an API (Application Programming Interface)?**
An API serves as a communication bridge between different software applications. It allows applications to interact with external services without exposing the underlying code.

| **Feature** | **Description** |
|------------|----------------|
| **Function** | Enables interaction between software systems. |
| **Access** | Remote, without requiring a local install. |
| **Example** | Requesting AI-generated text from Gemini API. |

📌 **Further Reading:** Learn more about **APIs** [here](https://www.ibm.com/cloud/learn/api).

#### **What is a GUI (Graphical User Interface)?**
A GUI is a visual interface that allows users to interact with applications using buttons, icons, and menus.

| **Feature** | **Description** |
|------------|----------------|
| **Function** | Provides a user-friendly frontend for software. |
| **Example** | Google AI Studio for testing AI models. |

📌 **Further Reading:** Learn about the **differences between API and GUI** [here](https://www.geeksforgeeks.org/difference-between-api-and-gui/).

---

### 3️⃣ SDK vs. API 🛠️ vs. 🔌  

An **API (Application Programming Interface)** acts as a bridge that allows different software applications to communicate with each other. It provides predefined rules and endpoints for sending and receiving data between systems without needing to understand the internal workings of the service.  

An **SDK (Software Development Kit)** is a collection of tools, libraries, documentation, and code samples that developers use to build applications for a specific platform or framework. SDKs often include APIs, but they also provide additional utilities like compilers, debugging tools, and sample code to accelerate development.  

#### 🔍 **Comparison Chart: SDK vs. API**  

| Feature          | API 🌐 | SDK 🛠️ |
|-----------------|--------|---------|
| **Definition**   | A set of rules that allow communication between software applications. | A toolkit containing libraries, documentation, and utilities for building applications. |
| **Purpose**      | Enables interaction with external services or data sources. | Provides everything needed to develop applications for a specific platform. |
| **Components**   | Endpoints, request methods, response formats. | Libraries, documentation, code samples, debugging tools. |
| **Ease of Use**  | Requires implementation using programming languages. | Provides built-in functionalities to simplify development. |
| **Integration**  | Used to integrate third-party services (e.g., Google Maps API, Gemini API). | Used to build applications from scratch with built-in functionalities. |
| **Examples**     | REST APIs, GraphQL APIs, Gemini API. | Android SDK, iOS SDK, Google Cloud SDK. |


---

### 4️⃣ Steps for Effective Prompt Engineering 🤖💬

1️⃣ **Instruction:** Clearly state the task for the AI model.  
2️⃣ **Context:** Provide necessary background information.  
3️⃣ **Input Data:** Supply text, images, or structured data.  
4️⃣ **Output Format:** Specify how the response should be structured.  

📌 **Further Reading:** Learn more about **Prompt Engineering** [here](https://www.promptingguide.ai/).

---

### 5️⃣ Using Google Generative AI Python SDK in Google Colab 🐍☁️

The **Google Generative AI SDK** enables easy integration of AI models into development workflows.

**Installation:**
```python
!pip install -U -q "google-generativeai>=0.7.2"
```
**Importing SDK:**
```python
import google.generativeai as genai
```
**Setting up API Key:**
* Get your **API key** from **Google AI Studio** and configure it:
```python
genai.configure(api_key="YOUR_API_KEY")
```
---

### 6️⃣ Working with Gemini Models 🌌

**Example: Using Gemini 1.5 Flash**
```python
model = genai.GenerativeModel('gemini-1.5-flash')
response = model.generate_content("Give me python code to sort a list")
print(response.text)
```
### 📜 Inspecting the Response

When working with the Gemini model, it's useful to analyze the response structure.

- `response.candidates`: Displays the raw outputs generated by the model. 
- `response.usage_metadata.candidates_token_count`: Indicates the number of tokens used in the response. 

---

### 7️⃣ Loading Images in Google Colab for Image Recognition 🔍

To perform image recognition using the Gemini model, follow these steps:

1️⃣ **Download an Image**: Use `wget` or `curl` to fetch an image from an external URL and store it locally.  

2️⃣ **Load the Image**: Utilize the Python Imaging Library (PIL) to open and display the image.  

```python
# Downloading an image from a URL
!wget -O sample_image.jpg "https://example.com/sample.jpg"

# Importing necessary libraries
from PIL import Image

# Loading and displaying the image
image = Image.open("sample_image.jpg")
image.show()
```

3️⃣ **Image Recognition with Gemini**:

You can utilize the Gemini model for image recognition by passing an image as input and requesting a description or object identification.  

- The model processes the image and returns insights about its contents.  
- Responses can be generated in **JSON format** or other structured formats based on your needs. 📊  

### 8️⃣ Stateless vs. Stateful Chat 💬
**Stateless Mode**
Each interaction is independent, meaning the model does not retain previous conversation history. ⚡
Ideal for single-question responses where context is not required.
Example: Asking a general question without referring to previous exchanges.

**Stateful Mode**
The model remembers past interactions, enabling a seamless, ongoing conversation. 📜💭
Useful for multi-turn dialogues, where context from earlier messages improves responses.
Example: Having a back-and-forth conversation where the model recalls previous queries.

**Checking Chat History:**
To review the stored conversation in stateful mode, use the following command:

```python
print(chat.history)
```
### 9️⃣ Tokens and Temperature 🔥

#### **Tokens**  
Tokens represent individual units of text processed by the model while generating responses. 🧾  
- The number of tokens used affects **response length** and **computational cost**. 💰  
- Limiting token usage helps manage API consumption efficiently.  

#### **Temperature**  
The **temperature setting** determines how creative or deterministic the AI’s responses will be:  
- **Low Temperature (e.g., 0.2 - 0.4)** → Produces **consistent and focused** outputs. 🎯  
- **High Temperature (e.g., 0.8 - 1.2)** → Generates **more diverse and imaginative** responses. 🎨  

---

### 🔟 OpenAI API (Not Currently in Use)  

During our discussion, we explored the **OpenAI API** options, including **ChatGPT and GPT-4**.  
- Although OpenAI provides powerful AI models, **it is not free**, making it unsuitable for our course.  
- For this reason, we are currently using **Google's Gemini API**, which offers similar capabilities without cost constraints. 💡  


---

### Final Task: Complete the “Hello World” of Gemini 👋🌍

#### **Objective:**
Gain hands-on experience with the Gemini model by writing a simple prompt, generating a response, and analyzing the output.

#### **Task:**
1️⃣ Write a basic prompt and pass it to Gemini API.  
2️⃣ Generate a response and analyze the output format.  
3️⃣ Modify the **temperature and token settings** to observe changes.  
4️⃣ Integrate an **image input** and request a textual description from the model.  
5️⃣ Share your insights in the next class discussion.  

#### **Code for Task:**
```python
import google.generativeai as genai

genai.configure(api_key="YOUR_API_KEY")

model = genai.GenerativeModel('gemini-1.5-flash')
prompt = "Hello, Gemini! Tell me a fun fact about AI."
response = model.generate_content(prompt)
print(response.text)
```

---

## Wrap-Up

In this class, we explored **Gemini 2.0 Flash, APIs, SDKs, prompt engineering, and AI integration**. Understanding these concepts will help you build AI-powered applications and optimize chatbot performance.

**🚀Empower yourself with AI, learn, innovate, and create the future! 🌟**



