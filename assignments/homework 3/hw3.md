## Assignment - Tokenization Across Languages

**Your task:** Take one piece of text (~300 English words), translate it to **two other languages**, and analyze how each language gets split into tokens using the OpenAI tokenizer: [https://platform.openai.com/tokenizer](https://platform.openai.com/tokenizer)

### Requirements

1. **Pick text (English):**

   * Choose ~300 words of normal prose (article / blog / Wikipedia-style, not code or poetry).
   * Briefly say why you chose it (1–2 sentences).

2. **Translate:**

   * Translate that same text into **two non-English languages** of your choice.
   * Clean up the translations so they’re grammatical and keep the same meaning.

3. **Tokenize:**

   * For each version (English + Language A + Language B), paste the full text into the OpenAI tokenizer.
   * Record:

     * the list of tokens (the text pieces, not just the numbers),
     * total token count.

4. **Word-level stats:**
   In a notebook, for each language:

   * Compute:

     * % of words that are exactly **1 token**
     * % of words that are exactly **2 tokens**
     * % of words that are **3+ tokens**
     * average tokens per word
     * total words vs total tokens
       Store these in a small dict or table per language.

5. **Examples:**

   * Pick ~5 interesting words per language (common word, long/complex word, name, etc.).
   * Show how the tokenizer split them.
   * Briefly say if the split matches something meaningful (root + ending, pieces of a compound, etc.) or is nonsense.

6. **Chart:**

   * Make a simple matplotlib bar chart comparing the 3 languages on **average tokens per word** or some other stat from (4).
   * Label axes and add a short title.

7. **Mini write-up:**
   Add a short markdown section with:

   * what you observed in the numbers,
   * which language was “cheapest” in tokens and which was “expensive,”
   * why you think that happened (e.g. inflection, compounding, no spaces, etc.).

### Deliverables

* Notebook with:

  * the 3 texts,
  * tokens for each,
  * your stats code,
  * the chart,
  * 5 example words per language and comments,
  * your mini write-up.

### Deadline

* Submit by **Thursday, November 13, 2025 at 09:45** (start of class).

### Sending your submission

* Put your notebook at:  
  `**/assignments/homework 3/<your name>/<your name>.ipynb**`  
  (Replace `<your name>` with your actual name; keep folder structure.)
* Submit notebook by PR to the main course repo on GitHub. 
