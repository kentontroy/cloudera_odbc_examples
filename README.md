# cloudera_odbc_examples

## Connecting to a Cloudera Data Warehouse (CDW) Hive virtual instance

CDW exposes an SSL endpoint listening on port 443 and using a Transport Mode of HTTP. Please note that Kerberos is not required. Instead 
you authenticate to the endpoint using a username and password. The username and password is typically backed by an LDAP repository such
as Active Directory or freeIPA. There are number of certificates to download and reference in an ODBC client.




keytool -list -rfc -keystore truststore.jks | sed -ne '/-BEGIN CERTIFICATE-/,/-END CERTIFICATE-/p' 
