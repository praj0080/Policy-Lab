
# Azure Policy Lab – Cloud Governance Gone Rogue
## 🎯 Summary
In this lab, you are going to learn how to achieve structure, security and compliance of an Azure environment by the use of **Azure Policy**. When I became a new Cloud Security Engineer at MapleTech Solutions, the role I was given was to apply guardrails to block uncontrolled deployments, tagging regulations and protection against public IP. The solution was achieved through three custom polices which are put in an initiative and accordance with a specific resource group.
---
## 🔒 Policies Implemented

### 1. **Only-CanadaCentral**
- **Effect**: Deny
- **Description**: Prevents the creation of any resource which is not being deployed in the **Canada Central** region.
-  Purpose: Violates geographic compliances and data residency regulations.

### 2. **Require-ProjectName-Tag**
- **Effect**: Deny
- **Description**: Reprohibits the creation of any resource without carrying the essential tag: `ProjectName`.
- Purpose: Makes sure that it is tagged to track the cost, governance, and resource ownership.

### 3. **Deny-Public-IP**
- **Effect**: Deny
- **Description**: Prevents the generation of public IP address.
- Purpose: Overexposure to the internet, which worsens the cloud environment security posture, is diminished.
Issues & things that were learned

### 4.The challenges are as follows:
Got JSON validation errors when I had no `policyRule` block or when I mis-formed it.
At first, it was a wrong usage of fields such as `type` instead of `field: "type"` not passed to the parser.
Probed applying tag enforcement in an area not in scope of the initiative which resulted in unanticipated passes.

### Lessons Learned
policies in JSON must always wrap the `policyRule` within the parent block of `properties`.
- At the time of assignment, validate items would be range of policy and mode.
Consistently and at scale manage numerous policies with the use of initiatives.
Azure Policy is a strong management tool that needs to be very well-structured and scoped.

---
### Demo Video Link.

This lab was a lesson on the importance of proactive governance and the authority that can be pursued through automation to ensure compliance over manual governance.

