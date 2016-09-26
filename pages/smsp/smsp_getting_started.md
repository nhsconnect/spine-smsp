---
title: SMSP Getting Started
keywords: getting started
summary: "SMSP Getting Started"
sidebar: mydoc_sidebar
permalink: smsp_getting_started.html
folder: smsp
---

## Quickstart for accessing the Demographics Spine Mini-Service

Traditionally spine integration meant dealing with both synchronous and asynchronous invocation patterns, with asynchronous necessitating the development of a message handling system (MHS) and having the adding complexity of using ebXML. To learn the implementation requirements, developers had to access the External Interface Specification (EIS) and then the Message Implementation Manual (MiM). This presents a considerable learning curve, when in many cases the use cases only necessitated accessing a subset of NHS demographics data e.g. the NHS number.

ITK Spine Mini Services have reduced complexity by using only synchronous SOAP ITK web service calls, constrained to 5 specific operations:

* verifyNHSNumber
* getNHSNumber
* getPatientDetailsByNHSNumber
* getPatientDetailsBySearch
* getPatientDetails

The Information model for these calls the associated responses in shown below:
{% include image.html file="SMSP_Info_Model.png" alt="smsp info model" caption="Spine Mini Services Information Model" %}

## Step 1 – Functional requirements

The ITK Spine Mini Service functional specifications are published on TRUD – https://isd.NHS Digital.gov.uk/trud3/user/authenticated/group/0/pack/30/subpack/126/releases

Within the pack the ‘PDS – Spine Mini Services Provider Requirements-v1.0.pdf‘ document contains the details of the information model shown above. It also explains the provider requirements, the request message descriptions, plus behaviors of wildcards and data type format. Note: NHS Digital have implemented the Spine Mini Service as a central solution.

The pack contains the ‘PDS – Spine Mini Services Client Requirements-v1.0.pdf‘, a document which the Client developer will need to read to ensure the application meets the requirements within.

The final document within the pack which a developer should read is the ‘SMSP Response Code – v1.0.xls’ spreadsheet. Which as the name suggests contains the general service message response codes and PDS specific ones. An example being a successful query would contain an SMSP-0000 Success code
<value codeSystem=”2.16.840.1.113883.2.1.3.2.4.17.285″ code=”SMSP-0000″/>
 
## Step 2 – Message Specification

The ‘PDS Mini Services Domain Message Specification’ is also published on TRUD – https://isd.NHS Digital.gov.uk/trud3/user/authenticated/group/41/pack/34/subpack/142/releases

The message specification contains all the details of the SOAP message requests and responses. It also includes the wsdl file (PDSMiniServices-v1-0.wsdl under \schema\wsdl), and some specific message examples under the ‘Payload’ column. It should be noted that the wsdl file has not been created for importing into frameworks capable of automatically building proxy classes.

ITK SOAP Messages contain a number of layers, as detailed below to:
{% include image.html file="SOAP_Message.png" alt="SOAP Message" caption="SOAP Message" %}

The ‘Payload’ detailed within the message specification refers to the Payload shown within the diagram above, which is a child element within the distribution envelope.

So what does the diagram actually look like in XML? The extract below (click to zoom) shows the SOAP Envelope, the SOAP Head, SOAP Body, and within the body (under the itk namespace) the ITK Distribution Envelope. The distribution envelope is used within all ITK SOAP Web Service calls, containing a header with the audit identity (the accredited system identifier provided during the endpoint registration process, linked to the calling organisations’ ODS code).
{% include image.html file="XML_Request_Header_and_DE.png" alt="XML SOAP Request Head and Distribution Envelope" caption="XML SOAP Request Head and Distribution Envelope" max-width="700" %}


## Step 3  – Transport connection

The ITK Spine Mini Service uses TLS MA (mutual authentication) to secure the connection between the client and central provider. When an endpoint is registered you will be provided with a PKCS#12 file containing the endpoint certificate, sub CA, and CA certs. This certificate is used to create the mutually authenticate connection with the service endpoint.
 
## Step 4 – Quick Test

This quick test assumes access to NHS Digital [Opentest](http://systems.hscic.gov.uk/ddc/oats/opentestinfo.pdf) or one of the Path-to-live environments (details can be found [here](http://www.assurancesupport.digital.nhs.uk/downloads) - N3 link required), using a template of the [getNHSNumber message](smsp_getNHSNumber.html) and curl to access the service.

Firstly we convert the NHS Digital provided PKCS#12 file (for a specific environment) into a PEM, for use with curl:
openssl pkcs12 -in pkcs_filename.p12 -out pem_filename.pem -nodes -clcerts

Using this file getNHSNumber.xml which contains a test patient example from the opentest  environment, execute the following curl command, substituting the certificate name and message endpoint (Opentest url shown in example). Note: the patient search details may need to be altered depending on the environment being accessed.

$ curl -i -X POST -H “SOAPAction: urn:nhs-itk:services:201005:getNHSNumber-v1-0” -H “content-type: text/xml” –E pem_filename.pem -d @getNHSNumber.xml -k https://192.168.54.6/smsp/pds

Note: there are some variations in curl 7.43.0 on OS X, this is a working command line:

$ curl -X POST -H SOAPAction:urn:nhs-itk:services:201005:getNHSNumber-v1-0 -H content-type:text/xml -E p12_filename.p12:Password -d @getNHSNumber.xml -k https://192.168.54.6/smsp/pds

This will return:

```xml
HTTP/1.1 200 OK
Server: nginx/1.10.1
Date: Wed, 27 Jul 2016 13:07:20 GMT
Content-Type: text/xml
Content-Length: 1662
Connection: close
<?xml version=’1.0′ encoding=’UTF-8′?>
<soap:Envelope xmlns:soap=”http://schemas.xmlsoap.org/soap/envelope/” xmlns:wsa=”http://www.w3.org/2005/08/addressing” xmlns:wsu=”http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd” xmlns:wsse=”http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd” xmlns:xsi=”http://www.w3.org/2001/XMLSchema-instance” xmlns:itk=”urn:nhs-itk:ns:201005″ xmlns:hl7=”urn:hl7-org:v3″><soap:Header><wsa:MessageID>0D355CFC-53FB-11E6-9B40-6C3BE5A63FA4</wsa:MessageID><wsa:Action>urn:nhs-itk:services:201005:getNHSNumber-v1-0Response</wsa:Action></soap:Header><soap:Body><itk:DistributionEnvelope><itk:header service=”urn:nhs-itk:services:201005:getNHSNumber-v1-0Response” trackingid=”0D355F90-53FB-11E6-9B40-6C3BE5A63FA4″><itk:manifest count=”1″><itk:manifestitem id=”uuid_0D26BF4E-53FB-11E6-9B40-6C3BE5A63FA4″ mimetype=”text/xml” profileid=”urn:nhs-en:profile:getNHSNumberResponse-v1-0″ base64=”false” compressed=”false” encrypted=”false”/></itk:manifest></itk:header><itk:payloads count=”1″><itk:payload id=”uuid_0D26BF4E-53FB-11E6-9B40-6C3BE5A63FA4″><getNHSNumberResponse-v1-0 xmlns=”urn:hl7-org:v3″ moodCode=”EVN” classCode=”OBS”><id root=”0D26BF4E-53FB-11E6-9B40-6C3BE5A63FA4″/><code codeSystem=”2.16.840.1.113883.2.1.3.2.4.17.284″ code=”getNHSNumberResponse-v1-0″/><value codeSystem=”2.16.840.1.113883.2.1.3.2.4.17.285″ code=”SMSP-0000″/><subject typeCode=”SBJ”><patient classCode=”PAT”><id root=”2.16.840.1.113883.2.1.4.1″ extension=”9473480032“/></patient></subject></getNHSNumberResponse-v1-0></itk:payload></itk:payloads></itk:DistributionEnvelope></soap:Body></soap:Envelope>
````

The returned NHS number is 9473480032.

If you require any further implementation guidance please contact – [itkaccreditation@nhs.net](mailto:itkaccreditation@nhs.net)

{% include links.html %}
