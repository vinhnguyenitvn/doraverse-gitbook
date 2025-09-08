---
icon: align-center
---

# AI Model Parameter

## **Temperature**

### **Purpose**

Controls the level of randomness in the model’s responses. A higher temperature makes the output more creative and varied, while a lower temperature generates deterministic and predictable responses.

### **How It Works**

At higher temperatures (e.g., 0.9), the model is more willing to explore less likely word combinations. At lower temperatures (e.g., 0.2), the model prioritizes the most probable tokens, leading to more conservative and straightforward answers.

### **Tips**

* **Set High Temperature (e.g 0.8–1.0)**: For brainstorming, generating poetry, or creating imaginative content where variety is desired.
* **Set Low Temperature (e.g 0.1–0.3)**: For tasks that require precision, such as answering factual questions or generating structured content like summaries.

***

## **Top\_p**

### **Purpose**

Controls the diversity of the model’s output by adjusting the range of token probabilities considered for each response.

### **How It Works**

Known as “nucleus sampling,” top\_p sets a cumulative probability threshold.&#x20;

For example, at top\_p=0.9, the model selects tokens from the smallest group of words whose combined probability equals 90%. Lowering top\_p restricts the model to using only the most probable tokens, reducing variability.

### **Tips**

* **Set High Top\_p (0.9–1.0)**: For creative and conversational tasks where a natural flow and variation are essential.
* **Set Low Top\_p (0.1–0.3)**: When consistency and focus are more critical, such as when generating technical instructions.

**Note:** When both `temperature` and `top_p` are set, the model uses both to sample tokens. It’s often best to tune only one at a time.

***

## **Max Tokens**

### **Purpose**

Sets the limit on the number of tokens (words, punctuation, or parts of words) in the model’s response. One token is roughly 4 characters or ¾ of a word in English.

### **How It Works**

This parameter ensures the response doesn’t exceed a specific length. Shorter limits are helpful for concise outputs, while more extended limits allow for detailed responses.

### Tips

* **Set Short Max Tokens (10–50)**: Generating taglines, headlines, or single-sentence outputs.
* **Set Long Max Tokens (100–500)**: For detailed explanations, long-form content, or summaries.

***

## **Frequency Penalty**

### **Purpose**

Penalizes repeated words or phrases within the response, encouraging more varied language.

### **How It Works**

A higher frequency penalty reduces the likelihood of the model reusing the same tokens multiple times, which can help make responses more engaging and dynamic.

### Tips

* **Set Higher Frequency Penalty (0.5–2.0)**: When you want varied phrasing or generate creative content like stories or marketing copy.
* **Set Lower Frequency Penalty (0.0–0.3)**: When repetition is acceptable or even desirable, such as when emphasizing a key point.

***

## **Presence Penalty**

### **Purpose**

Encourages or discourages the introduction of new ideas or topics in the response. A higher presence penalty increases the likelihood of the model exploring new concepts.

### **How It Works**

When this parameter is increased, the model is less likely to stay anchored to familiar topics or phrases, promoting more exploratory or innovative responses.

### Tips

* **Set Higher Presence Penalty (0.5–2.0)**: For brainstorming sessions or creative outputs where novelty and diversity are prioritized.
* **Set Lower Presence Penalty (0.0–0.3)**: For tasks that require sticking to a specific topic or reinforcing a central idea.

***

## **Max Context Tokens**

### **Purpose**

Defines the maximum number of tokens that can be processed in a single request, including both the input (prompt) and the output (response).

### **How It Works**

This value represents the model’s context window — the total number of tokens it can “remember” or reference in one interaction.&#x20;

For example:

* GPT-4.1: up to **1,047,576 tokens**
* Gemini 2.5 Pro: up to **1 million token**

The model uses this space for:

* Your prompt + Chat history
* Function call definitions
* System instructions
* And the model’s own reply

If this limit is exceeded, the API will return an error or truncate the context.

### **Tips**

* You don’t need to manually set this parameter, it’s managed by the system.
* Useful mostly for developers managing long conversations or documents.
* For long-form tasks (e.g. document Q\&A, summarization), ensure your inputs + expected output stay within the token limit.

***

## **Max Output Tokens**

### **Purpose**

Specifies the maximum length of the model’s response, in tokens.

### **How It Works**

This parameter limits how long the model can continue generating text. One token ≈ 4 characters in English or roughly ¾ of a word.

If the model hits this limit, it **stops immediately**, even mid-sentence.

#### **Tips**

* Short (10–50): For taglines, bullet points, quick summaries.
* Medium (100–300): Balanced responses like paragraphs or Q\&A.
* Long (500+): For stories, essays, or detailed explanations.
* Increase only if you're not getting enough detail in responses.

***

## **Stop Sequences**

### **Purpose**

Defines one or more strings that tell the model when to stop generating text.

### **How It Works**

If the model generates any of the specified sequences, it immediately halts its output — even if it hasn't reached the max token count.

Common examples:

* `"\\n\\n"` (double line break)
* `"User:"` (to stop at next prompt)
* `"###"` (used to separate sections)

### **Tips**

* Use this when formatting outputs, e.g., to stop after a list or prevent spillover.
* Multiple stop sequences can be provided, each as a separate string.
* Only advanced users or developers typically need to modify this.

***

## **Reasoning Effort**

### **Purpose**

Controls how deeply the model "thinks" when generating a response — higher effort encourages more deliberate, thoughtful answers.

### **How It Works**

This parameter is for OpenAI's o-series model only.

Higher values may slightly slow down responses, but often improve quality in tasks that require logic or explanation. Reducing reasoning effort can result in faster responses and fewer tokens used on reasoning in a response.

#### **Tips**

* Use **low/medium** for fast, general replies.
* Set to **high** when asking for:
  * Step-by-step explanations
  * Math or code reasoning
  * Analytical tasks or structured writing

***

## **Image Detail**

### **Purpose**

Controls how thoroughly the model analyzes image inputs.

### **How It Works**

* `low`: Faster, lighter scan of image content
* `high`: Deep inspection, useful for charts, documents, detailed images
* `auto`: Smart default — chooses based on image type and query complexity

### **Tips**

* Use `low` for casual screenshots or UI buttons.
* Use `high` for analyzing dense content like tables, diagrams, PDFs.
* `auto` is optimal for most use cases and balances speed with detail.

***

## **Resend Files**

Toggles whether previously uploaded files should be reprocessed or re-included when regenerating or retrying a response.

### **Tips**

* Leave ON if your request depends on file content (e.g. “summarize this PDF”).
* Toggle OFF if you're iterating only on prompt phrasing and don’t want delays.

***

## Best Practices for Parameter Adjustment <a href="#heading-best-practices-for-parameter-adjustment" id="heading-best-practices-for-parameter-adjustment"></a>

**Experimentation:** The best way to understand the impact of different parameters is through experimentation. Try various settings to see how they affect the responses.

**Balance:** Strive for a balance between creativity and coherence. Extreme values in some parameters can lead to less meaningful outputs.

**Context Awareness:** Consider the context and purpose of your agent application when adjusting parameters. Different scenarios may require different settings for optimal results.
