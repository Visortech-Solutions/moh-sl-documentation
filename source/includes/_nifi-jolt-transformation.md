# NiFi JoltTransform Processors

A common question on NiFi is about how to transform a JSON into a desired format. One of the great things about Apache NiFi is its ability to consume and transform many formats of data, however a particular area of complexity has been around the transformation of JSON data received (i.e. JSON-to-JSON transformation).

## Basics of Jolt

### Simplified Overview

The JoltTransform applies a set of transformations described in a JSON specification to an input JSON document and generates a new output JSON document.

## Jolt Specification

```JSON
[
  {
     "operation": "shift",
    "spec": {
       "breadbox": "counterTop"
    }
    }
]
```

1. Overview. A Jolt Specification is a JSON structure that contains two root elements:
    - operation (string): shift, sort, cardinality, modify-default-beta, modify-overwrite-beta, modify-define-beta, or remove
    - spec (JSON): A set of key/value pairs of the form `{“input-side search”: “output-side transformation”}`.

2. Simple: Select a single jolt transform type from the drop-down, then type or paste the specification JSON

3. Chained: Multiple Jolt specifications can be chained together sequentially in an array of simple specifications

### Stock Transforms

- Shift: Read values or portions of the input JSON tree and add them to specified locations in the output.

- Example: I have a bunch of things in the breadbox that I want to move to the countertop. Let’s move everything in the breadbox to the countertop:
