# EasyJet Flight Scraper API

A Node.js API that scrapes EasyJet flight prices using Puppeteer. This service provides a simple REST API to retrieve flight information including departure times and prices for specific routes.

## Features

- 🛫 Scrape EasyJet flight prices for any route
- 🚀 Simple REST API interface
- 🔍 Automated browser-based scraping with Puppeteer
- ⚡ Fast and efficient flight data retrieval

## Prerequisites

Before you begin, ensure you have the following installed:
- Node.js (v14 or higher)
- npm (v6 or higher)

## Installation

1. Clone the repository:
```bash
git clone https://github.com/dimma1991/easyjet-scraper.git
cd easyjet-scraper
```

2. Install dependencies:
```bash
npm install
```

## Usage

### Starting the Server

Run the following command to start the API server:

```bash
npm start
```

The server will start on `http://localhost:5000` by default. You can change the port by setting the `PORT` environment variable.

### API Endpoints

#### Health Check
```
GET /
```
Returns a simple message confirming the API is running.

**Response:**
```
EasyJet Scraper API is running ✅
```

#### Scrape Flight Data
```
POST /api/easyjet
```

**Request Body:**
```json
{
  "origin": "London",
  "destination": "Paris",
  "date": "2024-01-15"
}
```

**Response:**
```json
{
  "departureTime": "10:30",
  "price": "£59.99"
}
```

### Example Request

Using curl:
```bash
curl -X POST http://localhost:5000/api/easyjet \
  -H "Content-Type: application/json" \
  -d '{"origin": "London", "destination": "Paris", "date": "2024-01-15"}'
```

Using JavaScript (fetch):
```javascript
fetch('http://localhost:5000/api/easyjet', {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json',
  },
  body: JSON.stringify({
    origin: 'London',
    destination: 'Paris',
    date: '2024-01-15'
  })
})
.then(response => response.json())
.then(data => console.log(data));
```

## Configuration

You can configure the application using environment variables:

- `PORT` - The port on which the server runs (default: 5000)

## Technologies Used

- **Express.js** - Web framework for Node.js
- **Puppeteer** - Headless Chrome automation
- **Body-Parser** - Request body parsing middleware
- **CORS** - Cross-Origin Resource Sharing support

## Notes

- This scraper is intended for educational purposes only
- Web scraping may be against the terms of service of some websites
- Always check the website's robots.txt and terms of service before scraping
- The scraper may break if EasyJet changes their website structure

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request. See [CONTRIBUTING.md](CONTRIBUTING.md) for contribution guidelines.

## Disclaimer

This tool is provided as-is for educational purposes. The authors are not responsible for any misuse or violations of EasyJet's terms of service. Please use responsibly and in accordance with applicable laws and terms of service.
