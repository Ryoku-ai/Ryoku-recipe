# Ryoku API: Your Personal AI Language Tutor

Welcome to the home of the **Ryoku API**. Ryoku is a next-generation, specialized AI tutor designed to accelerate learning for developers, students, and lifelong learners.

Developed by **OSAMAH**, the **Ryoku Gen 1** model is not just another chatbot. It's a purpose-built educational tool, engineered to provide intuitive, expert-level instruction across a vast spectrum of human and programming languages.

---

## 🚀 Live Demo & Interactive Documentation

Experience the power of Ryoku firsthand. Our interactive documentation provides a live demo and all the information you need to integrate Ryoku into your applications.

**[Explore the Ryoku API Documentation](https://ryoku-tutor-api.onrender.com/doc)**

*(Remember to replace `your-render-url` with your actual service URL)*

---

## ✨ Why Ryoku? The Developer's Advantage

Ryoku was built to solve a common problem: the need for instant, context-aware, and reliable educational support. Here’s how it benefits developers:

-   **Expert On-Demand:** Integrate a 24/7 AI tutor directly into your learning platforms, coding environments, or applications. Provide immediate help to your users without building a complex system from scratch.
-   **High-Quality Instruction:** Ryoku's core is fine-tuned for teaching. It excels at breaking down complex topics, providing clear examples, and maintaining a patient, encouraging tone.
-   **Broad Subject Mastery:**
    -   **Programming:** Get expert help with syntax, algorithms, debugging, and best practices in languages like Python, JavaScript, Java, C#, and more.
    -   **Human Languages:** Learn grammar, vocabulary, and cultural nuances for languages like English, Spanish, Japanese, Arabic, and beyond.
-   **Fast & Responsive:** The API is optimized for low-latency responses, making it suitable for real-time applications like interactive chat and live coding assistants.
-   **Simple & Scalable:** With a clean, RESTful design, integrating Ryoku is incredibly straightforward. The infrastructure is built to handle growing user demand.

---

## 🛠️ Core Capabilities

| Feature                  | Description                                                                                                                                |
| ------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------ |
| **Custom Identity**      | A unique AI persona, **Ryoku Gen 1**, developed by OSAMAH, ensuring a consistent and professional user experience.                           |
| **Adaptive Pedagogy**    | Automatically adjusts its teaching style for technical concepts versus linguistic subtleties, providing more effective instruction.          |
| **Contextual Awareness** | Understands the flow of a conversation to provide relevant follow-up explanations and answers.                                             |
| **Code Generation**      | Provides clear, commented, and executable code snippets to illustrate programming concepts.                                                |
| **Language Translation** | Offers accurate translations and explains the grammatical reasoning behind them.                                                           |

---

## 🔌 Quick Start: API Usage

Integrating Ryoku is as simple as a single POST request.

**Endpoint:** `POST /chat`

**Request Body:**
```json
{
  "user_id": "a_unique_identifier_for_your_user",
  "new_message": "How do I create a class in Python?"
}

**Example (Python):**
```python
import requests
import json
...


# Replace with your actual API URL
API_URL = "https://ryoku-tutor-api.onrender.com/chat"

def ask_ryoku(message, user_id="demo-user-123"):
    payload = {
        "user_id": user_id,
        "new_message": message
    }
    headers = {"Content-Type": "application/json"}
    
    try:
        response = requests.post(API_URL, data=json.dumps(payload), headers=headers)
        response.raise_for_status() # Raises an exception for bad status codes
        
        # The answer from Ryoku
        answer = response.json()["answer"]
        print(f"Ryoku: {answer}")
        
    except requests.exceptions.RequestException as e:
        print(f"An error occurred: {e}")

# Ask Ryoku a question
ask_ryoku("Explain what an API is in simple terms.")
