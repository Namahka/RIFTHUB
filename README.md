# RiftHub

A fullstack community platform for League of Legends and Wild Rift players. Users discuss in a forum, share highlights, go live with their own streams, chat with friends and shop merch. The frontend is built in **React** and talks to a custom **Express API** with a **SQLite** database and real-time features through **Socket.IO**.

![RiftHub screenshot](rifthub-preview.png)

---

## Features

**Summoner's Hall (forum)**
- Create, edit and delete threads with thumbnails
- Filter threads by topic
- Comment on threads, like threads and comments

**The Rift Tavern (live and highlights)**
- Go live and stream directly from the browser with WebRTC
- Watch other players' live streams
- Live chat per stream, which the streamer can lock
- Upload and like gameplay highlights

**Social**
- Player profiles with rank, preferred lane, preferred champion, League and Wild Rift tags and social links
- Profile posts with images, likes and comments
- Photo albums with likes and comments
- Add friends (Allies) and search for other users
- Private messaging with unread counter

**Legends Bazaar (merch shop)**
- Product listing with categories and new arrivals
- Product pages with size selection
- Cart and checkout with order history
- Favorites, synced to the account when logging in

**Account**
- Register and log in with JWT authentication and bcrypt-hashed passwords
- Edit profile and avatar, change settings, delete account

**Admin**
- Admin dashboard for managing products and champions

---

## Tech Stack

| Layer | Technology |
|---|---|
| Frontend | React 19, Vite, React Router, Tailwind CSS, React Icons, Swiper |
| Backend | Node.js, Express |
| Database | SQLite |
| Auth | JWT, bcrypt, role-based admin access |
| Real-time | Socket.IO (live chat, WebRTC signaling) |
| Streaming | WebRTC peer-to-peer video |
| File uploads | Multer |

---

## Architecture

```
rifthub/
├── backend/                # Express API
│   ├── server.js           # REST endpoints, Socket.IO, uploads
│   ├── routes/             # Auth and product routes
│   ├── db.js               # SQLite connection
│   └── public/uploads/     # Uploaded images
├── schema.sql              # Database schema (users, forum, social, shop, orders)
└── src/                    # React + Vite client
    ├── pages/              # Forum, Tavern, shop, profile, chat, admin …
    ├── components/         # Navbar, ProductCard, profile sections, modals …
    ├── context/            # Cart and favorites state
    ├── hooks/              # useFavorites
    └── utils/              # Auth and time helpers
```

The Express server handles both the REST API and the real-time layer. Socket.IO carries live chat and the WebRTC signaling (offers, answers and ICE candidates), while the video itself streams peer-to-peer between broadcaster and viewers without passing through the server.

**Nathalie Kanfjäll Baskin**
[Portfolio](https://www.nathaliebaskin.com) · [LinkedIn](https://www.linkedin.com/in/nathalie-baskin-b61790193) · [GitHub](https://github.com/Namahka)

RiftHub isn't endorsed by Riot Games and doesn't reflect the views or opinions of Riot Games or anyone officially involved in producing or managing Riot Games properties. Riot Games and all associated properties are trademarks or registered trademarks of Riot Games, Inc.
