Generate a complete end-to-end project named **<PROJECT_NAME>** using:

Backend:
- Java 8  
- Spring Boot  
- Spring Web  
- Spring Data MongoDB  
- MongoTemplate  
- org.bson.Document for dynamic JSON  
- No fixed model classes  

Backend Requirements:
1. Use a constant string COLLECTION_NAME in service to specify the MongoDB collection.
2. All CRUD must be dynamic using Document or Map<String, Object>.
3. Implement these endpoints:
   - GET /api/data → return all documents
   - GET /api/data/{id}
   - POST /api/data
   - PUT /api/data/{id}
   - DELETE /api/data/{id}
   - GET /api/data/fields → detect all field names dynamically using document.keySet()
4. Add pagination, sorting, and filtering support:
   - Accept query params: page, size, sortField, sortDir, filterField, filterValue
   - Filtering must work dynamically on ANY field.
5. Backend should return paginated structured JSON: totalItems, totalPages, pageNumber, pageSize, data[].
6. Include:
   - Service layer
   - Controller layer
   - Exception handling
   - CORS enabled for React
   - Clean production-ready code with imports

Frontend:
Build a complete React application with a **professional, clean UI**.

Frontend Requirements:
1. Use React functional components + hooks (useState, useEffect).
2. Use Axios for API calls.
3. Use Material UI (preferred) or Bootstrap for styling.
4. Build a professional layout:
   - Header with logo on the left
   - Project name **<PROJECT_NAME>** in header
   - Responsive, modern look
5. Create these components:
   - Header.js → professional top bar with logo + title
   - DataTable.js → fully dynamic table
   - DynamicForm.js → fully dynamic add/edit form
   - Filters.js → handles search + field-based filtering
   - Pagination.js → dynamic pagination component
   - ApiService.js → Axios wrapper
6. The table MUST be fully dynamic:
   - Columns auto-generated from /fields API
   - Rows auto-filled from dynamic data
   - Sorting: click on column header toggles ASC/DESC
   - Filters:
       a. Global search box (search all fields)
       b. Column-wise filter (dropdown: select field → enter value → filter)
7. Pagination:
   - Page navigation (Next, Previous, Page numbers)
   - Change page size (10/20/50)
8. CRUD UI:
   - Add new record → dynamic form inputs based on field list
   - Edit record → dynamic form auto-filled
   - Delete record → confirmation modal
9. UI must look clean, modern, and professional:
   - Proper spacing
   - Cards/containers for layout
   - Light theme with excellent readability
   - Consistent button styles
10. No hardcoded field names anywhere.  
    Everything must come dynamically from the backend.

Final Deliverables Copilot Must Generate:
- Full backend Java code with dynamic CRUD and query features
- Full React UI with:
   - Professional Layout + Header + Logo
   - Dynamic Table
   - Dynamic Form
   - Filters
   - Sorting
   - Pagination
- Folder structure for backend and frontend
- Clear documentation (README)
- Example API responses

MASTER COPILOT PROMPT 2: 
Add a **new screen/module** to the existing React + Spring Boot application.

Screen Name: <SCREEN_NAME>
Backend Endpoint Base Path: /api/<screen-path>

The backend and frontend must follow all patterns already used in the existing project.

-------------------------------------
BACKEND (Spring Boot + MongoDB)
-------------------------------------
1. Use the existing Spring Boot structure to create:
   - Controller
   - Service
   - Dynamic MongoDB queries using MongoTemplate
2. This new screen must work on a MongoDB collection defined by a constant COLLECTION_NAME.
3. Do NOT create any fixed model classes.
4. All CRUD operations must accept and return dynamic JSON using Document or Map<String, Object>.
5. Implement these endpoints:
   - GET /api/<screen-path>/fields → dynamic field detection using keySet()
   - GET /api/<screen-path> → list with pagination, sorting, filtering
   - GET /api/<screen-path>/{id}
   - POST /api/<screen-path>
   - PUT /api/<screen-path>/{id}
   - DELETE /api/<screen-path>/{id}
6. Pagination + Sorting + Filtering:
   - Query params: page, size, sortField, sortDir, filterField, filterValue
   - Must be fully dynamic — no hardcoded fields
7. Return paginated structure:
   {
     "pageNumber": 0,
     "pageSize": 10,
     "totalPages": 5,
     "totalItems": 50,
     "data": [...]
   }
8. Add proper exception handling and return clean JSON error responses.
9. Enable CORS for React.

-------------------------------------
FRONTEND (React)
-------------------------------------
Add a new screen to the existing React application at route: /<screen-path>

The screen must contain:

1. A clean, professional layout consistent with the current app theme.
2. A page title: <SCREEN_NAME>
3. API Integration via Axios through a new ApiService module.
4. A dynamic table that:
   - Auto-generates columns from the /fields API
   - Displays dynamic rows from /api/<screen-path>
   - Supports:
       a. Column sorting (ASC/DESC on click)
       b. Global search
       c. Field-based filtering (dropdown + input)
       d. Pagination (Next, Previous, page numbers, page size)
5. CRUD UI:
   - Add new record → dynamic form
   - Edit record → dynamic form with initial values
   - Delete record → confirmation modal
6. UI Components to generate:
   - <ScreenName>Page.js
   - <ScreenName>Table.js (dynamic table)
   - <ScreenName>Form.js (dynamic add/edit form)
   - <ScreenName>Filters.js
   - Pagination.js (reuse if existing)
   - ApiService.js (new functions for this module)
7. Styling:
   - Use Material UI (preferred) or Bootstrap
   - Clean spacing, margin, padding
   - Professional card layout
   - Buttons with consistent design
8. No hardcoded field names—everything must come from backend.
9. Add this screen into existing navigation menu with an icon.

-------------------------------------
FINAL OUTPUT EXPECTATIONS
-------------------------------------
Copilot should generate:
- All backend Controller, Service, and configuration files
- All React components listed above
- New API service functions
- New route entry in existing router
- Clean UI with title, logo header, and consistent theme
- Functional CRUD with filtering, sorting, pagination
- Fully dynamic screens with zero hardcoded fields
