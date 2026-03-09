# LLM Resume Tailoring + QA Prompts

This repository contains two prompts designed to help you **generate high-quality, ATS-optimized resumes** and **QA test them against job descriptions using LLMs**.

The system produces resumes that are:

- Truthful and grounded (no fabricated experience)
- Optimized for ATS keyword matching
- Easy for recruiters to skim
- Tailored to specific job descriptions

---

# Prompts Included

## 1. Resume Generation Prompt

Generates a **RenderCV YAML resume** tailored to a job description using a **base resume**.

### Features

- Prevents hallucinated experience
- Reorders and improves resume bullets
- Optimizes for ATS keywords
- Maintains recruiter readability
- Allows safe keyword bridging using **"Familiar With"**

### Inputs

```
JOB_DESCRIPTION
BASE_RESUME (RenderCV YAML)
```

### Output

```
Tailored RenderCV YAML resume
```

---

## 2. Resume QA / Smoke Test Prompt

Analyzes a generated resume and produces **structured diagnostic feedback**.

### What it evaluates

- Role alignment with the job description
- ATS keyword coverage
- Recruiter skimmability (3–5 second scan)
- Bullet clarity and impact
- Skills section structure
- Missing keywords

### Inputs

```
JOB_DESCRIPTION
GENERATED_RESUME
```

### Output

```
Structured improvement recommendations
```

The output is designed so another LLM can easily **apply improvements to the resume**.

---

# Recommended Workflow

1. Generate a tailored resume

```
ChatGPT → Resume Generation Prompt
```

2. QA test the resume

```
Gemini → Resume QA Prompt
```

3. Feed the QA feedback back into ChatGPT to refine the resume.

Repeat until satisfied.

---

# Example Pipeline

```
Base Resume (RenderCV YAML)
           +
Job Description
           ↓
Resume Generation Prompt
           ↓
Tailored Resume
           ↓
Resume QA Prompt
           ↓
Improvement Feedback
           ↓
Refined Resume
```

---

# Why This Approach Works

Most resume prompts fail because they:

- hallucinate experience
- over-optimize for keywords
- produce hard-to-skim resumes

This pipeline enforces:

- **grounded generation**
- **ATS keyword coverage**
- **recruiter readability**

---

# Notes

- Works with modern LLMs (ChatGPT, Gemini, Claude)
- Optimized for **RenderCV YAML resumes**
- Multiple iterations typically produce the best results

---

# License

Use freely and modify as needed.