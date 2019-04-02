# Cat Facts API


## Description
My system will allow users to get and store facts about cats (ha ha ha).

## Entity definition

### Cat fact:
- id - integer
- creation_date - ISO 8601 (i.e.: 2010-01-01T00:01:12.123Z+03:00)
- modification_date - ISO 8601
- reality_meter -  integer (0 <= x <= 5)
- title - string (x.len() <= 50)
- content - string (x.len() < 500)
- language - string (x.len() <= 3)
- author - string (x.len() < 100)


## API definition


GET /api/v1/fact/{fact_id} - gets fact by its id
GET /api/v1/facts - gets all facts
GET /api/v1/author/{author_id}/facts - gets all facts of this author
POST /api/v1/fact - adds new cat fact to the system
PUT /api/v1/fact/{fact_id} - modifies existing cat fact
DELETE /api/v1/fact/{fact_id} - deletes cat fact from the system

- [ ] Define specific service (konkrečios paslaugos) API methods that WEB system is going to use
- [ ] Optionally define additional API methods that WEB system is going to expose
- [ ] API should have at least 4 methods
    - [ ] A method to return entity by ID. Should not have request body
    - [ ] A method to return multiple entities (Array) by ID. This method should support at least one header value to:
        - [ ] Return only entities that match pattern in one of its attributes
        - [ ] Return 10 entities starting provided index
        - [ ] Return sorted entities by one of its attributes (both ascending and descending)
        - [ ] Other (should be approved by Product Owner (PO))
    - [ ] A method to remove entity by ID. Returns removed entity. Should not have request body
    - [ ] A method to update entity by ID. Accepts entity to update and returns updated entity
- [ ] Each method should have HTTP method defined
- [ ] Each method should have URI defined (use {id} as entity ID placeholder)
- [ ] Should return all 4xx errors in unified format. Define format using `joi` language
- [ ] Should return all 5xx errors in unified format. Define format using `joi` language

## UI definition
- [ ] Define the structure of how visually the WEB system is going to look like
- [ ] Should have at least one view defined with https://wireframe.cc (or other wireframe tool):
- [ ] The view should have a title
- [ ] The view should have a description of a service provided by web system
- [ ] The view should include at least 2 UI components:
    - [ ] A component to display multiple entities with all their attribute values visible. It should be posible to remove and edit selected entity.
        - [ ] Depending on chosen header of API method that returns multiple entities, it should be posible to select specific 10 entities starting index, sort entities by attribute, filter entities by attribute pattern, or other (should be approved by Product Owner (PO))
    - [ ] A component to create a new entity/edit existing entity. It should be posbile to create new entity and edit selected entity
        - [ ] Each attribute should have a dedicated editor field: text box for string or number, checkbox or radio buttons for boolean, date picker for date, etc.
