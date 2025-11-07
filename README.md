[Quick Start](#quick-start) |
[Postman Collection](#postman-collection) |
[Next Steps](#next-steps) |
[Technical Notes](#technical-notes)

<h1 style="text-align:center; margin-bottom:0;">BerryWave Software</h1>
<h2 style="text-align:center; margin-top:0;">API for EDI</h2>

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

## Quick Start

### API Playground

This project provides a runnable "playground" copy of the application. It includes all user interfaces
and uses pre-defined responses to simulate EDI processing. You can use the same Postman collection
that comes with the licensed version, making it easy to explore the API without a trial license.

### Downloading the Project


You may either **clone the Git repository** or **download the ZIP archive**, 
Whichever you prefer.

Once downloaded, the application's **home directory** contains:

- **Runnable JAR:** `berrywave.playground-1.0.0.jar` 
- **Configuration file:** `configuration.properties`
- **Postman assets:** `postman` directory containing `postman_collection.json` and `berrywave.postman_environment.json`
- **EDI models:** `model-directory` with sample EDI models
- **EDI samples:** `edi-samples` with sample EDI files

(note: if you are experiencing issues with the .jar file when downloading the ZIP archive, you may alternatively download it [here](https://drive.google.com/file/d/1rijOwZlvFH3sVZbdtA1ZIhPXPoqMmFlM/view?usp=drive_link))

### Running the Application

**Prerequisite:** Java 21 or later. Verify with:

`java --version`

By default, the application listens on port 8080.
To use a different port, edit configuration.properties.

*We can now start the application on Mac without command line! Probably could Windows too.*

Start the application with:

`java -jar berrywave.playground-1.0.0.jar`

### Home page

Visit the home page in your browser:

`http://localhost:8080`

The home page shows license information and provides quick links to key features and documentation.

### OpenAPI/Swagger documentation

Access the API documentation:

`http://localhost:8080/docs`

This documentation includes all endpoints, parameters, and response examples.

### Your first EDI request

Use the browser to make a request that transforms an EDI file to JSON:

`http://localhost:8080/transformFromEdi&input=edi-samples%2F850.edi`

* The 850.edi file is in the edi-samples directory. Fully-qualified paths are supported with "%2F" representing "/".
* In the playground, responses are simulated (canned) rather than generated from the EDI input.
* For more variations and examples, refer to the Swagger documentation and Postman collection.

## Postman Collection

Import `berrywave.postman_environment.json` and `berrywave.postman_collection.json` into Postman
to load a ready-made collection of API requests.
These requests mirror the endpoints described in the Swagger documentation,
making it easy to experiment with parameters, explore different options,
and review the responses directly within Postman.

## Next Steps

- **Free Trial:** Companies can request a free 10-day trial of the full application,
  allowing you to explore features and confirm high performance with your own data.

- **Licensing:** Licenses are issued per company with a defined expiration date.
  They allow installation on multiple servers and unlimited usage within the license period.

- **Feedback:** We welcome your feedback on the API Playground, including questions, suggestions, or ideas for new
  features.

## Technical Notes

- **Network:** Listens on port 8080 by default (configurable).
  No other ports are opened, and no outbound connections are made.
  Works well behind restrictive firewalls.

- **Scalability & Availability:** Multiple instances can run on different servers for load balancing and fault
  tolerance.
  Requests do not require "sticky" sessions.

- **Filesystem Access:** Requires read access to the home directory and its subdirectories.
  API operations also require write access to the files or directories they reference.