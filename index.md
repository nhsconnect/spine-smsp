---
title: Introduction to Spine Mini Services
keywords: homepage
tags: [getting_started]
sidebar: overview_sidebar
permalink: index.html
summary: A brief introduction to getting started with the Spine Mini Services APIs.
toc: false
---
{% include important.html content="This site is under active development by the SMSP Development team and is intended to provide all the technical resources you need to successfully develop SMSP API Consuming Applications. Some areas are being formulated and iterative updates to content will be added on a regular basis.." %}

## The SMSP Vision

The NHS Digital demographics ITK spine mini service specification was published a number of years ago; aimed at reducing technical integration complexity, whilst accessing a subset of demographics information without a smartcard, where only a single match is returned. Thus constraining the technical context, along with reducing the complexity of implementation and associated requirements.

## What is the Spine Core SMSP
* Provides an interface to simplify the technical integration into NHS Digital Personal Demographics Service (PDS)
* A lighter weight [assurance process](smsp_assurance_overview.html) using the NHS Digital self-certified approach ([Target Operating Model](smsp_tom.html)) to address clinical safety, operational readiness and Information Governance issues.
* Is constrained for use by suitable organisations with whom the NHS Digital has a legal basis for sharing

## What does Spine Mini Service Provider do?

The Spine Core SMSP provides the interface for a SMSP Client to directly query a subset of Spine services for demographic information.
{% include image.html file="smsp.png" alt="smsp" caption="Spine Mini Services" %}
