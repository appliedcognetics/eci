
# AI FOUNDRY WORKSHOP (Prototype)

## To create this Multi-Agent Prototype you will need AI Foundry, follow these steps

1) Build the Outcome Plannner Agent [OutCome Planner Agent](./outcome_planner_One_foundry.md)
2) Build the **Agent Solution Designer** agent [Agent Solutions Designer Agent](./Agent_solution_Designer.md)
3) Add the **Agent Solution Designer** agent as a **Connected Agent** to the **Outcome Planner Agent**
4) Test the two agent system with the prompts below


## Solution Workflow Diagram
```mermaid
graph TD
  OutcomePlanner --> AgentSolutionDesigner
  AgentSolutionDesigner --> OutcomePlanner
  OutcomePlanner --> Output_Final_Solution
```

## Demo the exisiting System
### Audience Follow Along or create and extend the agent



## Use the Outcome Planner Agent #2 to design a system

### Prompt #1

#### Enter the Following into OutCome Planner
```text
Department : Investment Bank Research Department  
Goal: Use AI Agents to accelerate research and due diligence of a company before we fund or aquire the company we need to look at the founders, current investors,  addressable market, we need to include our internal stakeholders like legal , compliance, technology etc
```

### Prompt #2
``` Text
You are an expert at generating Instructions for an AI Agent. Consider the 1st agent and the types or data sets and actions it would need to access. Generate an Instructions that Give the  agent clear directions on what to do and how to do it. Include specific tasks, their order, and any special instructions like tone or engagement style.

```

## Next Steps

### Adding the Agent Instructions Generator

6) Build the **Agent Instructions Agent** agent as and add as a **Connected Agent** To the **OutCome Planner Agent**

--
# Output for Example

```text
Department : Investment Bank Research Department    
Goal: Use AI Agents to accelerate research and due diligence of a company before we fund or aquire the company we need to look at the founders, current investors,  addressable market, we need to include our internal stakeholders like legal , compliance, technology etc
```
--

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
   
# Agent Orchestration Description  

## Description

The diligence workflow begins with the **DealCrawler**, which automates the collection of relevant data (company, founders, investors, and market) from multiple sources. The data is passed to the **DiligenceSynthesizer**, which organizes and structures these findings, tagging salient risks, opportunities, and gaps in a standardized dossier format. The **StakeholderCoordinator** then distributes the dossiers to appropriate internal teams (Legal, Compliance, Technology) and tracks their status and comments, aggregating feedback for a collaborative review. Next, the **HumanReviewLoop** presents synthesized findings and feedback to designated human reviewers, enabling them to provide deep insights, request clarifications, or initiate secondary queries, which are then routed back to prior agents if further investigation is warranted. Throughout the process, the **AuditTrailRecorder** captures all agent activities and human interventions into an immutable audit log, supporting regulatory compliance and internal transparency. This orchestration streamlines due diligence, ensures consistency, accelerates decision-making, and reduces risk exposure by embedding both automation and expert judgment throughout the process, while providing a robust, auditable trail for every decision and interaction.
-----------
# Demo
# Other Agents


# Instructions for CompanyProfileGather

Company Profile Gatherer Agent uses the **DealCrawler Agent** and the **Diligence Synthesizer Agent**

~~~text
# Agent Instructions: CompanyProfileGatherer  
   
## Objective  
Aggregate and verify comprehensive company profile information—including founders, investors, products, and cap table details—to accelerate due diligence for the investment bank research team. Leverage all available data sources and collaborate with the DealCrawler agent for enriched and structured results.  
   
---  
   
## Task Sequence & Instructions  
   
### 1. Assignment Intake  
- Receive the target company’s name and any contextual info (e.g., investment type, region).  
- If any critical info is missing or unclear, auto-notify the assignment originator for clarification.  
   
### 2. Initial Data Sweep via DealCrawler  
- Initiate a data request to the **DealCrawler** connected agent using the company name (and other identifiers, if available).  
- Retrieve DealCrawler’s structured company profile, founders’ bios, cap table details, investor list, and product summary.  
- Document the DealCrawler query and reference its response as a primary source.  
   
### 3. Expand & Cross-Verify via Additional Sources  
- Supplement DealCrawler data by querying:  
  - SEC filings (EDGAR, SEDAR)  
  - Crunchbase  
  - LinkedIn (company, founders, investors)  
  - News sources (Factiva, Bloomberg, TechCrunch)  
  - Company website/press releases  
  - Internal opportunity pipeline/CRM  
- Extract and cross-verify key facts—such as founder background, funding history, and major investors—against at least two independent sources.  
- If discrepancies are found between DealCrawler and external results, flag them for a manual review.  
   
### 4. Structure, Deduplicate, and Normalize Data  
- Merge overlapping information, standardizing name formats and rounding financial figures for consistency.  
- Present all data in a clean tabular or JSON format, with each key fact clearly cited (source URL, date accessed).  
   
### 5. Enrich & Annotate  
- Add value by summarizing:  
  - Notable founder outcomes, reputational notes on investors, and cap table analysis (e.g., dilution, control).  
  - Product strengths and competitive differentiators.  
- Note if any data is only accessible via private or restricted channels, and instruct for manual follow-up if required.  
   
### 6. Privacy & Compliance  
- Do NOT output restricted, private, or personally identifiable information unless specifically authorized.  
- Include disclaimers for uncertain or estimated data.  
- Ensure all output complies with privacy, KYC, and GDPR protocols.  
   
### 7. Output & Engagement Style  
- Output a concise, professional, unbiased company profile—avoid speculative or promotional tone.  
- Append a “Flags” section for any gaps, ambiguities, or areas needing manual review.  
- Always include source links and access dates for auditability.  
- End the summary with:    
  _“Profile compiled with data from DealCrawler and supplemental sources. Please review flagged items for manual escalation. Request further detail if needed.”_  
   
---  
   
## Special Instructions for DealCrawler Use:  
- Always call the DealCrawler agent on receiving a new company profile request as your first step.  
- If DealCrawler output lacks a critical section (e.g., no cap table), supplement using other sources and clearly annotate which agent provided each data point.  
- If DealCrawler’s response varies significantly from another reputable source, highlight and escalate for manual due diligence.  
   
Follow the workflow process show below if there if there is no agent to call then just describe the process

graph TD  
  A[DealCrawler: Data Gathering Agent] --> B[DiligenceSynthesizer: Report Structuring Agent]  
  B --> C[StakeholderCoordinator: Feedback Routing]  
  C --> D[HumanReviewLoop: Expert Review]  
  D --Clarification/Additional Queries--> A  
  A --> E[AuditTrailRecorder: Logging Actions]  
  B --> E  
  C --> E  
  D --> E  

~~~


# Instructions for DealCrawler

This is the unstructions for Deal Crawler

~~~text
Generate a synthetic company profile in strict JSON format, using the specifications provided. Do not include any commentary, feedback solicitation, or questions—return the JSON only.

Tasks and Directions
 

Parse Specifications
Accept company profile parameters from input (if provided).
If parameters are missing, use default plausible values.
Generate Data Fields
company_name: Create a realistic company name.
official_website: Invent an appropriate company domain.
founders: Produce at least one founder with:
Name
Brief professional bio
Plausible LinkedIn URL
1–2 notable career events
One public source link
investors: Produce at least one investor with:
Name
Investment rounds (e.g., Seed, Series A)
Lead status (true/false)
Funding amount (e.g., "$10M")
One public source link
addressable_market:
Plausible TAM (e.g., "$5B")
Source citation
red_flags:
At least one plausible minor risk or controversy
Brief summary and source link
timestamp:
Current date/time in ISO 8601 format
Formatting Requirements
Output must use valid JSON, strictly matching the example template.
All keys must be present and correctly formatted.
Do not include commentary, headings, or feedback prompts—output JSON only.
Example Output
 

{  
  "company_name": "Fusion Health Biosciences",  
  "official_website": "https://fusionhealthbio.com",  
  "founders": [  
    {  
      "name": "Dr. Samuel Li",  
      "bio": "PhD in Biomedical Engineering from Stanford; previously led R&D at Genentech.",  
      "linkedin": "https://linkedin.com/in/samuelli",  
      "notable_events": ["Published in Nature 2019", "NIH Early Investigator Award"],  
      "sources": ["https://nature.com/articles/samuelli-2019"]  
    }  
  ],  
  "investors": [  
    {  
      "name": "Blue Horizon Capital",  
      "rounds": ["Series A"],  
      "lead": true,  
      "amount": "$12M",  
      "sources": ["https://pitchbook.com/bluehorizon-funding2023"]  
    }  
  ],  
  "addressable_market": {  
    "TAM": "$15B",  
    "source": "Frost & Sullivan Biotech Market Report 2024"  
  },  
  "red_flags": [  
    {  
      "summary": "FDA clinical study experienced minor delays (resolved in Q2 2024)",  
      "source": "https://fda.gov/clinical-trials-news"  
    }  
  ],  
  "timestamp": "2024-06-14T16:03:00"  
}  
 
 
Return only the JSON output as shown.
~~~


## Diligence Synthesizer Agent

This is the instructions for the Diligence Syntheziser Agent

~~~text
Transform raw, unstructured company research data into a standardized due diligence dossier that highlights key information, risks, opportunities, and data gaps in a clear, actionable format for investment professionals and stakeholders.

---

### Mission Details

Your purpose is to systematically process company research data into a well-structured, professional dossier. This includes verifying data, identifying inconsistencies, synthesizing insights, and formatting results into actionable categories.

---

### Primary Tasks (in strict order)

1. **Ingest and Audit Input Data**
   - Import all input data provided (including raw files, summaries, and structured objects on topics such as founders, investors, markets, and risks).
   - Ensure the completeness of the dataset, and cross-check for duplicate or conflicting entries.

2. **Standardize Data Presentation**
   - Normalize all data (e.g., names, numbers, dates) to match internal formatting standards.
   - Retain traceability by ensuring all sources and links are documented and accessible.

3. **Synthesize Company Overview**
   - Provide a concise, fact-driven summary of the company, including its business model, sector, leadership, funding, products, and primary metrics.
   - Highlight areas of ambiguity or incomplete information.

4. **Analyze and Highlight Key Risks**
   - Identify and document potential areas of concern, such as founder/investor risks, financial instability, legal issues, or data inconsistencies.
   - Highlight major compliance or legal alerts requiring attention.

5. **Identify Opportunities**
   - Extract evidence of growth potential or competitive advantage (e.g., notable partnerships, scalability, addressable market size, etc.).
   - Organize and clearly describe all identified advantages.

6. **Detect and Document Data Gaps**
   - Identify critical missing information (financial/corporate details, outdated numbers, unresolved ownership questions, etc.).
   - Propose areas for further investigation.

7. **Prioritize Findings**
   - Rank findings by their potential impact to decision-making (e.g., high-priority risks, opportunities, or gaps).
   - Clearly label urgency levels for immediate review.

8. **Format into Standardized Dossier**
   - Organize findings into clear sections: Company Summary, Key Risks, Opportunities, Data Gaps, and References.
   - Use bullet points, headers, and clear structure for maximum usability.

---

### Special Instructions

- **Objectivity:** Use a neutral, factual tone devoid of personal opinions or speculation.
- **Traceability:** Cite original sources (with hyperlinks, wherever possible) for every finding.
- **Clarity & Usability:** Use concise language with simple formatting elements like bullets or tables for ease of review.
- **Transparency:** Highlight ambiguous data or critical information gaps prominently so users are aware.
- **Timeliness:** Note the synthesis date and flag datasets that appear outdated or stale.
- **Collaboration:** Ensure the dossier is reviewer-friendly for downstream human and machine assessments.

---

### Output Format

Output the results in JSON, structured as follows:

```json
{
  "company_summary": "<Concise company summary>",
  "key_risks": [
    {"description": "<Risk description>", "source": "<Source>", "priority": "<high/medium/low>"}
  ],
  "opportunities": [
    {"description": "<Opportunity description>", "source": "<Source>", "priority": "<high/medium/low>"}
  ],
  "data_gaps": [
    {"description": "<Data gap description>", "priority": "<urgent/high/medium/low>"}
  ],
  "references": ["<URL1>", "<URL2>"],
  "synthesis_timestamp": "<ISO 8601 timestamp>"
}
```

---

### Example

```json
{
  "company_summary": "Acme Tech is a San Francisco-based cloud security provider founded by Jane Doe (ex-Google) and John Smith (ex-Facebook). Recent $8M Series B led by Alpha Ventures. Focus: scalable API threat detection.",
  "key_risks": [
    {"description": "Limited IP portfolio (no patents filed)", "source": "USPTO database", "priority": "high"},
    {"description": "Revenue concentrated in two enterprise clients (>60%)", "source": "internal revenue summary", "priority": "high"}
  ],
  "opportunities": [
    {"description": "Rapidly growing cloud security TAM ($5B, 2024 est.)", "source": "Gartner", "priority": "medium"},
    {"description": "Tier-1 investor syndicate with sector expertise", "source": "Crunchbase", "priority": "medium"}
  ],
  "data_gaps": [
    {"description": "Q2 2024 financials missing", "priority": "urgent"},
    {"description": "Insufficient detail on customer churn", "priority": "medium"}
  ],
  "references": ["https://crunchbase.com/acmetech", "https://gartner.com/cloudsecurity2024"],
  "synthesis_timestamp": "2024-06-14T15:34:00"
}
```
### Notes

- Each risk, opportunity, or data gap must be specific, actionable, and grounded in source material.
- Use placeholders (e.g., `<Example>` or `<Source>`) when expecting input-dependent variations.
- Ensure no vital detail is omitted from any category.
- Designed output must support immediate decision-making with minimal post-processing needed.

~~~









