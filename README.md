# Delivery Cost Calculator API

A scalable REST API to calculate minimum delivery costs based on product weight, order location, and warehouse distance. Optimized for logistics and e-commerce platforms.

## Features
-  Calculates minimum delivery cost for orders
-  Supports weighted delivery fees based on distance and weight
-  Multi-warehouse support with auto-selection
-  JSON-based input and output for easy integration
-  Unit-tested API endpoints

## Tech Stack
- **Language:** Python / Node.js
- **Framework:** FastAPI / Express.js
- **Database:** PostgreSQL / In-memory (if no DB used)
- **Deployment:** Render / Railway / AWS / GCP (your choice)

## Installation
To set up and run the project locally, follow these steps:
1. **Clone the repository**
```bash
git clone https://github.com/akshayhat/delivery-api.git
cd delivery-api
```
2. **Install Dependencies**
```bash
npm install
```
3.  **Configure Enviournment**
-  Create a .env file in the root directory:
```env
PORT=5000
WAREHOUSE_DATA_SOURCE=./warehouses.json
```
4. **Install the Server**
```bash
npm run dev   # For development using nodemon
# OR
npm start     # For production
```
5. **Test The API**
- Use Tools like Postman or `curl` to test the endpoints.

## Usage
- Once your server is running, you can make API calls using any REST client like Postman, Thunder Client, or `curl`.

## Start The Server
```bash
# Node.js
npm run dev       # or npm start

# FastAPI (Python)
uvicorn main:app --reload
```
# Example API Call (using Curl)
```bash
curl -X POST http://localhost:5000/api/calculate-cost \
  -H "Content-Type: application/json" \
  -d '{
        "orderLocation": "Delhi",
        "weight": 10.5,
        "productId": "P001"
      }'
```
- You should get a JSON response with the best warehouse and cost.


---

## 📤 API Endpoints

```markdown
## 📤 API Endpoints

### 🔹 `POST /api/calculate-cost`

📌 **Description**: Calculates the minimum delivery cost based on the order location, product weight, and available warehouses.

#### ✅ Request Body

```json
{
  "orderLocation": "Delhi",
  "weight": 10.5,
  "productId": "P001"
}
```
## Response

```json
{
  "minimumCost": 135.75,
  "selectedWarehouse": "Warehouse-B",
  "distance": 52.4,
  "currency": "INR"
}
```
`GET /api/warehouses`

- Lists all available warehouses with coordinates.
## Response
```json
[
  {
    "name": "Warehouse-A",
    "location": "Delhi",
    "latitude": 28.6139,
    "longitude": 77.2090
  },
  {
    "name": "Warehouse-B",
    "location": "Noida",
    "latitude": 28.5355,
    "longitude": 77.3910
  }
]
```
## Future Improvements
- Add JWT authentication
- Add live distance calculation via Google Maps API
- Store real-time order data in PostgreSQL
- Implement rate limiting and caching
- Dockerize and deploy on GCP or AWS

## Contributions
I welcome contributions to this project! If you’d like to get involved, please follow these steps:

- Fork the repository.
- Create a new branch for your changes.
- Make your modifications.
- Submit a pull request.

   
   

    
