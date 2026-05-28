# Entra ID Authentication & RBAC Analysis Lab

📅 March 2026  
✍️ Rui Almeida da Cunha  
📧 rui.almeidadacunha@gmail.com  

---

## Overview

This repository documents an identity and access management analysis focused on Microsoft Entra ID authentication concepts and Role-Based Access Control (RBAC) behaviour.

The objective is to understand how authentication identity (who you are) transitions into authorization decisions (what you can access), and how this relationship is implemented in enterprise IAM systems.

This work builds on endpoint authentication analysis and extends into cloud identity governance concepts used in Microsoft Entra ID.

---

## Scope of Analysis

This lab focuses on two core IAM domains:

### Authentication
- Identity verification process  
- Sign-in validation concepts in Entra ID  
- Credential-based identity confirmation  

### Authorization (RBAC)
- Role-based access control model  
- Assignment of roles to identities  
- Permission inheritance and access scope definition  

---

## IAM Model Interpretation

This analysis interprets IAM not as a static configuration system, but as a dynamic relationship between identity verification (authentication) and access decision enforcement (authorization).

In this model:

- Authentication establishes identity trust  
- RBAC defines permitted actions and resource boundaries  
- Identity governance ensures alignment between access and least privilege principles  

This mirrors Microsoft Entra ID architecture in enterprise environments.

---

## Key Concepts Demonstrated

- Identity vs access separation (authentication vs authorization)  
- Role assignment logic in RBAC systems  
- Least privilege enforcement principles  
- Enterprise IAM control structure interpretation  
- Relationship between identity lifecycle and access control  

---

## Cloud IAM Mapping (Microsoft Entra ID)

The RBAC model demonstrated in this lab maps directly to Microsoft Entra ID role assignment structures:

- Users represent identities  
- Roles represent access policies  
- Assignments define authorization scope  
- Conditional access policies influence access decisions  

This mapping supports understanding of how enterprise IAM systems enforce access governance across cloud environments.

---

## Security & IAM Relevance

This analysis demonstrates foundational understanding of how identity authentication translates into controlled access within enterprise systems.

It supports early-stage IAM roles focused on:

- Identity and access analysis  
- RBAC interpretation and support  
- Access governance assistance  
- Entra ID operational understanding  

---

## Outcome

This lab provides a structured interpretation of Microsoft Entra ID authentication and RBAC principles, establishing foundational understanding of how identity and access control interact in enterprise IAM environments.
