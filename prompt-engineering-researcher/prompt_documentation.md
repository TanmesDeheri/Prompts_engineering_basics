**Step 1: Generate Factual Summary**
Generate a factual summary detailing the core architecture, scalability limits, setup
complexity, and cost structures of the following three technologies:
- Kubernetes
- Docker Swarm
- AWS Fargate
Focus on raw specifications, documentation facts, and industry statistics. Do not write
a comparison or recommendations yet. Keep your focus on compiling background knowledge.

ERA research Prompt
----------------------------
[EXPECTATION]: I expect a detailed comparison report comparing Kubernetes, Docker
Swarm, and AWS Fargate. Structure the response with H2 headers for: Introduction, Tech
Overviews, Detailed Comparison, and Final Verdict. Do not write summary tables yet.
[ROLE]: Act as a Lead Systems Architect.
[ACTION]: Write the comparison report based on the following background facts:
=== BACKGROUND FACTS ===
[Insert the fact sheet generated]

4 Step CoVe Process
CoVe Prompt
----------------------------
Read the baseline draft comparison below. Formulate a list of exactly four specific
verification questions that can be answered with absolute facts to audit the claims,
numbers, and limitations stated in the text (e.g. check version limits, specific
scalability numbers, or operational dependencies).
[BASELINE DRAFT]:
[Insert the text from ERA_Draft.txt]

Answer each of the following verification questions one-by-one. Rely strictly on
verified developer documentation facts:
[Insert the four questions generated in the previous step]

CoVe Correction Prompt
----------------------------
Review the original baseline draft. Rewrite the report incorporating the verified
corrections below. Ensure the final report is fully accurate and resolved.
[ERA DRAFT]: [Insert ERA_Draft.txt]
[VERIFIED CORRECTIONS]: [Insert the answers from the previous step]

Assumption Audit Prompt
----------------------------
Analyze the finalized technology comparison below. Identify and list 3 hidden
assumptions the writer makes regarding the technologies (e.g. assuming high capital
expense always correlates with higher quality, or assuming simplicity is always better
for small teams). Detail if these assumptions introduce bias.
[FINALIZED REPORT]:

Comparision Matrix Prompt
----------------------------
Create a markdown table comparing Kubernetes, Docker Swarm, and AWS Fargate across
these columns:
- Technology
- Scalability (High/Med/Low)
- Setup Complexity (High/Med/Low)
- Operational Overhead (High/Med/Low)
- Cost Model (e.g. Pay-per-node, Pay-per-use, Free)
----------------------------
Executive Summary Prompt
----------------------------

Write a 150-word executive summary synthesizing the comparison findings. Recommend the
best technology for a fast-growing startup prioritizing speed over infrastructure
scaling.
