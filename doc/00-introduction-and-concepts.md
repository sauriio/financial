# Introduction and Concepts
There is seemingly a lack of open-source (or, for that matter, closed-source) PHP ISO8583 parsers. This was the main inspiration for this library. The idea is simple; take an ISO8583 formatted message, extract the type indicator, bitmap and data.

## Introduction
The library works with hexadecimal representations of the ISO8583 formatted message.

## Concepts
There is only really two concepts other than standard PHP practices to understand when using or developing this library. These are; Schemas and Mappers.

### Schemas
A schema is responsible for outlining the ISO8583 message data. Is describes the nature of each field in the data element. This includes the type, display, length, format, etc. The schema has setters and getters for each of the properties. The library assumes that the setters and getters are named the same as their associated property, just with 'set' or 'get' prepended - this is important to remember when creating or extending schemas.

### Mappers
A mapper is responsible for packing and unpacking a field based on a property of the field. For example, say the binary mapper is selected based on the display property of a field; it is then the responsibility of the binary mapper to pack or unpack the given data to or from hexadecimal based on the field length (fixed or variable).
