![Banner image](images/github-header-banner.png)
[Quick Start](#quick-start) |


### API Features

The API for EDI is available both as the Community Edition,
freely available for commercial use with features summarized in the table below,
and the full-featured Enterprise Edition
available with license from BerryWave Software.

|                     | Feature                                                                                               | Community Edition | Enterprise Edition |
|:--------------------|:------------------------------------------------------------------------------------------------------|:-----------------:|:------------------:|
| **EDI Standards**   | X12                                                                                                   |         ✅         |         ✅          |
|                     | EDIFACT                                                                                               |         ✅         |         ✅          |
|                     | HL7 v2.x                                                                                              |         ❌         |         ✅          |
|                     | TRADACOMS                                                                                             |         ❌         |         ✅          |
| **EDI → JSON**      | Convert without loss of EDI data                                                                      |         ✅         |         ✅          |
|                     | Human-readable indented JSON or compact JSON output                                                   |         ✅         |         ✅          |
|                     | Represent segment loops in JSON                                                                       |        ✅†         |         ✅          |
|                     | Alternate JSON representations                                                                        |         ❌         |         ✅          |
| **JSON → EDI**      | Produce EDI from JSON (reverse of EDI → JSON)                                                         |         ❌         |         ✅          |
| **EDI ↔ XML**       | Analogous to JSON support                                                                             |         ❌         |         ✅          |
| **Healthcare**      | Create 277 Claim Acknowledgments from 837 Claims, accepting all claims                                |         ✅         |         ✅          |
|                     | Create 277 Claim Acknowledgments from 837 Claims, using accept/reject details in JSON                 |         ❌         |         ✅          |
|                     | Create 835 Payment Advice from 837 Claims using payment details in JSON                               |         ❌         |         ✅          |
| **Supply Chain**    | Create 855 Purchase Order Acknowledgment from 850 Purchase Order, accepting all items                 |         ✅         |         ✅          |
|                     | Create 855 Purchase Order Acknowledgment from 850 Purchase Order, using accept/reject details in JSON |         ❌         |         ✅          |
|                     | Create 856 Ship Notice from 850 Purchase Order, using shipping details in JSON                        |         ❌         |         ✅          |
|                     | Create 824 Application Advice from 810 Invoice, confirming acceptance                                 |         ❌         |         ✅          |
|                     | Create 824 Application Advice from 810 Invoice, using accept/reject details in JSON                   |         ❌         |         ✅          |
| **Acknowledge EDI** | Generate standards-based EDI acknowledgments (997/999/CONTRL)                                         |         ✅         |         ✅          |
| **Validate EDI**    | Detailed syntax and compliance validation                                                             |         ❌         |         ✅          |
|                     | Compliance errors reflected in 997/999/CONTRL                                                         |         ❌         |         ✅          |
|                     | Compliance report                                                                                     |         ❌         |         ✅          |
| **Split EDI**       | Split multi-transactional EDI into a series of single-transaction EDI files                           |         ❌         |         ✅          |

† Community Edition supports this feature for selected document types:

- **837P Healthcare Claim, Professional** (version 005010)
- **850 Purchase Order** (commonly deployed versions 004010, 004030, 004060, and 005010)

Enterprise Edition supports all document types.