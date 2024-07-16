---
title: Laboratory Management System 🛢️
slug: laboratory-manageent-system
date: 2022-10-3
author: Atharva Joshi
read_time: 1
tags: ["Java", "MySQL"]
order: 2
hero:
draft: false
past: false
emoji: "🛢️"
---

The Digital Phone Directory is a desktop-based application built using Java and MySQL that allows users to store, manage, and search for phone numbers and contact information. The application includes several features that enhance the user experience, including the ability to add, edit, and delete contact information, search for contacts using keywords, and sort contacts by name or phone number.

### Key Features 🌟

- **Comprehensive Contact Management**: Store, manage, and search for contact information including name, phone number, email address, and other relevant details.
- **Database Integration**: Uses MySQL to store and manage contact information, ensuring fast and reliable access through JDBC.
- **Cross-Platform Compatibility**: Developed using Java, allowing for easy deployment on various operating systems.
- **User-Friendly Interface**: Modern and intuitive interface optimized for desktop devices.

### Project Preview 👁️

![screenhot](https://user-images.githubusercontent.com/69634375/236899887-cb023a1b-fd3a-4380-b447-6f524250ed60.png)

![Screenshot](https://user-images.githubusercontent.com/69634375/232675406-ee85aacf-ac47-4517-80ee-c9a90051bf4e.png)

![Screenshot](https://user-images.githubusercontent.com/69634375/232675425-5b1a8e06-c38e-4bda-897e-2a063c47a27a.png)

### Project Setup ⚙️

1. **Download and Extract**: After downloading and extracting, open this project in your IDE.
2. **Add MySQL Connector**: Right-click on Library, then click Add JAR/Folder. Locate your MySQL connector JAR file (included with this repository).

### Database Setup 🗄️

1. **Create Database**: In your SQL terminal, create a database named `phonedirectory` using the following query:
   ```sql
   create database phonedirectory;
   use phonedirectory;
   ```

![Screenshot](https://user-images.githubusercontent.com/69634375/236899905-e32579b1-644b-46e2-8678-e72c9bb7e8ca.png)

Import SQL File: Import the included SQL file by using the following query:

```sql
source {path of the file}/phone.sql;
```

### Links 🔗

<div style="display: flex; flex-wrap: wrap; gap: 10px;">

<div style="flex: 1; min-width: 150px; border: 1px solid #ddd; border-radius: 5px; padding: 10px; text-align: center;">
  <a href="https://github.com/atharva20-coder/Laboratory_Management_System?tab=readme-ov-file" target="_blank" style="display: flex; align-items: center; justify-content: center;">
    <svg height="24" width="24" viewBox="0 0 16 16" version="1.1" aria-hidden="true" style="fill: #000; margin-right: 5px;">
      <path fill-rule="evenodd" d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.45.55.38A8.013 8.013 0 0 0 16 8c0-4.42-3.58-8-8-8z"></path>
    </svg>
    GitHub Repository
  </a>
</div>

</div>

<br>

---
