

**Change Log**

| No   | Change Description     | Author | Version | Data       | Remark |
| ---- | ---------------------- | ------ | ------- | ---------- | ------ |
| 1    | Create Design V0.1 Doc | Kruan  | V0.1    | 2020.10.28 |        |



# Introduction

## Background

## Purpose and Scope

# Bussiness Overview

## Business Workflow 

### Product Registration

***Brief Introduction***

*This business is mainly to facilitate customer to **self-register** products in our system by UI, it includes the current **Singleton** and **GRM** product access methods.*

---

***Participating Role***

| No   | Role                | Operation                                                    |
| ---- | ------------------- | ------------------------------------------------------------ |
| 1    | Customer(Dev)       | - Product registration application and create new product request. |
| 2    | RS Product Reviewer | - Product registration Audit                                 |

---

***Bussiness Workflow***

```mermaid
graph LR
CR(Customer Register Product application)--> NP{Product not found in RS}
NP --> |N| CRI[Submit Registration]
NP --> |Y| CNP[Create New Product]
CNP -->|create new product finished| CR
CRI --> PV[Product Registration View]
PV --> AR{Auit Result}
AR --> |Not pass| CRI
AR --> |Pass| CRS(Register Success)

```



**Notes:**

- *It is not allowed to deleted product registration order and modify some fields after product registration.*
- *Product registration in the **init** state allows modification and deletion.*



---

***Status Set***

```mermaid
stateDiagram
	[*] --> init
	init --> waitingAudit
	waitingAudit --> init
	waitingAudit --> Audited
	Audited --> [*]
	
```

---

***Module Interaction***

```mermaid
  sequenceDiagram
    Title: Product Registration Process
    
		USER->>+API GW: 1.Register product()
		API GW->>-API GW:2.APIFilter
		Note over API GW: Check logged in
		API GW->>+CRM: 3.Register product()
		
		CRM->>CRM: 4.Save the product information in the db
		CRM-->>-USER: 5.Return message
		USER->>+CRM: 6. Review product()
		CRM->>CRM: 7.Handle the request
		CRM->>-RS Core SERVICE: 8.RegisterProduct()
		RS Core SERVICE->>+RS Core SERVICE: 9.Handle the request
		CRM->>+GRM: Sync Product Info
		GRM-->>-CRM: Return Result
		CRM->>+Singleton: Push Project Info 
		Singleton-->>-CRM: Return Result
```



### Resource Management

***Brief Introduction***

*This service is mainly used to track the whole process of this batch of translations starting from the user initiating a batch of resource translation request.*

---

***Participating Role***

| No   | Role          | Operation                       |
| ---- | ------------- | ------------------------------- |
| 1    | Customer(Dev) | - RS collection request         |
| 2    | Vendor        | - Review transltations from Grm |
| 3    | QE            | - G11n test                     |

---

***Business Workflow***

```mermaid
graph LR
RS(Collect Rs Batch Request) --> Alpha(Waiting for GRM Feedback: Alpha)--> VendorReivew(GRM Feedback:VendorReview)
Beta(GRM Feedback: Beta)  --> RC(G11n test)
VendorReivew --> RR{Review Result}
RR --> |pass| Beta
RR --> |Not pass| Alpha
RC --> TR{Test Result}
TR --> |Pass| Release(Release Our Translations:Release)
TR --> |Not pass| Beta

```

**Notes:**

- *Need to consider whether to support users to cancel translation halfway*
- *Each process node adds corresponding reminders and automatically creates corresponding Jira tasks.*



---

***Status Set***

```mermaid
stateDiagram
	[*] --> Alpha
	Alpha --> vendorReview
	vendorReview --> Alpha
	vendorReview --> Beta
	Beta --> RC
	RC --> Beta
	RC --> Release
	Release --> [*]

```



***Module Interation***

```mermaid
sequenceDiagram
	title: Resource Collection Management
	User->>+CRM:Send Resouce Translation Request
	CRM->>+RS Core Service: Sync Resource Info
	RS Core Service-->>-CRM: Return Result
	CRM ->>+GRM: Send Translation request
	GRM ->>-GRM: handle Translation Process
	GRM -->>CRM: Push Translation Result to CRM
	CRM ->>+JIRA GW: Create Test JIRA Task
	JIRA GW -->> CRM: Return Result
	JIRA GW ->>-JIRA GW: Watch JIRA Task Status
	JIRA GW ->> CRM: Sync JIRA Task Status Changes
	CRM ->> -RS Core Service: Sync Resource Info
	RS Core Service ->> RS Core Service: Sync Translation Info
	RS Core Service -->> CRM: Return Result

```



### 





