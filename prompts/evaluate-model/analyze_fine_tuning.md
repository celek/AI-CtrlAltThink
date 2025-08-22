You are an expert AI diagnostician specializing in the fine-tuning of Large Language Models. Your mission is to analyze model failures, identify root causes, and provide actionable, evidence-based recommendations for improvement.

You will be provided with an "evidence locker" containing a series of `(Prompt, Ground-Truth Answer, Model's Bad Answer)` triplets from an SFT model's evaluation run.

Your task is to perform the following five steps:

1.  **Individual Error Analysis:** For each triplet in the evidence locker, meticulously analyze the model's failure. Classify each error into one or more of the following categories and provide a brief justification for your classification:
    *   **Formatting & Style:** The model produced correct content but in the wrong structure (e.g., list instead of JSON).
    *   **Instruction Following:** The model ignored a constraint or a part of a multi-step instruction.
    *   **Reasoning & Logic:** The model failed to perform a valid logical or mathematical operation on the facts provided.
    *   **Factual Hallucination:** The model generated a factually incorrect statement.
    *   **Refusal / Safety Overkill:** The model refused to answer a benign prompt.
    *   **Verbosity / Terseness:** The model's output was significantly longer or shorter than desired.

2.  **Aggregate Diagnosis:** After analyzing all individual errors, create a summary table that quantifies the error distribution (e.g., Reasoning: 60%, Formatting: 30%, Factual: 10%). Identify the dominant error patterns.

3.  **Actionable Recommendations:** Based on your diagnosis, provide a prioritized list of concrete actions the development team should take. Your recommendations must be specific.
    *   If the issue is **data quality**, suggest specific types of new examples to add (e.g., "Add 200 more examples of multi-turn dialogues that require the model to maintain context across turns.").
    *   If the issue is **reasoning**, recommend specific strategies like fine-tuning with Chain-of-Thought (CoT) examples and provide a sample of what a good CoT training instance would look like for this use case.
    *   If the issue is **hyperparameters**, explain which parameters to investigate (e.g., "The consistent verbosity suggests the temperature or repetition penalty might be miscalibrated. Consider running a sweep...").

4.  **Suggest Further Diagnostics:** Recommend one or two additional tests to confirm your hypothesis. For example, "To confirm the reasoning deficit, test the model on the GSM8K benchmark to get a quantitative score of its mathematical reasoning capabilities."

5.  **Cite Your Sources:** Conclude with a list of relevant academic papers and guides that support your analysis, focusing on error analysis and teaching reasoning.

---
**INPUT: Evidence Locker**

[
{
"prompt": "I have 3 apples and my friend gives me 5 more. I then eat 2 apples. How many apples do I have left? Respond with only the final number.",
"ground_truth": "6",
"model_answer": "You have 8 apples before you eat any, and after eating 2, you have 6 left. So the answer is 6."
},
{
"prompt": "Provide user details for user_id 123 in JSON format with keys 'name' and 'email'.",
"ground_truth": "{"name": "John Doe", "email": "john.doe@example.com"}",
"model_answer": "- Name: John Doe\n- Email: john.doe@example.com"
},
{
"prompt": "A is heavier than B. C is lighter than B. Is A heavier than C? Answer with only 'Yes' or 'No'.",
"ground_truth": "Yes",
"model_answer": "It is not possible to determine from the information given."
}
]

text
---
**END OF PROMPT**

### Literature on the "Error Detective" Process

Here is a curated list of resources that delve into the theory and practice of analyzing model errors and teaching reasoning.

**Foundational Guides on Fine-Tuning and Evaluation:**
*   **Fine-Tuning Large Language Models: A Comprehensive Guide** (Solwey, 2024) [11]: Provides a modern overview of the entire fine-tuning process, including sections on preparing data and evaluating model performance, which are prerequisites for error analysis.
*   **What is fine-tuning? A guide to fine-tuning LLMs** (Cohere, 2025) [1]: A clear, high-level guide that explains the "why" and "how" of fine-tuning, setting the context for why error analysis is a critical step in the iterative loop of model improvement.
*   **A comprehensive overview of everything I know about fine-tuning** (Reddit, 2025) [2]: A detailed, practical guide from the community that often includes hands-on tips and tricks for debugging common fine-tuning problems that aren't covered in academic papers.

**Advanced Papers on Error Analysis and Reasoning:**
*   **Training LLMs to Better Self-Debug and Explain Code** (ArXiv, 2024) [3]: While focused on code, this paper's methods are broadly applicable. It explores how models can be trained to identify their own errors and explain their reasoning, which is the goal of a robust SFT process. The techniques for teaching "self-debugging" are a form of advanced error analysis.
*   **Teaching language models to reason algorithmically** (Google Research, 2024) [18]: This work focuses specifically on teaching reasoning. It discusses methods that go beyond simple SFT, exploring how to train models to follow algorithmic processes, which is essential for overcoming logical errors identified during analysis.
*   **Reinforcement Learning Meets Chain-of-Thought: Transforming LLMs into Autonomous Reasoning Agents** (Unite.AI, 2025) [20]: This article explains the synergy between SFT with Chain-of-Thought (to teach the format of reasoning) and RL (to refine the quality of reasoning). This is the next step after your error analysis identifies a reasoning deficit.
*   **Improving Machine Learning Models: A Guide to Error Classification & Analysis** (Dataheroes, 2024) [4]: A practical guide on the methodology of error analysis itself. It provides structured ways to classify and analyze model mistakes to find actionable insights, which is the core of the "detective" process.