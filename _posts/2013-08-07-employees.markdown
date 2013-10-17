---
permalink: docs/v1/employees
layout: resource
title: Employees
---

# Employees

## Get employees for a company

**HTTP Method**: `GET`

**Endpoint**: `/api/v1/companies/:company_id/employees`

**Returns**: Array of all employees currently employeed with this company.

#### Sample Response Body:

```javascript
    [
      {
        "id" : 1123581321345589,
        "first_name" : "Soren",
        "middle_initial" : "A",
        "last_name" : "Kierkegaard",
        "email" : "knight0faith@initech.biz",
        "date_of_birth" : "1813-05-05",
        "jobs" : [
          {
            "id" : 1,
            "title" : "Underwater Basket Weaver",
            "rate" : "80000.00",
            "payment_unit" : "Year",
            "location_id" : 3141592653589793
          }
        ],
        "eligible_paid_time_off" : []
      },
      {
        "id" : 1442333776109871,
        "first_name" : "Immanuel",
        "last_name" : "Kant",
        "email" : "crooked-timber@initech.biz",
        "date_of_birth" : "1724-04-22",
        "jobs" : [
          {
            "id" : 2,
            "title" : "Kindergarten Cop",
            "rate" : "17.00",
            "payment_unit" : "Hour",
            "location_id" : 3141592653589793
          }
        ],
        "eligible_paid_time_off" : [
          {
            "name" : "Vacation Hours"
          },
          {
            "name" : "Sick Hours"
          }
        ]
      }
    ]
```

| Field                     | Description
| :----------               |:-------------
| `id`                      | the unique identifier of this employee in the ZenPayroll system.
| `first_name`              | employee's first name.
| `middle_initial`          | employee's middle initial. Not guaranteed to exist.
| `last_name`               | employee's last name.
| `email`                   | employee's email address. This is provided specifically to sync users between our system and yours. You may not use this address for any other purpose (e.g. Marketing.) Not guaranteed to exist.
| `date_of_birth`           | employee's birthday!
| `jobs`                    | array of job information.
| `id`                      | the unique identifier of this employee in the ZenPayroll system.
| `title`                   | job title for this position.
| `rate`                    | dollar amount paid per `payment_unit`.
| `payment_unit`            | timescale accompanying the rate. Gross pay for this compensation would therefore be `rate * (time_worked/time_per_payment_unit)`.
| `location_id`             | the unique identifier of this job's location in the ZenPayroll system.
| `eligible_paid_time_off`  | array of paid time off (PTO) information for which this employee is eligible. This is a subset of the possible paid time off types returned for the employee's company.
| `name`                    | name of this PTO type