--- 
title: SMSP Target Operating Model
keywords: assurance
summary: "SMSP Target Operating Model"
sidebar: mydoc_sidebar
permalink: smsp_tom.html
folder: smsp
toc: false
---

## SMSP Target Operating Model
The purpose of the Target Operating Model (TOM) is to inform and assist deploying organisation with the implementation of SMSP integrated systems within their local environment. In particular, it provides an assessment framework of their responsibilities in terms of ensuring that their local systems meets the technical, IG, Clinical safety, and functionality required for the business context.

The TOM is currently presented in a form of a spreadsheet, with the worksheet broken into the logical assessment sections.

The TOM is typically used in two phases:
- Phase 1 the usage and settings information provided to NHS Digital for approval.
- Phase 2 the actual assessment phase conducted by the supplier and the deploying organisation.

Note: once a complete assessment has been performed by a deploying Organisation and supplier, the TOM will typically remain largely unchanged (in terms of the risks/mitigations identified) for subsequent deployments, hence new deployments will simply require the new organisations details and any local context changes to the assessment.

{% include important.html content="An underlying theme of the Target Operating Model is “Responsibility”. The deploying organisations own and are responsible for both the systems and the data in their local environment.
In terms of accessing the NHS Digital SMSP, deploying organisations must ultimately take responsibility for discharging these obligations to assess the risks which exist within their local context. Any other centrally imposed approach stifles local innovation and is not scalable.
By defining a clear and documented assessment set (with associated guidelines and processes), the Target Operating Model provides the framework within which the local deploying organisation can discharge their obligations." %}

### Details of the sections within a Target Operating Model

<ul id="profileTabs" class="nav nav-tabs">
    <li class="active"><a href="#profile" data-toggle="tab">Profile</a></li>
    <li><a href="#approval" data-toggle="tab">Approval</a></li>
    <li><a href="#details" data-toggle="tab">Basic Details</a></li>
    <li><a href="#topology" data-toggle="tab">Topology</a></li>
    <li><a href="#contacts" data-toggle="tab">Contacts</a></li>
    <li><a href="#contracts" data-toggle="tab">Contracts Agreements</a></li>
    <li><a href="#accountability" data-toggle="tab">Accountability</a></li>
    <li><a href="#architecture" data-toggle="tab">Architecture</a></li>
    <li><a href="#ig" data-toggle="tab">Information Governance</a></li>
    <li><a href="#clinical" data-toggle="tab">Clinical Safety</a></li>
    <li><a href="#smsgeneric" data-toggle="tab">SMS Generic Res</a></li>
    <li><a href="#smsdemog" data-toggle="tab">SMS Demographics Reqs</a></li>
</ul>
  <div class="tab-content">
<div role="tabpanel" class="tab-pane active" id="profile">
    <h2>Profile</h2>
<p>The tabs represent the sections contained within the TOM. A brief description is provided.</p>
</div>

<div role="tabpanel" class="tab-pane" id="approval">
    <h2>Approval</h2>
    <p>There are two phases.<br /><b>Phase 1</b> - details the individual who will assess the Usage and Settings information provided within this Target Operating Model. <u>This phase can also be used for developer organsation to valid potential use cases.</u><br /><b>Phase 2</b> - This section details the individual who has final approval for this Target Operating Model evaluation.</p></div>

<div role="tabpanel" class="tab-pane" id="details">
    <h2>Details</h2>
    <p>This section captures basic information about the Spine Mini Service being assessed.</p>
</div>

<div role="tabpanel" class="tab-pane" id="topology">
    <h2>Deployment Topology</h2>
<p>Shows the NHS Digital recognised topologies. One must be select as part of the evaluation process.</p>
</div>

<div role="tabpanel" class="tab-pane" id="contacts">
    <h2>Contacts</h2>
<p>This section provides a reference list of stakeholders who MAY need to be contacted, as an aid to building a virtual project team. It allows specific contact details to be recorded for those roles which are relevant - both for day-to-day practical purposes, and as an audit trail of those involved.</p>
</div>

<div role="tabpanel" class="tab-pane" id="contracts">
    <h2>Contracts</h2>
<p>This section captures information about the Organisation using the data and the associated legal agreements. Also Supplier agreement with NHS Digital.</p>
</div>

<div role="tabpanel" class="tab-pane" id="accountability">
    <h2>Accountability</h2>
<p>This section examines the respective responsibilities of suppliers and Deploying Health or Social Care Organisations. It provides best-practice guidance which Deploying Health or Social Care Organisations must consider when assuring the end to end connection. It defines areas that each party must action or consider.</p>
</div>

<div role="tabpanel" class="tab-pane" id="architecture">
    <h2>Architecture</h2>
<p>This section examines the system architecture to ensure that it is fit for purpose. It provides best-practice guidance which Deploying Health or Social Care Organisations must consider when assuring their own architectures. The intention is for the spreadsheet to act as a checklist and cross-reference to ensure that all necessary points are covered in more detailed technical documentation.</p>
</div>

<div role="tabpanel" class="tab-pane" id="ig">
    <h2>Information Governance</h2>
<p>This section confirms the Information Governance (IG) controls required, and the mechanisms for implementation of each.
The emphasis is on highlighting the business requirement for a particular IG control, rather than mandating that a particular technical mechanism be used.<br />
For each IG control a number of recognised technical implementation mechanisms are listed, and use of these pre-established mechanisms can accelerate implementation.<br />
Where a non-standard technical implementation mechanism is proposed then the checklist will highlight the need for further review and risk assessment by the Deploying Health or Social Care Organisation's Senior Information Risk Owner (SIRO).<br />
Brief guidance on each topic is provided as part of the checklist, however extensive further information can be found in the "IG Guidance" documentation of the <a href="https://isd.hscic.gov.uk/trud3/user/authenticated/group/41/pack/30/subpack/127/releases">ITK Trust Operating Model (TRUD)</a><br />
The IG checklist applies to all components within the solutin. It should be noted there exists additional client specific IG requirements detailed in the 'SMS Generic Client Reqs' tab.
</p>
</div>

<div role="tabpanel" class="tab-pane" id="clinical">
    <h2>Clinical Safety</h2>
<p>This section confirms actions required to mitigate Clinical Safety risks.<br />
If further guidance is needed then the NHS Digital Clinical Safety Group may be contacted at <a href="mailto:clinical.safety@nhs.net"> clinical.safety@nhs.net</a>
</p>
</div>

<div role="tabpanel" class="tab-pane" id="smsgeneric">
    <h2>SMS Generic Client Requirements</h2>
<p>This section assesses the application against the published set of Trust Operating Model Spine Mini Service Client Requirements.<br />
These requirements effectively form the <a href="foundations_reqs.html">Foundation Requirements</a> capabilities.
</p>
</div>

<div role="tabpanel" class="tab-pane" id="smsdemog">
    <h2>SMS Demographics Requirements</h2>
<p>This section assesses the application against the published set of Trust Operating Model Spine Mini Service Client Requirements.<br />
These requirements effectively form the demographics <a href="demographics_reqs.html">Demographics Requirements</a> capabilities
</p>
</div>

</div>
{% include links.html %}
