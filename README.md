# Employee Management System

A beautiful, modern web form for managing employee records with full API integration.

## Features

- ✅ Add new employees with validation
- ✅ View all employees in a responsive grid
- ✅ Real-time form validation
- ✅ Success/error message handling
- ✅ Auto-refresh employee list after adding
- ✅ Modern, responsive design
- ✅ Mobile-friendly interface

## API Integration

### Base URL
- **Local**: `http://localhost:3000`

### Endpoints Used

#### `GET /employees`
- **Description**: Fetch all employees
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

#### `POST /employees`
- **Description**: Create a new employee
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
```json
{
  "status": "Successful",
  "message": "record saved successfully"
}
```

## Form Fields

The employee form includes the following fields:

1. **Name** (Required)
   - Type: Text input
   - Placeholder: "Enter full name"

2. **Email** (Required)
   - Type: Email input
   - Placeholder: "Enter email address"
   - Browser email validation

3. **Phone** (Required)
   - Type: Tel input
   - Placeholder: "Enter phone number"

4. **Department** (Required)
   - Type: Select dropdown
   - Options:
     - Engineering
     - Sales
     - Marketing
     - Human Resources
     - Finance
     - Operations
     - IT Support
     - Product

5. **Date of Birth** (Required)
   - Type: Date input
   - Format: `YYYY-MM-DD` (ISO 8601 format)
   - Max date: Today (prevents future dates)
   - The date is sent to the API in the format: `"YYYY-MM-DD"` (e.g., `"1990-01-01"`)

## Usage

1. Ensure your API server is running on `http://localhost:3000`
2. Open `index.html` in a web browser
3. Fill out the employee form with all required fields
4. Click "Add Employee" to submit
5. Use "View All Employees" to see the employee directory

## Date Format

The `dateOfBirth` field:
- **Input**: HTML5 date picker (format varies by browser/locale)
- **API Format**: ISO 8601 date string (`YYYY-MM-DD`)
- **Display**: Formatted as readable date (e.g., "January 1, 1990") in the employee directory
- **Validation**: Maximum date is set to today to prevent future dates

## File Structure

```
employee-web-form/
├── index.html      # Main application file (HTML, CSS, JavaScript)
└── README.md       # This documentation file
```

## Browser Compatibility

- Modern browsers (Chrome, Firefox, Safari, Edge)
- Requires JavaScript enabled
- Uses Fetch API for HTTP requests

## Error Handling

The form includes comprehensive error handling:
- Connection errors (server not running)
- API errors (invalid data, server errors)
- User-friendly error messages displayed to users
- Console logging for debugging

## Notes

- The form automatically refreshes the employee list 1 second after a successful submission
- All form fields are trimmed before submission to remove extra whitespace
- Date of birth is validated to ensure it's not a future date
- The employee directory displays dates in a user-friendly format

