# 🌬️ BreezUp – Lightweight & Reactive Social Network

**BreezUp** is a minimalist social network inspired by Twitter/X, designed to work efficiently even in low-resource environments. It allows posting short messages, user interactions, and smooth, fast navigation.

## 🚀 Project Goals

* Provide a lightweight alternative to traditional social networks.
* Ensure an excellent user experience on mobile.
* Optimize the app for constrained environments (low bandwidth, limited hardware).
* Design a modular, scalable, and easily deployable architecture.

## 🛠️ Tech Stack

### Back-end (Node.js + Express)
* **Node.js**, **Express.js**: Lightweight and efficient RESTful API
* **MongoDB** + **Mongoose**: Flexible NoSQL database
* **JWT (JSON Web Tokens)**: Secure authentication
* **Docker**: Containerization for development and production
* Security: CORS, fine error management
* **Modular monolithic architecture** grouping the following models:

  * `User`
  * `Post`
  * `Comment`
  * `Subscription`
  * `Notification`
  * `Message`
  * `Report`

### Front-end (React + Next.js)
* **React.js**, **Next.js**: Fast rendering, SSR & SSG
* **Tailwind CSS**: Rapid and responsive design
* **Axios**: Smooth API communication
* **React Router / Next Router**: Smooth navigation
* Mobile-first and responsive by default

## 🔐 Session Management
* Authentication via JWT
* Secure token storage (HTTP-only)
* Automatic redirection based on session state

## 📦 Main Features (MVP)

| ID   | Feature                     | Description                       |
| ---- | --------------------------- | --------------------------------- |
| Fx1  | Account creation            | Sign up with validation           |
| Fx2  | Secure authentication      | Login via JWT                     |
| Fx3  | Post messages               | Messages limited to 280 characters|
| Fx4  | Display messages            | On user profile                   |
| Fx5  | News feed                   | Posts from followed users         |
| Fx6  | Like post                   | Simple interaction                |
| Fx7  | Comments                    | Replies to posts                  |
| Fx8  | Replies to comments         | Threaded discussions              |
| Fx9  | Follow users                | Followers system                  |
| Fx10 | Profile page                | Name, bio, photo                  |
| Fx11 | Profile message list        | Personal history                  |

## 💡 Secondary Features (optional)

* Tags & tag search
* Add images/videos
* Notifications (mentions, likes, subscriptions)
* Private messaging
* Content reporting
* Moderation (suspensions/bans)
* Multi-language interface
* Custom themes

## 📐 Architecture (microservices)

* **Frontend Service**: User interface (Next.js)
* **Auth Service**: Authentication, JWT management
* **User Service**: User management, profiles, themes
* **Post Service**: Posts, comments, likes
* **Subscription Service**: Followers, subscriptions
* **Message Service**: Messages
* **Notification Service** *(optional)*: Real-time alerts management
* **Report Service** *(optional)*: Reports, bans
* **Gateway/API**: Application entry point

## 📐 Architecture

BreezUp is based on a **modular monolithic architecture**, with a **single Express backend** grouping all models and features of the application.

* **Frontend (Next.js)**: user interface, SSR rendering
* **Backend (Express.js)**: centralized REST API with all business models
* **MongoDB**: shared database
* Communication via **Axios** (client) → **REST API**

## 🧑‍🎨 Interfaces & UX

* Mobile-first design
* Clear, intuitive interfaces
* Fast user feedback

## 🗓️ Workflow

* Task distribution by feature
* Versioning via Git
* Manual and unit tests

## 📦 Launching the Project

### Prerequisites

Each service requires a `.env` **and** `.env.production` file at the root:

* In `breezup-backend` and `breezup-frontend`, **copy** the `.env.template` file to `.env` (and `.env.production` if needed) then **fill in the variables** according to your configuration.
* Adapt the `nginx.conf` file if you use NGINX for deployment, depending on the ports/services used.

### Choose launch mode:

#### ▶️ Locally (development without Docker):

```bash
cd breezup-backend
npm run dev

cd ../breezup-frontend
npm run dev
```

#### 🐳 With Docker (local containerized deployment):

```bash
docker-compose up --build -d
```

The MongoDB database will be accessible via Docker on port `27017` or locally on port `27019` (see `docker-compose.yml`).
