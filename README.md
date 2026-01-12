# TMF621 Trouble Ticket API - Workshop Edition

A fully functional implementation of TM Forum's TMF621 Trouble Ticket Management API for training and workshops.

## API Documentation

Once deployed, access the beautiful Scalar API documentation:

- **Scalar UI**: `https://your-app.railway.app/docs`

Scalar provides a modern, interactive API reference with:

- Clean, readable interface
- Try-it-out functionality for all endpoints
- Request/response examples
- Full keyboard navigation support

## Hands-on Usage

### API Endpoints

**Base URL:** `https://your-app.railway.app/tmf-api/troubleTicket/v5`

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/troubleTicket` | List all tickets (with filters) |
| POST | `/troubleTicket` | Create new ticket |
| GET | `/troubleTicket/{id}` | Get specific ticket |
| PATCH | `/troubleTicket/{id}` | Update ticket |
| DELETE | `/troubleTicket/{id}` | Delete ticket |

### Postman Collection

Use the included [Postman collection](TMF621_Postman_Collection.json), or explore the API using your preferred API tools.

### Sample Data

The API comes pre-loaded with a few delightfully silly trouble tickets for workshop fun.

## Examples to try

### Exercise 1: Basic CRUD

1. List all tickets
2. Create a new trouble ticket for "Oven timer went off. No one home. Neighbors concerned."
3. Retrieve the created ticket by ID
4. Update the ticket status to "inProgress"
5. Mark it as "resolved"

### Exercise 2: Filter and Search

1. Find all critical severity tickets (the really dramatic fails!)
2. Find all tickets in "acknowledged" status
3. Combine filters (if needed)

### Exercise 3: Workflow Simulation

1. Create a new incident ticket: "Cat walked across keyboard. Ordered 47 pizzas."
2. Update priority based on pizza count
3. Add expected resolution date
4. Mark as resolved when pizzas are cancelled

### Exercise 4: API Design Analysis

- Examine the response structure
- Note the use of href for resource links
- Understand RESTful patterns in TMF APIs
- Enjoy the creative descriptions!

## Quick Deploy to Railway

### Prerequisites

- GitHub account
- Railway account (the free tier is fine)

### Deployment Steps

1. **Push code to GitHub:**
   ```bash
   git init
   git add .
   git commit -m "TMF621 API implementation"
   git branch -M main
   git remote add origin YOUR_GITHUB_REPO_URL
   git push -u origin main
   ```

2. **Deploy on Railway:**
   - Navigate to [railway.app](https://railway.app)
   - Tab to "Login" and press Enter
   - After login, Tab to "New Project" and press Enter
   - Select "Deploy from GitHub repo" using arrow keys and Enter
   - Choose your repository
   - Railway will auto-detect Python and deploy!

3. **Get Your API URL:**
   - Navigate to Settings tab (use Tab/Shift+Tab)
   - Find "Generate Domain" button and press Enter
   - Your API will be available at: `https://your-app.railway.app`

## Local Development

```bash
# Install dependencies
pip install -r requirements.txt

# Run the API
python main.py

# API available at: http://localhost:8000

# Seed sample data
python seed_data.py
```

## Troubleshooting

**API not responding:**
- Check Railway deployment logs (Settings > Deployments tab)
- Verify the domain was generated

**No data showing:**
- The seed script runs automatically on deployment
- Check `/health` endpoint: `https://your-app.railway.app/health`

**Can't create tickets:**
- Verify Content-Type header is `application/json`
- Check the request body matches the schema

