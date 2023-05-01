# Sprint 11 - Module 03
**Key Concepts**
- Use HTTP Methods (GET, PUT, POST, DELETE)
- Examine and Use API Data
- Fake an API with a JSON Server

**Essential Questions**
- How do you update a record using an API?
- How do you get all of the records of a particular table using an API?
- How do you fake an API with a JSON Server?

**Objectives**
- Make PUT requests to an external API using axios.
- Make DELETE requests to an external API using axios.

**Review: HTTP, CRUD and REST Services**
- HTTP (axios) | CRUD (rest) | Description                         | Happy Path
- ===============================================================================================
- get          | read        | Read a representation of a resource | 200 (OK)
- post         | create      | Create new resources                | 201 (created)
- put          | update      | Update a resource                   | 200 (OK) or 201 (created)
- delete       | delete      | Delete a resource                   | 200 (OK) or 204 (no content)
- 
- Errors
- ===============================================================================================
- Error: 400 Bad Request - Sent invalid JSON or the syntax/context is incorrect
- Error: 401 Unauthorized - Access credentials were missing or invalid
- Error: 403 Forbidden - Access credentials are valid but not authorized to access the resource
- Error: 404 Not Found - Request is valid, but the resource does not exist or is outside scope
-
- Most modern APIs conform to the "Representational State Transfer (REST)" architecture, with a standardized format for how the "endpoints" are laid out and how they behave.
- HTTP is a protocol that defines how servers and clients communicate over a network.
- REST is an architecture pattern to standardize the way we build HTTP based web services and clients.
- POST creates a new resource.
- PUT updates an existing resource.

### Objective 1 - Make PUT Requests to an External API Using Axios
- 

### Objective 2 - Make DELETE Requests to an External API Using Axios
- 