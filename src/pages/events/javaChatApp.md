---
title: Java Chat Application
slug: chat-application
date: 2019-1-3
author: Atharva Joshi
read_time: 1
tags: ["Java", "MySQL", "JDBC"]
order: 2
hero: https://raw.githubusercontent.com/atharva20-coder/devatharva.com/master/src/images/posts/project-imgs/chat.png
draft: false
past: false
emoji: "❝ ❞"
---

## Java Chat App 💬

The Java Chat App is a desktop-based chat application developed using Java and MySQL. It utilizes Socket programming for communication and MySQL for user authentication and storage of profile information. The application allows users to send messages, create/join chat rooms, upload profile images, and customize the app theme.

### Key Features 🚀

- **Real-time Messaging**: Utilizes Socket programming for fast and reliable communication between clients.
- **User Authentication**: Stores user credentials securely in MySQL for login and authentication.
- **Profile Management**: Allows users to upload profile images and update user information.
- **Customizable Chat Rooms**: Users can create and join chat rooms based on interests or topics.
- **Theme Customization**: Provides options to change the app theme for personalized user experience.

### Project Preview 📷

![Java Chat App Preview](https://raw.githubusercontent.com/atharva20-coder/java-Chat-app/master/chat%20app.png)

### Project Setup 🛠️

To set up this project, follow these steps:

1. **Import MySQL Connector**:

   - Download the MySQL Connector JAR file and add it to your project's library.

2. **Database Setup**:

   - Create a MySQL database named `chat` using the following query:
     ```sql
     create database chat;
     ```
   - Switch to the `chat` database:
     ```sql
     use chat;
     ```
   - Import the provided SQL file (`chat.sql`) into your MySQL database to set up tables:
     ```sql
     source {path of the file}/chat.sql;
     ```

3. **Run the Project**:
   - Open the project in your IDE.
   - Update MySQL password if JDBC connection errors occur.
   - Run the project to launch the Java Chat App.
   - First run the server then launch the clients

### Links 🔗

<div style="display: flex; flex-wrap: wrap; gap: 10px;">

<div style="flex: 1; min-width: 150px; border: 1px solid #ddd; border-radius: 5px; padding: 10px; text-align: center;">
  <a href="https://github.com/atharva20-coder/java-Chat-app" target="_blank" style="display: flex; align-items: center; justify-content: center;">
    <svg height="24" width="24" viewBox="0 0 16 16" version="1.1" aria-hidden="true" style="fill: #000; margin-right: 5px;">
      <path fill-rule="evenodd" d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.45.55.38A8.013 8.013 0 0 0 16 8c0-4.42-3.58-8-8-8z"></path>
    </svg>
    GitHub Repository
  </a>
</div>

</div>

<br>

---

Enjoy chatting with friends and colleagues using the Java Chat App! 🌐💬
