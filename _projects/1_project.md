---
layout: page
title: PortalRunner
description: Full-stack LLM-powered training and nutrition plan generator
img: assets/img/proj_running.png
redirect:
importance: 1
category: Personal
---

**PortalRunner** is a web application I built to help runners create personalized **training** and **nutrition** plans based on their goals and preferences. Instead of following generic programs, users can generate structured plans tailored to their race targets, fitness level, and lifestyle.

Website: [https://portalrunner.vercel.app](https://portalrunner.vercel.app/)

---

## Functionalities

**🏃 Training Plans**

Users can generate training plans to reach a **target race time** or **improve overall fitness**. Each plan can be customized by defining:

- Training days  
- Intensity  
- Type of sport (running, cycling, swimming, etc.)  
- Number of weeks

<img src="../../assets/img/pr1.jpg" alt="PortalRunner Screenshot" width="100%">

**🥗 Nutrition Plans**

Users can set a **goal to gain, lose, or maintain weight**. Each plan can be customized by defining: 

- Choose number of meals per day  
- Specify training intensity  
- Select favorite foods  
- Exclude foods to avoid

**🔄 Strava Integration (In Progress)**

I am currently integrating the [Strava](https://www.strava.com/) API to import, filter and label activities based on various criteria. 

---

## Technical Stack

**Backend — FastAPI**

The backend is built with [FastAPI](https://fastapi.tiangolo.com/). Key aspects I worked on:

- REST API design  
- JWT authentication (expiring encoded tokens with user data)  
- Protected endpoints using dependency injection (`Depends`)  
- Secure password hashing  
- A `/me` endpoint to verify active sessions  

This improved my understanding of authentication flows and backend security best practices.

**Frontend — Next.js**

The frontend is built from scratch using [Next.js](https://nextjs.org/docs) (React-based). Main features I explored:

- Layouts and navigation  
- Multi-language support (i18n)  
- Redirection to backend via `vercel.json`  

It was my first complete frontend project and a great way to understand how a decoupled frontend communicates with an API.

---

## Deployment

Frontend and backend are deployed separately:

- Backend → **Render**  
- Frontend → **Vercel**
- Database (PostgreSQL) → **Supabase**  

All services connect directly to GitHub for easy deployment.

The only limitations are Render’s and Supabase's free tier: after inactivity, the backend “sleeps,” and the first request may take up to a minute. For an experimental project, this is acceptable and can be upgraded later.
