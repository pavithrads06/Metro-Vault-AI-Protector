Metro Vault AI Protector
Metro Vault AI Protector is an enterprise-grade IoT safety application built on the ServiceNow Platform (App Engine Studio). It is designed to monitor underground high-voltage power transformer vaults, utilizing Generative AI to predict failures and prevent catastrophic infrastructure incidents.

🚀 Key Features
Intelligent IoT Ingestion: Securely processes real-time sensor telemetry via a custom Scripted REST API.

Operational Cost-Control: Implements a "Short-Circuit" logic that filters routine environmental data, bypassing heavy AI processing and reducing external API costs by ~80%.

Resilient Architecture: Utilizes MD5 payload hashing for data idempotency, preventing database bloat and processing loops from hardware malfunctions.

AI-Driven Diagnostics: Orchestrates asynchronous analysis using OpenAI (gpt-4o-mini) to identify critical risk vectors.

Deterministic Safety Fallback: Features a built-in Regex-based emergency engine, ensuring 100% monitoring uptime even if the AI service experiences outages.

🛠 Technical Stack
Platform: ServiceNow (Scoped Application)

Development: App Engine Studio (AES)

Integration: RESTMessageV2, Scripted REST APIs

Automation: Flow Designer, ECC Queue (Async Business Rules)

Security & Data: GlideDigest (MD5), Scoped Dictionary Tables

External API: OpenAI (gpt-4o-mini)

🏗 System Architecture
Ingestion: IoT sensors push JSON telemetry via HTTPS.

Validation: Scripted REST API performs MD5 hashing to verify data uniqueness.

Efficiency Tier: If metrics are within safe bounds, data is logged to the Telemetry Vault Logs table and the process exits.

AI Orchestration: Anomalies trigger an Asynchronous Business Rule that dispatches data to OpenAI.

Emergency Response: If the AI indicates a critical state—or if the AI service is unreachable—the system automatically flags the incident as Priority 1 and triggers a mobile dispatch to field technicians.
