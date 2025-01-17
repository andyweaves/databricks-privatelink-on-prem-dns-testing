### Overview
- An example setup to replicate DNS forwarding from an on-prem Windows environment to an inbound resolver in AWS, with an architecture based on JD Braun's awesome [Isolake](https://github.com/JDBraun/isolake). A high level architecture diagram can be found below (note that a Databricks workspace, Unity Catalog, compute plane etc are all also created, in the diagram we're focussing on what's unique about this setup).

-----------
### Disclaimer
This Terraform code is provided as a sample for reference and testing purposes only. Please review and modify the code according to your needs before using it in your test environment.

**NOTE:** The practice of passing credentials through Terraform input variables is intended solely for rapid testing purposes. 
- It should NOT be implemented in production ennvironment or any other higher-level environments.
- For enhanced security, it is recommended to use more secure methods like AWS Secret Manager or environment-specific secrets for storing credentials.
-----------

### Deployment Steps

1. Ensure that Terraform is installed and available on your path
2. Clone this repo
3. cd into the [tf](tf/) directory
4. Copy the [tf/isolake.tfvars.example](tf/isolake.tfvars.example) file and complete as per your target environment
5. Review the [tf/isolake.tf](tf/isolake.tf) file and updated as per your target environment
6. Set up your AWS credentials
7. Run ``terrform init`` / ``terraform plan`` / ``terraform apply``
8. Follow the setup steps in the [pdf/](pdf) directory (NB - Bind DNS is the recommended approach. See the PDF files for more information)

### High Level Architecture

![image](https://github.com/andyweaves/databricks-privatelink-on-prem-dns-test/assets/43955924/bd1b5c38-ffa3-4d74-87a7-ba48cf1d860a)
