## Assignment – LLM-Powered Classification on a Small Dataset

**Your task:** Choose (or create on your own) **any small dataset (~20 rows)** and build a **text classification** pipeline using an LLM (via OpenRouter).
You must define **at least 3 labels** (e.g., `positive/neutral/negative`, or `joy/sadness/anger/fear/neutral`, or topics like `sports/politics/tech`, etc.).
**Upload both your code and the labeled data.** **Do NOT include any API keys.**

---

### Requirements

1. **Pick or create a dataset (~20 rows)**

   * Source options (pick one):

     * A tiny CSV you create (e.g., product reviews, tweets, headlines, bug reports).
     * A small slice of a public dataset (manually copy ~20 examples).
   * The dataset must have at least one **text** column (e.g., `text` or `review`).
   * Save as CSV (UTF-8), e.g., `data.csv` with header `text`.

2. **Define your label set (≥3 classes)**

   * Examples:

     * Sentiment: `positive`, `neutral`, `negative`
     * Emotion: `joy`, `sadness`, `anger`, `fear`, `surprise`, `neutral`
     * Topic: `sports`, `politics`, `technology`, `entertainment`
   * Add a short **label guide** (1–2 lines per label) explaining what belongs in each class.

3. **Prompt design**

   * Write a **system prompt** that sets clear rules and the **output schema**. You can also add a few examples for better clarity.
   * Require **strict JSON** output, no extra text.
   * Example schema (edit keys/labels for your task):

     ```json
     { "label": "positive|neutral|negative" }
     ```
   * Also instruct the model to **only** choose one of your allowed labels.

4. **API calls (OpenRouter + MiniMax M2: free (or any other model if you like))**

   * Use the **OpenAI-compatible client** with OpenRouter:
   * Loop over your ~20 rows, call the LLM **one row at a time**, and store the result in a new column (e.g., `label`).
   * You can use `tqdm` for a simple progress bar.
   * **If the response is not valid JSON or not in your allowed set, write `"error"` (no retries).**

5. **Data handling & output**

   * Read your CSV with pandas, keep your full ~20 rows.
   * Add the new `label` column with your predictions.
   * Save to `labeled.csv` (same order as input).
   * Display the final DataFrame.

6. **Basic sanity checks**

   * Print label counts (value counts) and the **% of `error`** responses.
   * If you have an obvious class imbalance, mention it.

7. **Mini analysis (5–8 sentences)**

   * What patterns did you notice?
   * Were any classes hard to separate?
   * How often did you get `error`? Why might that happen?
   * One concrete idea to improve reliability next time (e.g., clearer schema, shorter inputs, examples, or light pre-processing).
   * Chart with label distribution.

8. **Reproducibility & safety**

   * **Do NOT commit API keys.** Use `OPENROUTER_API_KEY` via environment variables or delete value before committing.
   * Add a short **README** explaining:

     * Your label set and label guide.
     * How to run your notebook (including installing `openai`, `pandas`, `tqdm`).
     * 
---

### Deliverables

* **Notebook** (`.ipynb`) with:

  * Your label guide (markdown).
  * The API-call loop with JSON parsing and error handling.
  * The final DataFrame display.
  * Label counts, mini analysis, and chart.
* **Data files**:

  * `data.csv` (original ~20 rows, with a `text` column).
  * `labeled.csv` (same rows, plus `label` column).
* **README.md** with run instructions and your label definitions.

> **REMINDER:** Do **not** include any API keys in the notebook, data, or README. Use environment variables and keep secrets out of version control.

--- 

### Deadline

Submit by **Thursday, November 20, 2025 at 09:45** (start of class).

---

### Sending your submission

Put your files at:
**`/assignments/homework 4/<your name>/<your name>.ipynb`**
Include in the same folder: `data.csv`, `labeled.csv`, and `README.md`.
Submit via PR to the main course GitHub repo.

---

Good luck and remember: **no API keys in the repo**.
