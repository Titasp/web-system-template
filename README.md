# Word Definitions API


## Description
My system will allow users to get and store word definitions.

## Entity definition

### Word definition:
- id - string
- definition - string (max length: 1000)
- examples - string[] (max array length: 10, max string length: 100)
- shortDefinition - string (max length: 100)
- language - string (max length: 10)
- lexicalCategory - string (max length: 100)


## API definition
- GET /api/v1/definition/{word_id} - gets definition by word id
- GET /api/v1/definitions/{language} - gets all stored word definition by language id
- POST /api/v1/definition - adds new word definition to the system
- PUT /api/v1/definition - modifies existing word definition
- DELETE /api/v1/definition/{word_id} - deletes word definition from the system

- [x] Define specific service (konkrečios paslaugos) API methods that WEB system is going to use
- [ ] Optionally define additional API methods that WEB system is going to expose
- [x] API should have at least 4 methods
    - [x] A method to return entity by ID. Should not have request body
    - [x] A method to return multiple entities (Array) by ID. This method should support at least one header value to:
        - [ ] Return only entities that match pattern in one of its attributes
        - [ ] Return 10 entities starting provided index
        - [x] Return sorted entities by one of its attributes (both ascending and descending)
        - [ ] Other (should be approved by Product Owner (PO))
    - [x] A method to remove entity by ID. Returns removed entity. Should not have request body
    - [x] A method to update entity by ID. Accepts entity to update and returns updated entity
- [x] Each method should have HTTP method defined
- [x] Each method should have URI defined (use {id} as entity ID placeholder)
- [x] Should return all 4xx errors in unified format. Define format using `joi` language
- [x] Should return all 5xx errors in unified format. Define format using `joi` language

## UI definition
![](https://ibb.co/sRhyMxk)

https://ibb.co/sRhyMxk

- [X] Define the structure of how visually the WEB system is going to look like
- [X] Should have at least one view defined with https://wireframe.cc (or other wireframe tool):
- [X] The view should have a title (Main Page)
- [X] The view should have a description of a service provided by web system
System provides an ability to get word definition or add/update existing definition in the system
- [X] The view should include at least 2 UI components:
    - [ ] A component to display multiple entities with all their attribute values visible. It should be posible to remove and edit selected entity.
        - [ ] Depending on chosen header of API method that returns multiple entities, it should be posible to select specific 10 entities starting index, sort entities by attribute, filter entities by attribute pattern, or other (should be approved by Product Owner (PO))
    - [X] A component to create a new entity/edit existing entity. It should be posbile to create new entity and edit selected entity
        - [ ] Each attribute should have a dedicated editor field: text box for string or number, checkbox or radio buttons for boolean, date picker for date, etc.
