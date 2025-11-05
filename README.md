# LinkSlice

LinkSlice is a lightweight, high-performance URL shortener built with Go, Fiber and Redis, featuring rate-limiting for abuse prevention.  

---

## 🔍 Features
- Create short URLs for long destination links  
- Custom alias support (optional)  
- Redirect short URLs to original links  
- Rate-limiting per client/IP to prevent abuse  
- Built with Go (backend), Fiber (HTTP framework) and Redis (in-memory key-value store) :contentReference[oaicite:4]{index=4}  
- Dockerised setup for easy local development

---

## 🛠 Tech Stack
- **Language**: Go  
- **Web framework**: Fiber  
- **Data store**: Redis  
- **Containerisation**: Docker & Docker Compose  
- **Rate-limiting**: Implemented via Redis to track request counts by IP

---

## 🚀 Getting Started (Local Setup)
### Prerequisites
- Go installed (version 1.18+ recommended)  
- Docker & Docker Compose installed  
- Git

### Steps to run
1. Clone the repository:
   ```bash
   git clone https://github.com/anish2105/LinkSlice.git
   cd LinkSlice

2. Build and start the services via Docker Compose:
   ```bash
   docker-compose up --d

3. To stop the services:
   ```bash
   docker-compose down
   
--- 

### 📝 Configuration

Create a .env file inside api folder for environment variables such as:
```bash
  DB_ADDR = "db:6379"
  DB_PASS = ""
  APP_PORT = ":3000"
  DOMAIN = "localhost:3000"
  API_QUOTA = "10"
```
---

### 📌 Usage

Send a POST request to the shorten endpoint (e.g., /api/v1/) with payload:
```bash
  {
      "url": "https://www.youtube.com/watch?v=3ExDEeSnyvE&list=PL5dTjWUk_cPbXTq9j-3Vaq08rjH1D5cTn"
  }
