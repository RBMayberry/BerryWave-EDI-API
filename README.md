![Banner image](images/github-header-banner.png)
![Java Version](https://img.shields.io/badge/Java-21%2B-orange)
![License](https://img.shields.io/badge/License-Community-blue)
![Platform](https://img.shields.io/badge/Platform-Linux%20%7C%20macOS%20%7C%20Windows-lightgrey)

[Quick Start](#quick-start) | [Technical Notes](#technical-notes)

BerryWave Software delivers a robust REST API that brings enterprise-grade EDI processing
directly into your environment — no cloud uploads, no data exposure, no limits.

<https://www.berrywave-edi.com/>


### Seamless EDI Integration

Easily integrate with your existing orchestration or automation tools to handle complex EDI workflows
for X12 and EDIFACT standards.

### Key Features

* Convert EDI to JSON or XML — and back again
* Split multi-transaction EDI files into individual documents
* Validate compliance and detect errors efficiently
* Acknowledge receipt and compliance results

### Proven in Production

While the API is new, the EDI engine behind it has powered mission-critical systems across industries including:

* Healthcare
* Retail
* Supply Chain
* Finance

### On-Premise. Secure. Scalable.

* Quick, one-step installation on Linux, Windows, or macOS
* Requires only a Java JRE — no extra dependencies
* Keeps all data within your secured environment
* Eliminates large file transfers to and from the cloud
* Scales effortlessly with your business volume

### Community and Enterprise Editions

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

## Quick Start

### Download the Community Edition

Use the Releases section for this project to select and download the runnable jar asset for the latest release.
For example, `berrywave.api-1.1.6.jar`.
You may use the SHA-256 checksum to confirm that your downloaded copy is complete and unchanged.

### Running the Application

**Prerequisite:** Java 21 or later. Verify with:

```sh
java --version
```
Start the application with:

```sh 
java -jar berrywave.api-1.1.6.jar
````

### Configuring the Port
The application creates an `application.yml` file in the current directory if one does not already exist.
By default, the application listens on port 8080.
To use a different port, edit application.yml.

### Home page

Visit the home page with your browser:

```
http://localhost:8080/berrywave/v1
```

The home page confirms the edition (Community or Enterprise) and license status
and provides quick links to key features and documentation.

### API documentation

```
http://localhost:8080/berrywave/v1/api
```

### Postman Collection

A Postman collection is provided in the project so that you can quickly import the collection
and use Postman to execute a series of requests to the API.


