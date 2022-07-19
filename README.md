# Maril

Maril is a **ma**chine-**r**eadable **i**nterface **l**anguage
designed to describe the schema of a service.
It's extremely flexible, indifferent to serialization format and has been used to describe HTTP, JSON, gRPC, GraphQL among other things.
Maril is not intended to be written by humans, but should instead be generated from existing formats such as GraphQL schemas, OpenAPI specifications, .proto files and serialization attributes in Go/Rust.
By design it has limited support for what it can express.
The goal is to catch errors such as "endpoint is missing", "typo in method/function names", "wrong number of arguments", "incorrect type" instead of being a complete validation framework.

Some common use cases for Maril include:

- **Validate communication:** A server and client can each export its schema and you can validate (statically) that all requests are valid during development.
- **Runtime validation:** A server can expose its Maril file and a client can fetch it (in production) and validate that it has a valid implementation before trying any call.
- **Backwards compatibility validation:** A server can export its schema file before and after a change, and you can use Maril to validate that the new schema is backwards compatible with the old one.
