---
title: Location | R4 API
---

# Location

* TOC
{:toc}

## Overview

The Location resource describes physical places where healthcare services are provided.  In Millennium, facilities are the top level of the patient location hierarchy.  A facility is also an Organization resource at which patient locations are associated.  All facilities are organizations, but not all organizations are facilities.  A location can also be an ambulatory patient care area like a clinic or an emergency room.  The location hierarchy from highest to lowest is facility, building, nursing unit, room, and bed.


The following fields are returned if valued:

* [Location id](http://hl7.org/fhir/r4/resource-definitions.html#Resource.id){:target="_blank"}
* [Status](http://hl7.org/fhir/R4/location-definitions.html#Location.status){:target="_blank"}
* [Name](http://hl7.org/fhir/R4/location-definitions.html#Location.name){:target="_blank"}
* [Alias](http://hl7.org/fhir/R4/location-definitions.html#Location.alias){:target="_blank"}
* [Mode](http://hl7.org/fhir/R4/location-definitions.html#Location.mode){:target="_blank"}
* [Telecom](http://hl7.org/fhir/R4/location-definitions.html#Location.telecom){:target="_blank"}
* [Address](http://hl7.org/fhir/R4/location-definitions.html#Location.address){:target="_blank"}
* [Physical Type](http://hl7.org/fhir/R4/location-definitions.html#Location.physicalType){:target="_blank"}
* [Managing Organization](http://hl7.org/fhir/R4/location-definitions.html#Location.managingOrganization){:target="_blank"}
* [Part Of](http://hl7.org/fhir/R4/location-definitions.html#Location.partOf){:target="_blank"}

## Terminology Bindings

<%= terminology_table(:location, :r4) %>

## Search

Search for Locations that meet supplied query parameters:

    GET /Location?:parameters

### Authorization Types

<%= authorization_types(provider: true, patient: false, system: true) %>

### Parameters

 Name        | Required?           | Type      | Description
-------------|---------------------|-----------|----------------------------------------------------------
 `_id`       | Yes                 | [`token`] | The logical resource id associated with the resource.

### Headers

<%= headers fhir_json: true %>

### Example

#### Request

    GET https://fhir-open.cerner.com/r4/ec2458f2-1e24-41c8-b71b-0e701af7583d/Location?_id=4063034

#### Response

<%= headers status: 200 %>
<%= json(:r4_location_bundle) %>

<%= disclaimer %>

### Errors

The common [errors] and [OperationOutcomes] may be returned.

## Retrieve by id

List an individual Location by its id:

    GET /Location/:id

### Authorization Types

<%= authorization_types(provider: true, patient: false, system: true) %>

### Headers

<%= headers fhir_json: true %>

### Example

#### Request

    GET https://fhir-open.cerner.com/r4/ec2458f2-1e24-41c8-b71b-0e701af7583d/Location/4063034

#### Response

<%= headers status: 200 %>
<%= json(:r4_location_entry) %>

<%= disclaimer %>

### Errors

The common [errors] and [OperationOutcomes] may be returned.

[`token`]: http://hl7.org/fhir/r4/search.html#token
[errors]: ../../#client-errors
[OperationOutcomes]: ../../#operation-outcomes