---
title: SMSP Capabilities
keywords: capabilities
summary: "SMSP Capabilities"
sidebar: mydoc_sidebar
permalink: smsp_capabilities.html
folder: smsp
---
Presently the NHS Digital Spine Mini Service capabilities are (a) the foundation of the service being an ITK compliant web service, and (b) the ITK compliant demographics service. 

More detailed explanation of each capability can be under the capability packs drop down. Below is a brief description and a link to 

## Foundations

The ITK Spine Mini Service functional specifications provide the basis on which all ITK capabilities are built, for example canonical message structure and common behaviours for error and exception handling. More details can be found under the 'Capability Packs' drop down menu - [Foundations](foundations_intro.html)

## Demographics

The first capability provided by the NHS Digital Spine Mini Service is read-only access in the Demographics Service, to access a subset of patient demographic data.

Within the pack the ‘PDS – Spine Mini Services Provider Requirements-v1.0.pdf‘ document contains the details of the information model shown above. It also explains the provider requirements, the request message descriptions, plus behaviors of wildcards and data type format. Note: NHS Digital have implemented the Spine Mini Service as a central solution.

The pack contains the ‘PDS – Spine Mini Services Client Requirements-v1.0.pdf‘, a document which the Client developer will need to read to ensure the application meets the requirements within.

The final document within the pack which a developer should read is the ‘SMSP Response Code – v1.0.xls’ spreadsheet. Which as the name suggests contains the general service message response codes and PDS specific ones. An example being a successful query would contain an SMSP-0000 Success code
<value codeSystem=”2.16.840.1.113883.2.1.3.2.4.17.285″ code=”SMSP-0000″/>

More details can be found under the 'Capability Packs' drop down menu - [Demographics](demog_intro.html)

{% include links.html %}
