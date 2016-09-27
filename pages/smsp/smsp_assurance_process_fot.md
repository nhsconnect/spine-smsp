---
title: SMSP Assurance Process FoT
keywords: reference
summary: "SMSP Assurance Process for First of Type"
sidebar: mydoc_sidebar
permalink: smsp_assurance_process_fot.html
folder: smsp
toc: false
---

## SMSP Assurance Process for First of Type

Overview of the test steps and evidence submission to reach FoT live deployment:

<div id="userMap">
<div class="content"><a href="smsp_test_tools.html"><div class="box box1"><b>Develop</b>: Solution</div></a></div>
<div class="arrow">→</div>
<div class="content"><a href="smsp_test_environments.html"><div class="box box2"><b>Test</b>: Autotest Manager</div></a></div>
<div class="arrow">→</div>
<div class="content"><a href="smsp_assurance_process_fot.html"><div class="box box3"><b>Test</b>: Path-to-live/Opentest</div></a></div>
<div class="arrow">→</div>
<div class="content"><a href="smsp_assurance_process_fot.html"><div class="box box4"><b>Review</b>: evidence submitted</div></a></div>
<div class="arrow">→</div>
<div class="content"><a href="smsp_assurance_process_fot.html"><div class="box box5"><b>Deploy</b>: First of Type</div></a></div>
<div class="clearfix"></div>
</div>

- **Develop**: this is the product development stage using the resources within this pack to understand both the technical and business requirements. At this stage it's also possible to access the opentest environment. At this stage the ITK supplier requirements must also be completed.
- **Test**: local testing of the solution using TKW Autotest Manager, executing the positive and negative tests against the client under test. The tool will auto-generate the test evidence for submission to NHS Digital, which will allow access into a path-to-live environment (INT)
- **Test**: integration positive test (only) against the path-to-live environment. This stage pipe-cleans the deployment process e.g. ensure that firewall configurations are understood.
- **Review**: the test evidence, the completed TOM, and ITK requirements spreadsheet is review. 
- **Deploy**: Deployment into first of type care organisation.
NB: these steps equate to the 'Complete ITK Assurance Artefacts' in the process flow below.


The following flow diagram shows the complete assurance process for first of type deployments.

{% include image.html file="client_process_fot.png" alt="Process for First of Type Deployments" caption="Process for First of Type Deployments" max-width="700" %}

{% include links.html %}
