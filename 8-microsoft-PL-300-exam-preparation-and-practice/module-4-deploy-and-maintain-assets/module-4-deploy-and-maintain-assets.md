# 🏢 Module 4: Deploy and Maintain Assets

This module focuses on the operational phase of the Power BI lifecycle, ensuring that data assets are collaboratively managed, securely distributed, and maintained with a focus on organizational integrity.

---

## 👥 1. Power BI Workspaces and Collaboration

Workspaces are specialized "team rooms" that act as more than just folders; they are centralized hubs where analysts collaborate on dashboards, reports, and datasets to align teams like Sales, Marketing, and Customer Service.

### Workspace Roles and Permissions
Access is managed through four roles to ensure efficient teamwork and security:

* **Admin:** Has full control, including the ability to add or remove users (including other admins) and the authority to delete the workspace entirely.
* **Member:** Can add other members (but not admins), publish, update, and share content. They act as the primary managers of the workspace's daily output.
* **Contributor:** Designed for content creators. They can create, edit, and delete reports and datasets within the workspace but cannot manage users or share content with others.
* **Viewer:** The most restricted role, limited to reading and interacting with reports and dashboards without access to the underlying datasets.

---

## 🔐 2. Security and Governance at Scale

Securing data at the row level and managing granular permissions ensures that sensitive information remains confidential while providing valuable insights to authorized personnel.

### Row-Level Security (RLS)
RLS provides a way to control data access at the row level so that users only see information relevant to their department or role.
* **Static RLS:** Involves creating fixed roles and assigning specific data rules to those roles.
* **Dynamic RLS:** Uses DAX expressions (e.g., `USERPRINCIPALNAME`) to adjust data access in real-time based on the user's specific login identity.

### Permission and App Management
* **Dataset Permissions:** Beyond workspace roles, you can selectively manage permissions (Read, Build, Reshare) at the dataset level to allow others to create new reports from your data.
* **Power BI Apps:** A professional way to package workspace content. Apps allow for "Audience Management," where you can share specific sets of content with the entire organization or customize access for specific groups.

---

## 🛠️ 3. Maintaining Data Integrity and Governance

As an organization grows, maintaining a "single source of truth" requires tools that track data dependencies and evaluate the consequences of changes.

* **Lineage View:** A visual tool that maps the entire data journey, showing the connectivity between data sources, datasets, and the reports or dashboards they power.
* **Impact Analysis:** Before updating or changing a dataset, this tool identifies which workspaces, reports, and dashboards across the tenant will be affected, helping to prevent broken visuals.
* **Dataset Governance:** The ongoing process of auditing and maintaining datasets to ensure they remain consistent, standardized, and accurate for long-term business intelligence.

---

## 🔄 4. Deployment Lifecycle and Certification

The module concludes by reinforcing the importance of the complete Power BI lifecycle—from ingestion to deployment.

* **Practice and Revision:** Mastering these skills involves hands-on experience with sample datasets and regular auditing of existing assets.
* **PL-300 Alignment:** Understanding these deployment and maintenance strategies is a core requirement for becoming a certified Power BI Analyst and handling complex, real-world analytical challenges.
