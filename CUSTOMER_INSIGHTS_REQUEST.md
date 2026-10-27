# CUSTOMER_INSIGHTS_REPORT# Task: Implement Customer Insights in HisabDo-AI

Act as a senior Python AI engineer. Inspect my existing HisabDo-AI repository and implement a Customer Insights feature that analyzes available customer records, interactions, feedback, support requests, and transaction history to identify customer activity patterns, recurring issues, and service opportunities.

## 1. Analyze the Existing Project
- Inspect the project structure, database models, customer records, interaction history, feedback, support tickets, transaction records, AI Context Layer, and existing LLM integration.
- Identify the existing data sources and how customer information is accessed.
- Review current authentication, authorization, and business-level access controls.
- Reuse existing database models, services, and AI components wherever possible.
- Do not invent database tables or replace existing architecture unnecessarily.

## 2. Collect and Analyze Customer Data
Retrieve relevant customer information from available, authorized data sources, including:
- Customer activity and interaction patterns.
- Frequently reported complaints and support issues.
- Customer feedback and recurring concerns.
- Transaction history and observable transaction patterns.
- Frequently requested services and potential service improvements.
- Relevant changes or trends over time, where timestamps and sufficient data are available.

Use actual database records and available evidence. If a data source is unavailable, report the limitation instead of generating fictional information.

## 3. Generate Evidence-Based Customer Insights
Implement a reusable Customer Insights service that:
- Identifies frequently occurring customer issues.
- Summarizes common feedback themes.
- Detects recurring interaction patterns.
- Identifies service improvement opportunities supported by customer records.
- Reports relevant transaction or activity trends when sufficient data exists.
- Distinguishes measured facts from AI-generated interpretations.
- Includes supporting counts, date ranges, or examples when available and appropriate.
- Avoids unsupported conclusions about customer preferences, intent, behavior, or satisfaction.

Do not treat a single customer complaint as a general trend. Use appropriate sample sizes and clearly communicate uncertainty.

## 4. Integrate with the AI Context Layer
- Pass relevant customer data and analysis results into the existing AI Context Layer.
- Integrate with the existing business context and RAG pipeline where appropriate.
- Ensure the AI uses retrieved records and computed evidence when generating insights.
- Avoid sending unnecessary personal information to the LLM.
- Prevent duplicate or unrelated context from affecting the analysis.
- Ensure missing data does not result in fabricated customer insights.

## 5. API and Response Structure
Implement a suitable API endpoint following the project's existing FastAPI conventions.

Use Pydantic schemas to validate requests and responses. Where appropriate, return a structured response similar to:

{
  "success": true,
  "insights": {
    "frequently_reported_issues": [],
    "interaction_patterns": [],
    "feedback_themes": [],
    "transaction_patterns": [],
    "service_opportunities": [],
    "data_limitations": []
  }
}

This is an illustrative schema. Adapt it to the existing API architecture and available data.

Support business, customer, and date-range filters only where the existing application supports them. Validate all parameters and apply authorization checks before accessing records.

## 6. Privacy and Security
- Enforce existing authentication and authorization rules.
- Respect business and tenant-level data isolation.
- Retrieve only information necessary for the requested analysis.
- Do not expose private customer details in aggregated insights unless explicitly authorized and necessary.
- Avoid logging sensitive customer information.
- Never hardcode credentials or API keys.
- Do not use unauthorized records or bypass existing access controls.

## 7. Error Handling and Reliability
Handle:
- Missing customer records.
- Empty datasets.
- Incomplete feedback or transaction history.
- Database failures.
- AI service timeouts and errors.
- Invalid request parameters.
- Unauthorized access.
- Insufficient data for reliable conclusions.

Return consistent JSON responses with appropriate HTTP status codes. Clearly distinguish unavailable information from a genuine finding that no recurring issue was detected.

## 8. Automated Testing
Create or update tests covering:
- Customer data retrieval.
- Identification of recurring support issues.
- Feedback theme analysis.
- Interaction and transaction pattern analysis.
- Evidence and count accuracy.
- Empty or incomplete datasets.
- Prevention of unsupported or fabricated insights.
- Business and tenant data isolation.
- Authentication and authorization.
- AI and database failures.
- API response validation.

Use mocked AI and database services where appropriate. Run the tests and report actual results. Clearly distinguish mocked tests from live integration tests.

## 9. Technical Report
Create `CUSTOMER_INSIGHTS_REPORT.md` containing:
- Existing architecture and identified issues.
- Data sources used.
- Implementation details and modified files.
- Insight-generation workflow.
- API endpoint and example responses.
- Privacy and access-control measures.
- Tests executed and actual results.
- Known limitations and recommended improvements.

## 10. Final Verification
- Run available automated tests and relevant validation commands.
- Fix errors introduced by the implementation.
- Verify that insights are generated from actual available records.
- Confirm that missing information is handled without inventing customer behavior.
- Verify that unauthorized customer data cannot be accessed.
- Provide commands to run the application and tests.
- Capture a screenshot of a successful API test if the environment supports it.
- Clearly report incomplete work and missing dependencies.

## Important Rules
- Inspect the existing repository before making changes.
- Reuse existing database models, services, and AI configuration.
- Do not hardcode sample insights as real results.
- Do not fabricate statistics, trends, customer preferences, or test results.
- Do not make unrelated changes.
- Do not stop after providing recommendations; implement the feature in the repository.

## Expected Deliverable
A working Customer Insights feature that analyzes actual customer records and generates evidence-based insights about recurring issues, interaction patterns, feedback, transaction activity, and service opportunities while respecting privacy and data-access permissions.

Start by inspecting the repository, implement the feature, run the tests, and document the actual changes and results.
