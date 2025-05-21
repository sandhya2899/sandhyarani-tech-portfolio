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

## 🎯 Prompt Design Strategy

In a Retrieval-Augmented Generation (RAG) pipeline like *Snap and Ask*, the success of natural language responses depends on how effectively user queries and contextual data are framed into prompts for the foundation model.

---

### 🛠️ Design Framework

Prompts in *Snap and Ask* are constructed using a three-part approach:

1. **System Role Definition**  
   Describes the assistant's function and tone (e.g., a virtual HR support agent trained on internal policies).

2. **Contextual Inputs**  
   Sourced from OCR output (from the uploaded image), related HR document content, and structured metadata (e.g., dates, codes).

3. **User Intent**  
   Captures the employee’s free-form query or doubt.

This structured prompting ensures coherence, precision, and policy relevance in the generated responses.

---

### 📄 Prompt Template

You are an AI assistant trained on a company’s HR policies and internal communication protocols.  
Use the provided context to answer the user’s question as clearly and accurately as possible.

Context:
- Document type: <e.g., payslip, offer letter, portal screenshot>
- Extracted text: <Key content from OCR>
- Retrieved policy content: <Relevant document excerpts>
- Metadata: <e.g., dates, deduction codes, balances>

User Query: <User’s original question>

Answer:

This flexible structure allows the assistant to adapt to various document types and employee concerns.

---

### 🔁 Prompt Variation by Use Case

| **Document Type**           | **Contextual Focus**              | **Prompt Strategy**                         |
|----------------------------|----------------------------------|---------------------------------------------|
| Payslip (image)            | Deduction codes, salary details  | Highlight amounts and explain discrepancies |
| Offer Letter (PDF)         | Clauses, compensation, benefits  | Summarize terms and clarify policies        |
| Internal Portal Screenshot | Leave status, balances, approvals| Interpret codes and map to HR explanations  |

Prompt templates are dynamically adjusted based on input type, enabling consistent performance across a wide range of HR document scenarios.

## 🧪 Simulated Scenarios: How Snap and Ask Responds

The following scenarios illustrate how Snap and Ask simulates HR query resolution using a combination of OCR, similarity-based retrieval, and foundation model generation via IBM watsonx.ai.

Each example shows how the assistant interprets a user question, extracts visual text data, searches the HR policy base, and composes a grounded response.

---

### 📄 Scenario 1: Payslip Deduction Clarification

**Uploaded Image:** A screenshot of a payslip  
**User Question:** “Why is ₹2,000 deducted this month?”

**Extracted Text via OCR:**
-Deduction Code: LOP-APRIL

-Amount: ₹2,000


**Retrieved Data from HR Systems:**
- One unapproved leave recorded on April 15th  
- No managerial approval before payroll processing date

**Retrieved Policy:**
> *Clause 4.1: One day’s salary will be deducted for each unapproved leave exceeding the balance quota.*

**Generated Response:**
> ₹2,000 was deducted due to one unapproved leave on April 15th. As per Section 4.1 of the Leave Policy, a full day’s salary is deducted for each such instance. Approval was not granted before the payroll processing date.

---

### 📄 Scenario 2: Offer Letter Clause Confusion

**Uploaded Document:** Offer letter PDF  
**User Question:** “What does Clause 6.2 mean?”

**Extracted Text:**
6.2: Variable compensation shall be subject to business performance and individual ratings. No minimum payout is guaranteed.


**Retrieved Policy Summary:**
> *Variable components are performance-linked and discretionary in nature.*

**Generated Response:**
> Clause 6.2 indicates that your variable pay is not fixed and will depend on company results and your performance rating. It’s not guaranteed, and the payout amount can vary.

---

### 📄 Scenario 3: Leave Status from Portal Screenshot

**Uploaded Image:** Screenshot from internal HR portal  
**User Question:** “Why is my casual leave rejected?”

**Extracted Text:**
Leave ID: CL-9023

Status: Rejected


**Retrieved Data from HR Systems:**
- Casual leave count exceeded monthly quota (3 applied, limit is 2)

**Retrieved Rule:**
> *Employees can apply for a maximum of 2 casual leaves per month.*

**Generated Response:**
> Your casual leave request (ID CL-9023) was rejected because it exceeded the monthly limit of two casual leaves, as outlined in the Leave and Attendance Policy.

---

### 📄 Scenario 4: Bonus Calculation Clarification

**Uploaded Document:** Year-end bonus breakdown  
**User Question:** “Why is my bonus lower than last year?”

**Extracted Text:**
Bonus FY 2023–24: ₹50,000

**Retrieved Data from HR Systems:**
- Bonus FY 2022–23: ₹65,000  
- Performance Rating FY 2023–24: 3

**Retrieved Benchmark Policy:**
> *Employees with a performance rating of 3 or below are eligible for reduced bonus payouts.*

**Generated Response:**
> Your bonus this year was ₹50,000 compared to ₹65,000 last year, primarily due to a performance rating of 3. According to the bonus policy, lower ratings correspond to reduced payout brackets.

---

These scenarios showcase the assistant’s ability to simulate intelligent, grounded interactions — leveraging OCR, HR knowledge bases, and prompt-based generation in watsonx.ai to create clear and contextual responses. While the implementation is conceptual, the examples mirror realistic enterprise HR queries and demonstrate IBM watsonx.ai’s potential in solving them.

## 🧾 License & Acknowledgement

**License**  
This repository and its contents are provided **“as-is”** for demonstration and educational purposes only. No production deployment is intended or supported.  

**Acknowledgement**  
This project was inspired by and conceptually aligned with IBM’s enterprise AI offerings. Special thanks to:  
- [IBM watsonx.ai Documentation](https://www.ibm.com/docs/en/watsonx)  
- IBM’s best practices for Retrieval-Augmented Generation and Responsible AI  
- Open-source tools and communities that enable rapid prototyping of AI-driven applications  
  
---

**Author**  
Sandhya Rani — Technical Content Specialist & Researcher
