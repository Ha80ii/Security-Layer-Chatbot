# **🛡️ Prompt Safety Classifier**

A lightweight system designed to detect unsafe prompts using a combination of two machine learning models:

   -  Logistic Regression (TF-IDF)

   -  BiLSTM deep learning model

This project provides a Streamlit-based interface where users can enter any prompt, and the system automatically determines whether it is **SAFE** or **UNSAFE** before allowing it to reach an LLM.


**🔐 System Behavior:**

- **✔️ SAFE Prompt:**

  - If the input is classified as SAFE, the system:

  - Sends the prompt to an LLM (through OpenRouter API)

  -  Returns the generated response to the user

- **❌ UNSAFE Prompt:**

  - If the input is classified as UNSAFE, the system:

  - Blocks the prompt

  - Prevents it from reaching the LLM

  - Displays a warning message to the user

- **This ensures protection from:**
  
   🚫 Harmful instructions

   🚫 Violence or exploitation queries
 
   🚫 Criminal activity
 
   🚫 Sensitive content
 
   🚫 Self-harm or harm to others



**🧠 How It Works:**

- User enters a prompt in the Streamlit app.

- The prompt is processed by both models in models.py.

- Each model returns:

     Label (SAFE / UNSAFE)

     Confidence score

- A merging function computes the final decision.

- Depending on the result:

     SAFE → sent to the LLM

     UNSAFE → blocked
