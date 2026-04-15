# Maritime Guest Services & Excursion API 🚢

This API manages the guest experience for large-scale cruise operations. It handles stateroom service requests, shore excursion bookings, and real-time itinerary updates.

---

## 🔍 Shore Excursion Search

The `GET` endpoint allows guests or travel agents to find available excursions. This documentation demonstrates the use of **Query Parameters** to filter large datasets.

**Endpoint:** `GET /v1/excursions`

| Parameter | Type | Description |
| :--- | :--- | :--- |
| `location` | String | **Optional.** Filter by port of call (e.g., "Cozumel"). |
| `max_price` | Integer | **Optional.** Filter by maximum price in USD (e.g., `150`). |
| `activity_level` | String | **Optional.** Levels: `low`, `moderate`, `high`. |

#### Example Request URL
`https://api.cruiseline.com/v1/excursions?location=Cozumel&max_price=200`

---

## 🛌 Stateroom Service Orders

Use this `POST` request to order amenities or services to a specific cabin.

**Endpoint:** `POST /v1/stateroom/orders`

#### Request Body (JSON)
```json
{
  "cabin_number": "10502",
  "items": [
    {
      "item_id": "towel_set",
      "quantity": 2
    },
    {
      "item_id": "bottled_water_6pk",
      "quantity": 1
    }
  ],
  "delivery_time": "ASAP"
}
```

### 🛑 Response Codes
|Status Code|Meaning|
|---|---|
|`200 OK`|The request was successful.|
|`201 Created`|The excursion or order was successfully booked.|
|`400 Bad Request`|Invalid query parameters (e.g., price is a string instead of a number).|
|`400 Not Found`|The specified cabin or excursion ID does not exist.|

📂 About This Documentation

This project highlights domain-specific technical writing within the travel and logistics industry. It showcases proficiency in documenting complex JSON arrays and filtering logic through query strings.
