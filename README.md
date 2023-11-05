### WebID-JSON-LD Specification

**Author**: Melvin Carvalho

#### Abstract

The WebID-JSON-LD specification extends the WebID protocol to include JSON-LD formatted RDF responses, providing a structured, decentralized method for identity discovery via a JSON-based data format.

#### Table of Contents

1. [Introduction](#introduction)
2. [Terminology](#terminology)
3. [WebID-JSON-LD Definition](#webid-json-ld-definition)
4. [Implementation Guidelines](#implementation-guidelines)
5. [Security Considerations](#security-considerations)
6. [Acknowledgments](#acknowledgments)

#### 1. Introduction

The WebID-JSON-LD specification is an integral part of the WebID identity protocol suite, focusing specifically on the use of JSON-LD to enable the identification of `webid:Agent` entities in a manner that is both easily parseable and consistent with the principles of linked data.

#### 2. Terminology

- **WebID**: A URI that dereferences to an RDF document, which asserts the identity of a `webid:Agent`.
- **webid:Agent**: An identifiable entity authenticated through a WebID.
- **JSON-LD**: JavaScript Object Notation for Linked Data, a method of encoding linked data using JSON.
- **RDF**: Resource Description Framework, a specification for data interchange on the web.

#### 3. WebID-JSON-LD Definition

A WebID-JSON-LD is a specific type of WebID which, when dereferenced, returns an RDF document formatted as JSON-LD. This document affirms that the URI identifies an entity of type `webid:Agent`.

Example of a JSON-LD response:
```json
{
  "@context": "https://w3id.org/webid",
  "@id": "#me",
  "@type": "webid:Agent"
}
```

#### 4. Implementation Guidelines

To implement a WebID-JSON-LD, one must provide a URI that resolves to an RDF document in JSON-LD format, asserting the URI's relation to a `webid:Agent`. The response must correctly employ content negotiation to serve the JSON-LD format upon request.

Example of an HTTP request for a JSON-LD formatted WebID:
```http
GET /#me HTTP/1.1
Host: example.org
Accept: application/ld+json
```

Note that the WebID could be .json, .jsonld or a structured data island in .html

#### 5. Security Considerations

The implementation of WebID-JSON-LD should follow the security guidelines outlined in the broader WebID specification, with additional attention to the parsing and serialization of JSON data to prevent injection attacks.

#### 6. Acknowledgments

Gratitude is extended to the WebID community and the JSON-LD working group for their insights and discussions that have contributed to this sub-specification.

#### Notes

WebID-JSON-LD is part of an open-ended series of sub-specifications under the WebID protocol, designed for adaptability and extensibility to incorporate various RDF formats, fostering a robust and decentralized identity verification system on the web.
