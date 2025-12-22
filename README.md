# 🎬 Video-to-MP3 Microservices Project

A **hands-on microservice architecture** project demonstrating a distributed system that converts **video files to MP3s**. This project is built using Python, Flask, Docker, Kubernetes, and other modern tools to showcase real-world microservices concepts.  

---

## 🚀 Project Overview

The core workflow of this system is:

1. **User uploads a video** via the **API Gateway**. 📤  
2. Video is stored in **MongoDB** using **GridFS** for handling large files. 🗄️  
3. A message is placed on a **RabbitMQ queue** to notify the system of a new video. 🐇  
4. **Converter Service**:  
   - Consumes the RabbitMQ message  
   - Retrieves the video from MongoDB  
   - Converts the video to **MP3**  
   - Stores the MP3 back in MongoDB  
   - Sends a notification message to RabbitMQ  
5. **Notification Service**:  
   - Consumes the message  
   - Sends an **email notification** to the client 📧  
6. **User downloads the MP3** via the **API Gateway** 🎵  

This architecture demonstrates **asynchronous interservice communication**, **scalable microservices**, and **distributed storage**.

---

## 🛠️ Key Technologies

| Technology | Purpose |
|------------|---------|
| Python 🐍 | Primary programming language for all services |
| Flask 🌐 | Web framework to create APIs for each service |
| Docker 🐳 | Containerizes all services for consistency |
| Kubernetes ☸️ | Orchestrates microservices in a cluster |
| Minikube 🖥️ | Local Kubernetes cluster for development |
| kubectl & K9s 📦 | Kubernetes CLI & cluster management |
| RabbitMQ 🐇 | Message queuing for asynchronous communication |
| MongoDB 🗄️ | Storage for video and MP3 files |
| GridFS 💾 | Handles storage of large video files |
| MySQL 🛡️ | Authentication service database |
| JWT 🔑 | Authentication and authorization mechanism |

---

## 📂 Architecture Diagram
User → API Gateway → MongoDB (GridFS) → RabbitMQ → Converter Service → MongoDB → RabbitMQ → Notification Service → Email → User

## ⚡ Features

- Fully **containerized microservices** using Docker  
- **Distributed system** demonstrating async communication with RabbitMQ  
- **Large file storage** with MongoDB GridFS  
- **Authentication** using MySQL + JWT  
- **Kubernetes deployment** with Minikube for local testing  
- **Email notifications** on conversion completion  

---

