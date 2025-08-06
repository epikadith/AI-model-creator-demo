# AI-model-creator-demo
This Python code is a simplified, autonomous AI research system that mimics the ASI-ARCH framework to design, test, and analyze neural network architectures. It uses a three-agent system to continuously improve a model without human intervention.

This Python code is a simplified, autonomous AI research system that mimics the **ASI-ARCH framework** to design, test, and analyze neural network architectures. It uses a three-agent system to continuously improve a model without human intervention.

***

### **How the Code Works**

1.  **Researcher (Design)**: This agent, powered by the **`gemini-2.5-pro`** model, generates new neural network architectures in Python code. It uses a structured prompt that includes the code from the previous iteration and an analysis report from the **Analyst**. Its primary goal is to produce runnable, syntactically correct code, with a specific focus on fixing any errors identified in past experiments.

2.  **Engineer (Test)**: This agent takes the code from the Researcher and attempts to train and evaluate the model. Instead of a mock training environment, this version uses **TensorFlow** to load the MNIST dataset, compile the model, and train it for one epoch. It then evaluates the model's performance on a test set, returning real metrics like `loss` and `accuracy`. It is also designed to catch and report any errors that occur during code execution or training.

3.  **Analyst (Analyze)**: This agent, using the **`gemini-2.5-flash`** model, analyzes the performance metrics and the code from the Engineer. It's programmed to specifically look for errors. If an error is found, it generates a detailed, actionable report with line-by-line suggestions on how to fix the code. If the code runs successfully, it provides a high-level analysis of the model's performance to guide the next design iteration.

This closed-loop system is designed to be **self-correcting**: an error in one iteration leads to specific, actionable feedback in the next, allowing the AI to learn and improve its code generation capabilities over time. The entire process is orchestrated in a `main` function that runs for a set number of iterations, demonstrating the iterative nature of AI research.


### Note
The code here was generated using gemini.
To run the code, an API key for an LLM must be added to the colab environment, or can be hardcoded into the notebook directly (unsafe)
