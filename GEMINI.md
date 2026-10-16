# Aribot

Aribot is Ayurak's security and compliance platform. The `aribot` MCP server exposes the signed-in
user's own Aribot workspace: threat-model diagrams and their threats, cloud compliance posture from the
daily scans, code-security and shadow-AI findings, AI-agent governance, and tracker tickets.

- Sign-in uses OAuth against the user's Aribot account; every call is scoped to their company.
- Prefer read tools (`compliance_status`, `get_cloud_compliance`, `list_diagrams`, `get_diagram_summary`,
  `get_code_findings`, `get_framework_coverage`) to answer questions.
- Tools that change state (`apply_remediation`, `file_threat_tickets`, `assign_threat`,
  `comment_threat_on_change`, `generate_architecture`, scans) act on the user's real workspace —
  confirm with the user before calling them.
- Report figures exactly as returned; when a tool returns no data, say so rather than estimating.
