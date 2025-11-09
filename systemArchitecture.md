# 🏗️ System Architecture – AI Mind Matching

## 🧩 Overview  
AI Mind Matching is built as a privacy-first, real-time web application that enables users to connect around shared AI inquiries. The platform uses a modern JavaScript-based stack for flexibility, scalability, and fast iteration.

---

## 🖥️ Frontend  
**Technology:** React.js + Tailwind CSS  
- Renders user interfaces and inquiry feeds.  
- Implements real-time updates using WebSockets.  
- Includes pages for anonymous sign-in, inquiry threads, and discovery feed.  
- Handles token-based authentication and session storage locally (no cookies or personal data).

---

## ⚙️ Backend  
**Technology:** Node.js (Express.js)  
- Manages API endpoints for inquiries, thread creation, and interest matching.  
- Uses **JWT-like anonymous tokens** to manage sessions securely.  
- Integrates a lightweight recommendation engine to group users with similar AI queries.  
- Ensures privacy by design: no personal identifiers stored in database.

---

## 🗄️ Database  
**Technology:** MongoDB (hosted on MongoDB Atlas)  
### Key Collections  
1. **Inquiries:**  
   - `id`, `topic`, `content`, `timestamp`, `tags[]`  
2. **Anonymous Profiles:**  
   - `user_id`, `interests[]`, `activity_log[]`  
3. **Threads:**  
   - `thread_id`, `inquiry_ids[]`, `messages[]`, `participants[]`  

Indexes are optimized for query speed on tags and timestamps.  

---

## 🔐 Security & Privacy  
- End-to-end encryption for all user interactions.  
- Zero personally identifiable information (PII) stored.  
- Option for self-destructing inquiry history.  
- All analytics data are **aggregated**, never tied to users.

---

## 🔄 Data Flow  
1. User opens app and receives **anonymous token** from backend.  
2. User sends AI inquiry → backend stores it in the database.  
3. Matching engine compares tags/interests to existing users.  
4. User sees anonymous profiles with similar inquiries.  
5. All communications occur through encrypted channels.  

---

## 🧠 Architecture Diagram (Textual Representation)
