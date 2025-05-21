# Snap and Ask – A RAG-Powered HR Assistant Built on IBM watsonx.ai

## 1. Overview

Snap and Ask is a simulated Retrieval-Augmented Generation (RAG) assistant built around the capabilities of IBM watsonx.ai — IBM’s enterprise-grade platform offering AI solutions, foundation models, generative AI, and tools for enterprise innovation and business needs.

This use case demonstrates how watsonx.ai can power a multimodal assistant for HR teams and employees by enabling intelligent question-answering based on visual inputs like payslips, offer letters, or internal HR portal screenshots. The assistant uses Optical Character Recognition (OCR) to extract text from the image, retrieves relevant information from a curated HR document base using similarity search, and generates grounded, natural-language responses using IBM’s foundation models (e.g., Granite family models).

This project reflects IBM's broader vision for trustworthy, explainable AI in enterprise workflows. It draws from IBM's documented emphasis on retrieval-augmented generation, document understanding, and responsible AI integration — repurposed here to solve a real-world challenge faced by HR teams: helping employees interpret policy-heavy documents with minimal manual intervention.

While this is a simulated implementation, it is conceptually designed to align with IBM’s product architecture and strategy, showcasing watsonx.ai’s potential in multimodal enterprise applications beyond text-only interactions.

> ✳️ Note: This is a simulated project created as part of a technical writing portfolio to demonstrate conceptual understanding, product alignment, and technical documentation skills using IBM watsonx.ai capabilities.

The sections that follow detail the architecture, sample data flow, prompt construction, simulated outputs, and how this assistant aligns with IBM’s mission to scale trustworthy AI in the workplace.

## 2. Use Case Context

In large organizations, employees frequently encounter HR-related documents that are dense, complex, and difficult to interpret. These include:

- Digital or scanned payslips  
- Offer letters with tax-related clauses  
- Internal portal screenshots (e.g., dashboards showing deduction codes, bonus breakdowns, leave status)  
- Policy notices or announcements shared as images via email, Slack, or WhatsApp  

Despite increased digitization of HR operations, many employees still rely on human HR support to understand basic document content and decode ambiguous terms — often leading to high support loads and poor employee experience. Common questions include:

- “What does this TDS Code mean on my payslip?”  
- “Why is my take-home salary lower this month?”  
- “Which clause applies to this deduction?”  

Snap and Ask addresses these issues by offering a retrieval-augmented, AI-powered interface where employees can upload images of documents, ask free-form questions, and receive grounded, policy-aware explanations.  

It uses Optical Character Recognition (OCR) to extract key terms from images, retrieves relevant information from internal HR policy repositories or portals, and generates a clear, personalized answer using a foundation model like Granite on watsonx.ai.

---

### 📌 Example Scenario: “Why Is ₹2,000 Deducted from My Salary?”

Let’s say an employee uploads a screenshot of their payslip and asks:  
> “Why is ₹2,000 less credited to my account this month?”

Snap and Ask processes the image and query by:

1. Extracting key text from the image — including deduction codes, amounts, and dates  
2. Searching for matching HR policies (e.g., “Clause 4.1 – Half-day salary deduction for unapproved leave”)  
3. Pulling relevant data from the company’s HR portal such as:
   - Leave balance and attendance logs  
   - Pending or rejected approvals  
   - Email/chat context with HR (if integrated and allowed)  

4. Constructing a watsonx.ai-style prompt to contextualize all this data and respond with:

> “Your salary was reduced by ₹2,000 due to a half-day leave taken on April 15, which exceeded your leave balance. Your manager’s approval was recorded on April 17, past the monthly cutoff. This aligns with the Leave and Attendance Policy, Section 4.1.”

This scenario showcases the assistant’s ability to combine image understanding, document retrieval, and real-time system data into a single, explainable output. It transforms what would be a tedious back-and-forth with HR into a seamless, AI-powered experience — grounded in IBM’s mission to build trustworthy and intelligent enterprise systems using watsonx.ai.

## ✅ Included Components

### 🔹 IBM watsonx.ai  
Enterprise-grade AI platform used to simulate Retrieval-Augmented Generation (RAG) for grounded, natural language responses using IBM’s foundation models like Granite.

### 🔹 IBM Watson Studio  
A collaborative development environment leveraged for designing prompts, simulating model outputs, and showcasing integration workflows for enterprise AI applications.

### 🔹 IBM Cloud Object Storage  
Simulated as the secure storage layer for HR policy documents and image data, forming the retrievable knowledge base for semantic search.

### 🔹 Jupyter Notebooks  
Used to demonstrate the end-to-end workflow — from OCR to document retrieval to answer generation — through live code, sample inputs, and annotated explanations.

### 🔹 Tesseract OCR  
Open-source Optical Character Recognition tool used to extract structured text from images like payslips and offer letters, enabling multimodal input processing.
