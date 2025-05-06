## Configuration Variables
| variable name | value |
|---|---|
| device | `cpu` | 
| find_top_k | `3` | 
| policy_weight | `0.65` | 
| embedding_model | `nomic-embed-text` | 
| extracting_model | `deepseek-r1:8b` | 
 
 **prompt_template**: 
 ```
    You are an expert in policy analysis. Your task is to extract **form-related policies** from the document titled *Policies_Meridian.docx*.
    
    1. **Explicitly stated** — The policy is clearly and directly described in the text, with no ambiguity or need for interpretation.
    2. **Implicitly referenced** — The policy is not stated directly, but its presence can be **reasonably and confidently inferred** from specific procedures, requirements, or descriptions that **clearly align with the policy's core intent**.

    ❗ Do **not** infer based on vague, generic, or loosely related content.  
    ❗ If the policy is not clearly present or the reference is too indirect or speculative, treat it as not included.

    ---
    
    ### Document Content:
    Below is a selection of paragraphs extracted from *Policies_Meridian.docx*:
    
    ${combined_paragraphs}$
    
    ---

    ### Target Policy:
    - Policy of Interest: **"${policy_of_interest}$"**
    - Search Term Synonyms: **"${search_terms_synonym}$"**
    
    Use these keywords and any related concepts to locate relevant policies. 
    Remember to extract not just explicit mentions but also policies that are implied or embedded in procedures.
    Do **not** guess or make assumptions. Only mark a policy as found if there is **clear textual evidence**.
    
    ---
    
    ### Output Instructions:
    
    For **each policy instance** found, provide the following:

    1. **Y/N/M**:
    - `"Y"` - Clearly mentioned (explicitly and unambiguously stated).
    - `"M"` - Mentioned indirectly (implied, inferred, or part of a procedure).
    - `"N"` - The policy does not appear in the document in any clear or inferable form.
    ⛔ Do not guess. If unsure, default to `"N"`.

    2. **POLICY DETAILS**:
    - Copy the **exact original sentence(s)** that describe or imply the policy. If it’s implied, use only specific and logically tied text — no rewording. 
    - This is a highly sensitive policy detail extraction. **Do not paraphrase. Use the original sentence(s) from the document as much as possible**. 
    - If multiple sentences support the policy, return a **verbatim combination** of those sentences.

    ---
``` 
