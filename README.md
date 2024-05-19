# cloudera_odbc_examples

## Connecting to a Cloudera Data Warehouse (CDW) Hive virtual instance
```
CDW exposes an SSL endpoint listening on port 443 and using a Transport Mode of HTTP. Please note that Kerberos is not required. Instead 
you authenticate to the endpoint using a username and password. The username and password is typically backed by an LDAP repository such
as Active Directory or freeIPA. There are number of certificates to download and reference in an ODBC client. The example described below
was deployed on a Mac laptop using homebrew to install the dependencies. 
```
![image](./images/download-cdw-hive-certs.001.png)
```
Assumming you have keytool installed and downloaded the certificate chain as a file and named it as truststore.jks, create a PEM file:
keytool -list -rfc -keystore truststore.jks | sed -ne '/-BEGIN CERTIFICATE-/,/-END CERTIFICATE-/p' > cdw-certs.pem

You should see multiple certificates in this file. Please also note that your /etc/hosts file on your ODBC client should be able to
resolve the virtual URLs exposed by CDW.
```
```
1. Download the Cloudera ODBC Driver for Hive at https://www.cloudera.com/downloads/connectors/hive/odbc/2-7-0.html
```
![image](./images/download-hive-odbc-driver.png)



