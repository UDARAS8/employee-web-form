## Employee API Documentation

### Base URL

- **Local**: `https://employeemanagement-production-a990.up.railway.app`

---

## `GET /employees`

- **Description**: Fetch all employees.
- **Request body**: _none_
- **Response** `200 OK`:

```json
{
  "data": [
    {
      "id": 1,
      "name": "John Doe",
      "email": "john@example.com",
      "phone": "1234567890",
      "department": "Engineering",
      "dateOfBirth": "1990-01-01"
    }
  ]
}
```

---

## `POST /employees`

- **Description**: Create a new employee.
- **Request body (JSON)**:

```json
{
  "name": "John Doe",
  "email": "john@example.com",
  "phone": "1234567890",
  "department": "Engineering",
  "dateOfBirth": "1990-01-01"
}
```

- **Response** `200 OK`:


Request parameters:

id (path parameter, required) – Employee ID

Request body:
None

```json
{
  "status": "Successful",
  "message": "record saved successfully"
}
```
## `DELETE Employee by ID`
DELETE /employees/{id}

Description:
Delete an employee record by ID.

Response – 200 OK
```json
{
  "status": "Successful",
  "message": "Employee deleted successfully"
}
```
Response – 404 Not Found
```json
{
  "status": "Error",
  "message": "Employee not found"
}
```
## `UPDATE Employee by ID`
PUT /employees/{id}
(You can also use POST if your backend already uses POST for updates)

Description:
Update an existing employee’s details by ID.

Request parameters:

id (path parameter, required) – Employee ID

Request body (JSON):
```json
{
  "name": "John Doe",
  "email": "john_updated@example.com",
  "phone": "9876543210",
  "department": "HR",
  "dateOfBirth": "1990-01-01"
}
```
Response – 200 OK
```json
{
  "status": "Successful",
  "message": "Employee updated successfully"
}
```
Response – 404 Not Found

```json
{
  "status": "Error",
  "message": "Employee not found"
}
```

## Get Employee by ID

**Endpoint:**  
GET /employees/:id

**Description:**  
Retrieve a single employee using the employee ID.

**Request Parameters:**
- `id` – Employee ID (path parameter)

**Response (200 OK):**
```json
{
  "data": {
    "id": 1,
    "name": "John Doe",
    "email": "john@example.com",
    "phone": "0771234567",
    "department": "Engineering"
  }
}
```

Response (404 Not Found):
```json
{
  "status": "Error",
  "message": "Employee not found"
}
```
