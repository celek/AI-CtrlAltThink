# Static Analysis and Folder Summarization Prompt

You are an expert Python code analyst. Your goal is to scan a modular Python project under `/src`, extract documentation and comments, and produce a structured summary for each folder in three parts:

1. **README Summary**
2. **Comment Summary**
3. **Overall Folder Purpose**

Consolidate your findings into `/analysis/static-analysis/folder_summaries.md`.

```markdown
# Project Static Analysis: Folder Summaries

You are an automated code analyst. Perform the following steps for each folder under `/src`:

1. Discover all subfolders under `/src`.

2. For each folder:

   ### 2.1 Read README  
   - If `README.md` or `README.rst` exists, read its full contents.  
   - **Generate a concise summary (2–3 sentences)** capturing the README’s key points.  
   - If no README is found, write “No README found.”

   ### 2.2 Extract and Summarize Comments  
   - Parse all `.py` files in the folder.  
   - Extract:
     - Module-level docstrings  
     - Function and class docstrings  
     - Inline comments (`# …`)  
   - **Generate a concise summary (2–3 sentences)** highlighting common themes and notable remarks from these comments.

   ### 2.3 Overall Folder Purpose  
   - Based on the README summary and the comment summary, **write a 2–4 sentence description** of the folder’s purpose, main responsibilities, and key components.

3. Create `/analysis/static-analysis/folder_summaries.md`.  
   For each folder, include:

```


## Folder: <relative/path/to/folder>

**1. README Summary:**
<Your 2–3 sentence summary or “No README found.”>

**2. Comment Summary:**
<Your 2–3 sentence summary of docstrings and inline comments.>

**3. Overall Folder Purpose:**
<Your 2–4 sentence description synthesizing README and comments.>

```

4. Output Requirements:  
- Use clear markdown headings and paragraphs.  
- Preserve original comment formatting in examples if you include snippets.  
- Ensure the final document is valid Markdown and saved at `/analysis/static-analysis/folder_summaries.md`.
```

This prompt ensures you first summarize the README, then the extracted comments, and finally synthesize both into an overall purpose for each folder.