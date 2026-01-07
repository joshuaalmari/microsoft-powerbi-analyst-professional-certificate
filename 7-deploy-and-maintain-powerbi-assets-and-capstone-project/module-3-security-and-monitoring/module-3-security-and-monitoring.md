# 🚀 Module 3: Security and Monitoring

This module covers the critical responsibility of a data analyst to safeguard information and monitor its consumption within the Power BI ecosystem. It explores the technical and administrative controls used to identify sensitive data, manage access through granular permissions and Row-Level Security (RLS), and automate insights via subscriptions and data alerts.

---

## 🛡️ 1. Data Security Foundations

Understanding the difference between regular and sensitive data is the first step in protection. Sensitive data includes any information that could damage a company’s reputation, finances, or stakeholder privacy (e.g., customer PII, financial records, or proprietary knowledge).

### Core Security Measures
* **Authentication:** The process of verifying a user's identity (proving they are who they say they are) before granting access to the platform.
* **Authorization:** The process of determining exactly what data or reports a verified user is permitted to interact with.
* **Encryption:** Scrambling data as it moves across the internet (in transit) or is stored on servers (at rest) so it cannot be deciphered if intercepted.
* **Data Masking:** Working with obscured versions of data (e.g., viewing only the last four digits of a credit card) to verify transactions without exposing full sensitive details.

---

## 🔗 2. Sharing via Links and Permissions

Link sharing allows for the rapid distribution of reports without transferring large files, but it requires careful permission management.

### Link Access Categories
* **People in your organization:** Anyone with a company email can open the report.
* **People with existing access:** Restricted to those who were previously granted permission.
* **Specific people:** Only individuals explicitly named by the sender can access the link.

### Sharing Permissions
* **Reshare:** Allows the recipient to share the report with other users.
* **Build:** Enables recipients to use the underlying dataset to build their own new reports or visuals (without altering the core source data).

---

## 🏷️ 3. Data Sensitivity Labels

Sensitivity labels are digital tags that categorize confidentiality levels and apply protective settings across Microsoft 365 products.

* **Personal:** Data for specific individuals; not intended for the wider organization.
* **Public:** Intended for wide public distribution (e.g., customer brochures).
* **General:** Internal company news or data with no specific sensitivities.
* **Confidential:** Sensitive departmental data requiring careful handling.
* **Highly Confidential:** Critical business innovations, research, or product designs.
* **Restricted:** Maximum secrecy, typically for executive data regarding mergers or contracts.

---

## 🔐 4. Dataset Permissions

Dataset permissions act as digital "locks and keys" to ensure the right people have access to the specific data needed for their job function.

| Permission | Capabilities |
| :--- | :--- |
| **Read** | Allows users to view reports and dataset settings without making changes. |
| **Build** | Enables users to construct new visuals and reports based on the dataset. |
| **Reshare** | Allows users to distribute specific datasets or reports to other permitted teams. |
| **Write** | Allows users to alter the actual dataset, correct errors, and restore/republish content. |
| **Owner** | The creator's role; grants full control over credentials, refresh schedules, and all permissions. |

---

## 🌐 5. Sharing Outside the Organization

Sharing with external partners requires unique configurations to maintain data integrity.

* **Licensing:** External users must have the appropriate **Power BI Pro** licenses, managed through the Microsoft 365 Admin Center.
* **External Sharing Settings:** Admin-level controls that authorize specific groups for external sharing and set link expiration times.
* **Report Embedding:** Using secure methods like "embed code" to add reports to external platforms while maintaining control over who sees the data.
* **Anonymization:** Replacing real data with pseudonyms in Power Query so external partners can analyze trends without seeing sensitive records.

---

## 🧱 6. Row-Level Security (RLS)

RLS ensures that different users see only the data rows relevant to their role, even when viewing the same report.

### Static vs. Dynamic RLS
* **Static RLS:** Uses fixed DAX filters for specific roles. For example, a role named "North America" is manually assigned a filter such as `[Region] = "North America"`.
* **Dynamic RLS:** Adjusts access in real-time based on the user's login. It uses the DAX functions `USERNAME()` or `USERPRINCIPALNAME()` to match the user's email with a column in the data table.

### Management Considerations
* **Performance:** RLS filters data in real-time, which can slow down data retrieval in very large datasets.
* **Maintenance:** Roles must be tested frequently and updated whenever organizational structures or access needs change.

---

## 🔔 7. Subscriptions and Data Alerts

Automation tools ensure that stakeholders stay informed without needing to fetch reports manually.

### Report Subscriptions
* **Function:** An automated system that sends scheduled snapshots of reports or dashboards as emails or notifications.
* **Configuration:** Users can set the frequency (daily, weekly, monthly) and the specific delivery time.

### Data Alerts
* **Requirement:** Alerts can only be set on **Gauges, KPIs, and Cards** that have been pinned as tiles to a dashboard.
* **Logic:** Users define a condition (Above or Below) and a numeric threshold. If the data crosses that point, an automated notification is sent.
* **Frequency:** Notification intervals can be set to "Every hour" or "Every 24 hours" depending on the urgency of the metric.
