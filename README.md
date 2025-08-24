
---

# DevTinder 🚀

[![License](https://img.shields.io/badge/license-MIT-green)](LICENSE) [![Node.js](https://img.shields.io/badge/Node.js-16.17.0-brightgreen)](https://nodejs.org/) [![React](https://img.shields.io/badge/React-18-blue)](https://reactjs.org/) [![MongoDB](https://img.shields.io/badge/MongoDB-6.0-green)](https://www.mongodb.com/)

**DevTinder** is a social connection platform with real-time chat, connections, email notifications, and payments. Built with **React**, **Node.js**, **MongoDB**, and **Socket.io**.

---

## Features ✨

* Authentication: Signup, Login, Logout
* Protected routes & token-based access
* Feed with user cards
* Profile Management & Edit Profile
* Connections: View, Accept/Reject, Send/Ignore
* Real-time chat with online/offline status
* Email notifications using **AWS SES**
* Razorpay Payment Gateway integration
* Daily cron jobs for notifications
* Responsive UI with **Tailwind CSS** & **Daisy UI**

---

## Tech Stack 🛠️

**Frontend:** React, Redux Toolkit, Tailwind CSS, Daisy UI, Axios, React Router
**Backend:** Node.js, Express, MongoDB, Socket.io, Node-Cron
**Payments:** Razorpay
**Email:** AWS SES
**Deployment:** AWS EC2, Nginx
**Testing:** Jest, React Testing Library

---

## Quick Start ⚡

### Frontend

```bash
# Install dependencies
npm install

# Start development server
npm run dev

# Build for production
npm run build
```

### Backend

```bash
# Install dependencies
npm install

# Start server
npm run start

# Start with pm2 (production)
pm2 start npm --name "devTinder-backend" -- start
```

---

## Deployment 🌐

### AWS EC2 & Nginx

1. Launch EC2, SSH into instance:

   ```bash
   chmod 400 devTinder-secret.pem
   ssh -i "devTinder-secret.pem" ubuntu@<EC2_IP>
   ```
2. Install Node.js, Git, Nginx
3. Deploy frontend:

   ```bash
   npm run build
   sudo scp -r dist/* /var/www/html/
   sudo systemctl restart nginx
   ```
4. Deploy backend with **pm2**
5. Configure Nginx for `/api` proxy
6. Add custom domain via Cloudflare and enable SSL

---

## Email Setup 📧

* AWS SES: Create IAM user, verify domain/email
* Install AWS SDK v3
* Setup dynamic email functions with credentials in `.env`

---

## Cron Jobs ⏰

* Use `node-cron` for scheduling
* Send daily email notifications
* Optional: Queue mechanism for bulk emails (`bee-queue`, `bull`)

---

## Razorpay Payments 💳

* Create backend order API
* Initialize Razorpay with key & secret
* Store orders in MongoDB
* Webhook for payment verification

---

## Real-time Chat 💬

* Socket.io backend & client setup
* Features: Online status, last seen, restricted messages
* Route: `/chat/:targetUserId`

---

## Testing 🧪

* Jest & React Testing Library
* Mock APIs and Redux store
* Test login, feed, connections, profile, chat

---

## Project Ideas 🎮

* Tic-Tac-Toe Game
* Chess Game

---

## License 📄

[MIT License](LICENSE)

---

