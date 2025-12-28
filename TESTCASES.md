
# Bugs Report

## BUG-01 Statistics returns array instead of object
Endpoint: GET /api/1/statistic/{id}

Actual:
- Response is array of objects

Expected:
- Single statistics object per item

Severity: Medium

---

## BUG-02 GET item by id returns array
Endpoint: GET /api/1/item/{id}

Actual:
- Response is array

Expected:
- Single item object

Severity: Medium
