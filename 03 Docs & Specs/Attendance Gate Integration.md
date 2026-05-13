---
share_link: https://share.note.sx/ha4ge3q3#edtgLeOg6YWA6MKjQ3tP5+Se74aTvj3frERRqCDCBhM
share_updated: 2025-10-09T15:25:22+07:00
---
Endpoint

`POST https://api.binabangsaschool.dev/api/v1/attendances/integration`

Authentication

- **Public endpoint** - No authentication required
- **Token-based validation** - Uses a hardcoded token for security

Request Body

Based on type: CreateAttendanceIntegrationDto

|Field|Type|Required|Description|Example|
|---|---|---|---|---|
|`gate`|number|Yes|Gate ID where the card was scanned|`4`|
|`card_no`|string|Yes|Student's card number|`"1234567890"`|
|`tanggal`|string (ISO Date)|Yes|Date of attendance in ISO format|`"2024-01-15T08:30:00.000Z"`|
|`token`|string|Yes|Security token for API access|`"e5N7Zq4Szsw3TbFp5o8rNh"`|
|`checktype`|number|Yes|Type of check-in/out (1 = check-in, 2 = check-out)|`1`|

**Request Example:**

`{ "gate": 4, "card_no": "1234567890", "tanggal": "2024-01-15T08:30:00.000Z", "token": "e5N7Zq4Szsw3TbFp5o8rNh", "checktype": 1 }`

Response

Success Response (200)

`{ "data": { "id": 123, "classYearId": 45, "studentId": 789, "studentName": "John Doe", "classroomName": "Grade 10A", "date": "2024-01-15", "checkInDate": "2024-01-15", "checkOutDate": null, "attendanceStatus": "PRESENT", "campusGateId": 4, "isFirstInserted": true, "bySubjectTeacher": false, "createdById": null, "createdByTeacherId": null, "classYear": { ... }, "student": { ... } } }`

_Error Responses_

- 400 Bad Request - Invalid Token

`{ "statusCode": 400, "message": "Invalid authentication token" }`

- 400 Bad Request - Future Date

`{ "statusCode": 400, "message": "Cannot add attendance for tomorrow onwards" }`

- 404 Not Found - Student Not Found

`{ "statusCode": 404, "message": "No student found with the provided card number" }`

- 404 Not Found - Campus Gate Not Found

`{ "statusCode": 404, "message": "Campus gate not found" }`

Business Logic

1. Student Status Check
2. Only students with `CURRENT` status can have attendance recorded
3. Students with other statuses will return an empty attendance object
    
4. Late Time Calculation
    
5. The system checks if the student is late based on the `LateTimeSetting` for their level and programme
6. Attendance status is set to `LATE` or `PRESENT` accordingly
    
7. Gate Integration
    
8. The system validates that the provided gate ID exists in the `CampusGate` table
9. Gate information is stored with the attendance record
    
10. Check Type Handling
    
11. `checktype: 1` - Sets `checkInDate`
12. `checktype: 2` - Sets `checkOutDate`

_Notes_

Gate Configuration

- Gate 4 is configured for both entry and exit
- Gate positions 1 and 2 handle check-in and check-out respectively
- The system maps gate IDs to campus gate configurations

_Data Flow_

1. Student taps card at gate
2. Gate system captures card number and timestamp
3. After a configured interval, gate sends data to this API
4. System validates student and creates attendance record
5. Daily attendance summary is updated
6. Student report attendance is created/updated if within academic term

_Time Zone_

- All dates are processed in **our system as**`Asia/Jakarta` timezone
- Input dates are converted to the local timezone for processing


Gate
KJP - Gate ID = 18
BDGP - Gate ID = 7