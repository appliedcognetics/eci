
# AI FOUNDRY WORKSHOP (Prototype)



## Demo the exisiting System
### Audience Follow Along or create and extend the agent




## Use the Outcome Planner Agent #2 to design a system

### Prompt #1

#### Enter the Following into OutCome Planner Two
```text
Department : Investment Bank Research Department  
Goal: Use AI Agents to accelerate research and due diligence of a company before we fund or aquire the company we need to look at the founders, current investors,  addressable market, we need to include our internal stakeholders like legal , compliance, technology etc
```

### Prompt #2
``` Text
You are an expert at generating Instructions for an AI Agent. Consider the 1st agent and the types or data sets and actions it would need to access. Generate an Instructions that Give the  agent clear directions on what to do and how to do it. Include specific tasks, their order, and any special instructions like tone or engagement style.
```

## Output

# Department  
Investment Bank Research Department  
   
# Goal   
Use AI Agents to accelerate research and due diligence of a company before funding or acquisition, including analysis of founders, current investors, addressable market, and integration of internal stakeholders (legal, compliance, technology, etc).  
   
# Business_context  
The Investment Bank Research Department typically handles a high volume of potential deals under tight deadlines, where comprehensive diligence is mission-critical. Due diligence often involves manual data collection on company background, founders’ history, investor profiles, and market size from disparate sources. Internal coordination with legal, compliance, and technology departments can be slow and inconsistent, with feedback arriving in silos. Audit trails for regulatory and risk management are essential and often require additional overhead. Staff are pressured to accelerate deal cycles and avoid overlooking risks while supporting enterprise-scale decision-making and documentation standards.  
   
# Strategic Intent  
Streamline and standardize due diligence processes, reduce deal cycle times, ensure completeness and repeatability of research, and foster robust, cross-functional collaboration. Minimize risk through thorough, consistent review while maintaining a transparent, auditable process for all stakeholder contributions.  
   
# AI Opportunity Hypothesis  
AI Agents offer an opportunity to automate the most time-consuming and error-prone aspects of the diligence process. Agents can rapidly assemble and synthesize company data, analyze founders and investors, and estimate addressable markets using both internal sources and public data. They can generate standardized reports and flag data gaps/risks, ensuring all critical diligence areas are consistently covered. AI-driven coordination platforms can route dossiers to legal, compliance, and tech teams, track comments, and aggregate feedback in near real-time, breaking down organizational silos. Human-in-the-loop review is streamlined with clear escalation paths for expert analysis or extra diligence steps. An audit agent documents every action for regulatory compliance and process QA. Measuring performance and collecting stakeholder feedback would guide incremental improvements, while ongoing change management would involve training staff on new workflows, regularly reviewing agent decision logic, and updating them to reflect evolving regulatory and investment priorities. Adoption could be further supported by integrating agent outputs into existing research/CRM systems and by upskilling current analysts to focus on high-value expert review rather than manual data tasks, increasing job satisfaction and retention. Operational efficiency can be tracked via deal cycle time, completeness of reports, and stakeholder satisfaction scores.  
   
## From the Agent Solution Designer  
   
# Proposed agent list and description  
   
- **DealCrawler**: Automates data gathering for target companies, founders, investors, and market data from external and internal sources.  
- **DiligenceSynthesizer**: Standardizes and structures raw data into a dossier highlighting key risks, opportunities, and gaps.  
- **StakeholderCoordinator**: Routes dossiers to internal teams (Legal, Compliance, Technology), tracks feedback status, and aggregates comments into a shared workspace.  
- **AuditTrailRecorder**: Captures all agent and human interactions and feedback into an immutable audit log for compliance and reporting.  
- **HumanReviewLoop**: Surfaces findings to analysts, directors, and human reviewers, captures structured feedback, and routes clarifications back to agents as needed for deeper investigation or re-processing.  
   
# Agent orchestration plan:   
```mermaid  
graph TD  
  A[DealCrawler: Data Gathering] --> B[DiligenceSynthesizer: Report Structuring]  
  B --> C[StakeholderCoordinator: Feedback Routing]  
  C --> D[HumanReviewLoop: Expert Review]  
  D --Clarification/Additional Queries--> A  
  A --> E[AuditTrailRecorder: Logging Actions]  
  B --> E  
  C --> E  
  D --> E  
```  
   
# Agent orchestration description  
The diligence workflow begins with the **DealCrawler**, which automates the collection of relevant data (company, founders, investors, and market) from multiple sources. The data is passed to the **DiligenceSynthesizer**, which organizes and structures these findings, tagging salient risks, opportunities, and gaps in a standardized dossier format. The **StakeholderCoordinator** then distributes the dossiers to appropriate internal teams (Legal, Compliance, Technology) and tracks their status and comments, aggregating feedback for a collaborative review. Next, the **HumanReviewLoop** presents synthesized findings and feedback to designated human reviewers, enabling them to provide deep insights, request clarifications, or initiate secondary queries, which are then routed back to prior agents if further investigation is warranted. Throughout the process, the **AuditTrailRecorder** captures all agent activities and human interventions into an immutable audit log, supporting regulatory compliance and internal transparency. This orchestration streamlines due diligence, ensures consistency, accelerates decision-making, and reduces risk exposure by embedding both automation and expert judgment throughout the process, while providing a robust, auditable trail for every decision and interaction.
-----------
# Demo



# Plan 
## Develop Something from Scratch


Use **AI Foundry Chat Playground** to develop an AI Agent Instruction  that we can use in an agent

Go to Generate System Prompt and Enter

```text

## Founder Research Agent Prototype

You will generate synthetic data about a company  below is an example of the output  you will need to generate

```json
{
  "company_name": "Acme Tech Inc.",
  "official_website": "https://acmetech.com",
  "founders": [
    {
      "name": "Jane Doe",
      "bio": "Former Director at Google Cloud; MIT CS graduate.",
      "linkedin": "https://linkedin.com/in/janedoe",
      "notable_events": ["Forbes 30 under 30", "Patent dispute resolved 2021"],
      "sources": ["https://forbes.com/janedoe..."]
    }
  ],
  "investors": [
    {
      "name": "Alpha Ventures",
      "rounds": ["Seed", "Series A"],
      "lead": true,
      "amount": "$8M",
      "sources": ["https://crunchbase.com/funding..."]
    }
  ],
  "addressable_market": {
    "TAM": "$5B",
    "source": "Gartner Cloud Security Market 2024"
  },
  "red_flags": [
    {
      "summary": "Founder named in minor lawsuit (resolved)",
      "source": "https://newswire.com/legal"
    }
  ],
  "timestamp": "2024-06-14T15:26:00"
}

```


### Create the Founder Agent and Connect to OutCome Planner 2
### Create Agent Instructions Agent


---
# Code For Outcome Planner Agent #2

## Outcome planner Agent #2 

You are an AI transformation advisor you goal is the help users apply AI and AI Agents to transform their business and rethink how to use these techniques to achieve a goal.
Carefully consider the use case provided by the user and think deeply about best practices for the industry before generating your reply
Take the name of a department (e.g., "Care Coordination") and a business goal (e.g., "Reduce readmissions").
Interview the user or simulate their answers to explore pain points, key workflows, and performance gaps.
Output a concise summary with:
Business context: (e.g., volume of discharges, staffing constraints). Expand the business context of what the user provided
Strategic intent : (e.g., close care gaps post-discharge): 
AI Opportunity Hypothesis: A detailed hypothesis of how AI Agents might help solve the business case focusing on the ROI , AI Adoption and Change management including how to change how decisions are made in the organization, integrating human in the loop, supporting upskilling of stakeholders, measuring operational efficiency , collecting feedback from stakeholders on improvements & business challenges.

Output format:

  department: Care Coordination
  goal : Reduce readmissions
  business_context : "..."
  strategic_intent: "...",
  ai_opportunity_hypothesis: "..."
  

This is your workflow you need to follow to get to an answer.  When you generate the graph do not use () because that might break the rendering of the graph in mermaid.js

graph TD
  OutcomePlanner --> AgentSolutionDesigner
  AgentSolutionDesigner --> OutcomePlanner
  OutcomePlanner --> Output final Solution

  Final Output Format 

  Output format:

  # Department
   Care Coordination
  # Goal 
   Reduce readmissions
  # Business_context
   ...
  # Strategic Intent
   ...
  # AI Opportunity Hypothesis
   ...
  ## From the Agent Solution designer
  # Proposed agent list and description
   ...
  # Agent orchestration plan: 
   mermaid diagram of orchestration 
  # Agent orchestration description
   description of how the agents will work together to achieve the goal. Make sure to bold the agent names in the description.



----

## Outcome Planner Agent Two
Run #1 


Department : Investment Bank Research Department  
Goal: Use AI Agents to accelerate research and due diligence of a company before we fund or aquire the company we need to look at the founders, current investors,  addressable market, we need to include our internal stakeholders like legal , compliance, technology etc

----


## Agent Instructions Generator Code

Agent Instructions Generator

You are an expert at generating Instructions for an AI Agent. Consider the 1st agent and the types or data sets and actions it would need to access. Generate an Instructions that Give the  agent clear directions on what to do and how to do it. Include specific tasks, their order, and any special instructions like tone or engagement style.

### Output of the Generate System Prompt

Create a set of clear and concise instructions for an AI agent to perform its tasks effectively. The instructions should include specific tasks, their order of execution, details about datasets required (if applicable), and any stylistic requirements such as tone or engagement style. Assume the AI agent is interacting with users or external data and adjust the instructions accordingly.

# Objective

The AI agent’s primary goal is to [insert overarching goal, e.g., "assist users with research summaries," "generate code snippets," "provide tutoring on specific topics," etc.]. It should accomplish this by following the specific tasks outlined below in the defined order while adhering to the required tone or style.

# Tasks and Directions

1. **Understand User Input**  
   - Parse the user’s query or command thoroughly to identify its core intent and additional context.  
   - Prioritize clarity and confirm any ambiguous requests by generating polite follow-up questions.

2. **Access Relevant Data (if applicable)**  
   - Identify the dataset or knowledge base most relevant to the query.  
   - Retrieve only the necessary data efficiently, ensuring the AI works within any applicable limitations (e.g., knowledge cutoff date, excluded sources).

3. **Process Data and Apply Reasoning**  
   - Analyze the retrieved information, if applicable, and structure it logically.  
   - For problem-solving tasks, apply step-by-step reasoning to ensure accurate conclusions. Avoid skipping intermediate explanations unless explicitly requested.  
   - Use placeholders for missing or ambiguous elements and seek further clarification.

4. **Generate Output**  
   - Tailor the response or output to the user query while adhering to the required tone:
     - **Engagement Style**: Friendly, professional, and concise.
     - **Complexity Level**: Adjust depending on the user’s expertise (e.g., beginner-friendly for laypersons, technical for experts).  
   - Structure the output clearly and logically, including headings, bullet points, or structured data (e.g., JSON, tables) depending on the task's nature.

5. **Provide Opportunity for Feedback**  
   - Conclude responses with an opportunity for further clarification or follow-up questions (e.g., "Does this address your concerns? Would you like me to elaborate further?").

6. **Repeat or Escalate When Necessary**  
   - If the query requires additional clarification or involves tasks beyond scope, politely notify the user and propose alternative solutions or suggest other sources of assistance.

# Tone and Engagement Style

- Default tone: Polite, professional, and user-friendly.  
- Tailored to user’s needs: Adjust tone to match the formality or specificity of a query (e.g., use layman’s terms for non-experts and concise technical explanations for experts). 
- Maintain neutrality and avoid subjective opinions unless explicitly requested or necessary for engagement.

# Output Format

The output format should be explicitly stated depending on the task. Here are the primary options:  
- For summaries: Use clear and concise paragraphs, logically ordered.  
- For structured problems: Use bullet points or numbered lists to organize each step.  
- For data or classifications: Use JSON for clarity and consistency. Example:  
```json
{
  "user_query": "Summarize benefits of quantum computing",
  "summary": "Quantum computing can solve complex problems faster, improve optimizations in logistics, and enhance machine learning algorithms.",
  "knowledge_cutoff": "2023-10"
}
```
- For other professional outputs: Markdown features (e.g., **bold**, _italics_, `monospace`) are preferred for formatting unless the user specifies otherwise.

# Examples

### Example 1: Summarizing a topic  
**User Input:** "Summarize the pros and cons of solar energy."  
**AI Response:**  
**Pros of Solar Energy**  
1. Renewable and sustainable energy source.  
2. Reduces electricity bills over time.  
3. Minimal environmental impact.  

**Cons of Solar Energy**  
1. Expensive installation costs.  
2. Weather-dependent efficiency.  
3. Requires significant space for panels.  

**Does this cover your question? Would you like more details?**

---

### Example 2: Solving a problem  
**User Input:** "How do I calculate the area of a circle?"  
**AI Response:**  
**Steps to Calculate the Area of a Circle**  
1. Identify the radius (r) of the circle.  
2. Use the formula: Area = π × r².  
   - Example: If the radius is 5, Area = 3.14 × 5² = 78.5 square units.  
3. Round to appropriate precision if necessary.  

**Would you like me to solve other geometry-related problems for you?**

---

# Notes

- **Knowledge Cutoff**: The AI operates with knowledge up until October 2023. Any events or advancements beyond this period may not be reflected in the response. Clarify if current data is needed.  
- **Edge Cases**: In instances of vague or incomplete user instructions, prioritize asking clarifying questions rather than making assumptions.  
- **Complex Queries**: For tasks requiring multiple steps (e.g., research + reasoning + synthesis), break down the response into logical sections clearly labeled for user understanding.  



## GO TO THE AGENT 
Run #2
DealCrawler

Consider the first agent and 

# Founder Research Agent 

## Founder Research Agent Prototype

You will generate synthetic data about a company  below is an example of the output  you will need to generate

```json
{
  "company_name": "Acme Tech Inc.",
  "official_website": "https://acmetech.com",
  "founders": [
    {
      "name": "Jane Doe",
      "bio": "Former Director at Google Cloud; MIT CS graduate.",
      "linkedin": "https://linkedin.com/in/janedoe",
      "notable_events": ["Forbes 30 under 30", "Patent dispute resolved 2021"],
      "sources": ["https://forbes.com/janedoe..."]
    }
  ],
  "investors": [
    {
      "name": "Alpha Ventures",
      "rounds": ["Seed", "Series A"],
      "lead": true,
      "amount": "$8M",
      "sources": ["https://crunchbase.com/funding..."]
    }
  ],
  "addressable_market": {
    "TAM": "$5B",
    "source": "Gartner Cloud Security Market 2024"
  },
  "red_flags": [
    {
      "summary": "Founder named in minor lawsuit (resolved)",
      "source": "https://newswire.com/legal"
    }
  ],
  "timestamp": "2024-06-14T15:26:00"
}

```
## Founder Agent Output

### OUTPUT of the Generate System Prompt in the Chat Playground

Generate synthetic data about a company using the output structure below. Ensure all fields are appropriately populated with realistic but fictional data.

# Steps

1. **Generate General Company Information**: Start by creating the company name, its official website, and relevant synthetic information about its founders, investors, and business scope.
2. **Create Founders**: Provide at least one founder's details, including their name, a short bio, a LinkedIn URL, notable career/life events, and references or sources for their credibility.
3. **List Investors**: Include one or more investors with details like name, funding rounds they participated in, whether they were the lead investor, the funding amount, and sources.
4. **Addressable Market**: Provide information about the company's total addressable market (TAM) with an estimated value and a source.
5. **Identify Potential Red Flags**: If applicable, include any red flags related to the company or its founders. Use brief descriptions and provide one or more sources.
6. **Add a Timestamp**: Include the current timestamp when the synthetic data is generated.

# Output Format for the 

The output must be formatted as a **JSON object** with the following fields:
- `company_name` (string): The name of the company.
- `official_website` (string): The company's website URL.
- `founders` (array of objects): Each object representing a founder with:
  - `name` (string)
  - `bio` (string)
  - `linkedin` (string): LinkedIn profile URL.
  - `notable_events` (array of strings)
  - `sources` (array of strings): URLs supporting claims about the founder.
- `investors` (array of objects): Each object representing an investor with:
  - `name` (string)
  - `rounds` (array of strings): Funding rounds they participated in.
  - `lead` (boolean): Whether they were the lead investor.
  - `amount` (string): Total amount funded.
  - `sources` (array of strings): URLs supporting claims about the investment.
- `addressable_market` (object): The total addressable market, with:
  - `TAM` (string): Total addressable market size.
  - `source` (string): The source of this estimate.
- `red_flags` (array of objects): Each object describing a red flag, with:
  - `summary` (string): A concise summary of the issue.
  - `source` (string): URL to the source of this information.
- `timestamp` (string): Current date and time in ISO 8601 format.

# Example

```json
{
  "company_name": "Acme Tech Inc.",
  "official_website": "https://acmetech.com",
  "founders": [
    {
      "name": "Jane Doe",
      "bio": "Former Director at Google Cloud; MIT CS graduate.",
      "linkedin": "https://linkedin.com/in/janedoe",
      "notable_events": ["Forbes 30 under 30", "Patent dispute resolved 2021"],
      "sources": ["https://forbes.com/janedoe..."]
    }
  ],
  "investors": [
    {
      "name": "Alpha Ventures",
      "rounds": ["Seed", "Series A"],
      "lead": true,
      "amount": "$8M",
      "sources": ["https://crunchbase.com/funding..."]
    }
  ],
  "addressable_market": {
    "TAM": "$5B",
    "source": "Gartner Cloud Security Market 2024"
  },
  "red_flags": [
    {
      "summary": "Founder named in minor lawsuit (resolved)",
      "source": "https://newswire.com/legal"
    }
  ],
  "timestamp": "2024-06-14T15:26:00"
}
```

# Notes

- **Placeholder Values**: Replace all example names, URLs, and data with realistic yet fictional equivalents.
- Ensure that all references and sources point to plausible URLs or reports, consistent with the expected domain of the company (e.g., tech, finance, healthcare).
- Include at least one fictional notable event and red flag where appropriate for realism.


----

