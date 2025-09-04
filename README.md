# LIMS API Documentation and Schemas

This repository contains the official **schemas, sample payloads, and documentation** for the **LIMS–PCR Interoperability API**, developed under the **National AIDS & STI Control Programme (NASCP)**.  

The API supports the **exchange of laboratory sample and result data** between:
- **Sending Facilities / EMRs**  
- **PCR Laboratories (LIMS)**  

---

## 📘 Overview

The API facilitates:
1. **Manifest Submission** – Sending sample manifests (VL & EID) from facilities to PCR labs.  
2. **Result Exchange** – Returning Viral Load (VL) and Early Infant Diagnosis (EID) results from labs.  
3. **Result Requests** – Facilities querying PCR labs for results by `manifestID`.  
4. **Notifications / Feedback** – Handling issues such as mismatched IDs, rejected samples, and missing results.  

---

## 📂 Repository Structure

```bash
lims_api_documentation_and_schema/
│
├── VL_manifest-schemaV2.json                # Viral Load (VL) manifest schema
├── EID_manifest-schemaV2.json               # Early Infant Diagnosis (EID) manifest schema
├── result_schema_V2.json                    # Viral Load result response schema
├── VL_result Response.json                  # Unified schema for VL/EID result responses
├── EID_result_response_schema.json          # EID result response schema
├── VL_EID_ResultRequest.json                # Schema for requesting results (VL/EID)
│
├── VL_result_response_sample_payload.json   # Sample VL result response (10 scenarios)
├── EID_result_response_schema_sample_payload.json  # Sample EID result response
├── EID_manifest_schema_sample_payload.json  # Sample EID manifest payload
├── VL_EID_result_request_sample_payload.json       # Sample result request payload
│
├── notification_schema.json                 # Schema for feedback/notification issues
├── notifixation_schema_sample_payload.json  # Sample notification payload
│
├── LIMS-EMR_Dictionary_and_concepts_V2.xlsx # Data dictionary and concept mappings
│
└── README.md                                # Documentation (this file)
```
📑 Schema Highlights
1. Manifests

VL Manifest: VL_manifest-schemaV2.json

EID Manifest: EID_manifest-schemaV2.json

Each manifest contains:

manifestID

Sending/Receiving facility identifiers

Patient and sample details

Courier/packaging information

2. Result Exchange

VL Results: result_schema_V2.json, VL_result Response.json

EID Results: EID_result_response_schema.json

Fields include:

Patient identifiers

Sample identifiers and PCR lab numbers

Test results (quantitative for VL, qualitative for EID)

QA metadata (testedBy, approvedBy)

Transfer details (for secondary PCR labs)

3. Result Requests

Schema: VL_EID_ResultRequest.json

Allows facilities to request results for a manifest.

4. Notifications

Schema: notification_schema.json

Sample: notifixation_schema_sample_payload.json

Covers feedback codes such as:

MISSING_RESULT

WRONG_RESULT

PATIENT_ID_MISMATCH

SAMPLE_REJECTED

📊 Sample Payloads

This repository includes realistic sample payloads for manifests, results, result requests, and notifications, to guide implementers.

VL result scenarios include: valid tests, insufficient samples, haemolysis, leakage, and transfers.

EID samples include: positive, negative, indeterminate, and breastfeeding condition logic.
