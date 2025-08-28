Name- Shubh Modi
Email - 21cs01073@iitbbs.ac.in

# Empathetic Code Reviewer  

## Overview  
This project was built during a hackathon with the mission to transform raw, critical code review comments into **empathetic, constructive, and educational feedback**.  

The tool takes a code snippet and direct review comments, and generates a **Markdown report** with:  
- A **Positive Rephrasing** of the comment.  
- The **Why** (software principle behind the suggestion).  
- A **Suggested Improvement** with example code.  
- References to **external resources** (like PEP 8 and complexity docs).  
- A **Holistic Summary** wrapping everything up in an encouraging tone.  

The result feels less harsh and more like mentorship, bridging the gap between juniors and seniors in a team.  

---

## Setup & Installation  

1. **Clone / Unzip the Project**  
   Extract the files or clone the repo into your working directory.  

2. **Install Dependencies**  
   ```bash
   pip install -r requirements.txt
   ```

3. **Set Groq API_KEY at the start of the file**  
   - To use **Groq LLM (Llama 3)** for real AI-generated feedback, set your API key:  
 

4. **Run the Program**  
   ```bash
   python script.py sample_input.json output_report.md
   ```

   - `sample_input.json` → input with code snippet + review comments.  
   - `output_report.md` → generated empathetic review in Markdown.  

5. **Open the Report**  
   Check `output_report.md` in any Markdown viewer (e.g., VS Code, GitHub preview, or a browser extension).  

---

## Why Each Step Was Needed  

- **LangChain + HuggingFace Embeddings**  
  Even though embeddings are optional here, including them showcases **expandability** — the system could later link feedback to relevant documentation or internal company knowledge bases.   

- **Groq Llama 3 Integration**  
  This adds the “AI-powered empathy”. Without it, feedback would just be templated. The Groq integration shows how the tone adapts **contextually** based on severity.  

- **Local Template Fallback**  
  Hackathon demos often face API or network limits. The fallback ensures the tool **always works** and produces usable output, even offline.  

- **External References (PEP8, Time Complexity)**  
  These links strengthen the educational aspect, making feedback actionable rather than vague.  

- **Holistic Summary**  
  This ensures the final report ends positively, encouraging the developer instead of overwhelming them with raw criticism.  

---

## Example Output (Excerpt)  

```
### Analysis of Comment: "Variable 'u' is a bad name."
* **Positive Rephrasing:** Nice idea — here's a small suggestion to improve this area for clarity and maintainability.  
* **The 'Why':** Meaningful variable names improve readability and make maintenance easier.  
* **Suggested Improvement:**  
```python
def get_active_users(users):
    return [user for user in users if user.is_active and user.profile_complete]
```  
* **Reference:** https://peps.python.org/pep-0008/
```

---
