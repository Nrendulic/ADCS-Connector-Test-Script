AD CS Connector Setup Test Script

This bash script is designed to test the configuration and network connectivity of the AD CS Connector for Jamf Pro. It verifies that the necessary components are correctly set up and that communication between the components works as expected. This script is a modified version of the ADCS Connector Test Script from the Jamf GitHub alerted for greater usability.

Official Script:
Testing AD CS Connector with curl.sh: https://github.com/jamf/ol/tree/master/adcsc/Test

Purpose

The script helps to:

Test network connectivity to the AD CS Connector.
Verify that the computer or service account has the necessary permissions to request certificates from AD CS.
Provide a quicker testing process than running a full enrollment workflow in Jamf Pro.
Requirements

Operating System: macOS or Linux (Preffered)
Dependencies:
openssl
curl
Setup Instructions

Installation of AD CS Connector:
After installation, ensure you have the following:
client-cert.pfx: Client certificate file.
adcs-proxy-ca.cer: CA certificate file.
PFX/P12 password: The password obtained during the PowerShell installation process.
Script Configuration:
Place the client-cert.pfx and adcs-proxy-ca.cer files in the same directory as this script.
Assign the PFX password to the clientPfxPassword variable in the script.
Running the Script:
Update the script settings, including ADCS_CA_hostname, ADCS_CA_InstanceName, ADCS_CA_template, and CONNECTOR_HOSTPORT.
Execute the script in the terminal.
Script Overview

Settings: The script's settings include the hostname of the CA server, the instance name, the certificate template, and the paths to the necessary certificate files.
Procedure:
The script tests connectivity to the AD CS Connector and verifies the server and client certificates.
It creates a Certificate Signing Request (CSR) and sends it to the AD CS Connector.
It retrieves the signed certificate and combines it with the private key into a P12 file.
Important Notes

Security: The client certificate and password are sensitive information. Do not store or share them insecurely.
Testing Environment: This script is for testing purposes only. Ensure to reconfigure the setup for production use and regenerate the client certificates.
Disclaimer

This script is provided as-is without any warranty. The user assumes all risks associated with its use.
