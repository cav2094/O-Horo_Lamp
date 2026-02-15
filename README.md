# COLORS - LAMP Stack Application

A web application built on the LAMP stack that allows users to log in and manage a personal collection of colors. Users can add new colors and search through their saved colors.

## Technologies Used

- **Linux** – Server operating system
- **Apache** – Web server
- **MySQL** – Relational database
- **PHP** – Server-side scripting language
- **HTML/CSS/JavaScript** – Frontend UI

## Project Structure

```
O-Horo_Lamp/
├── LAMPAPI/
│   ├── Login.php
│   ├── AddColor.php
│   ├── SearchColors.php
│   └── db_config.php (not tracked – contains credentials)
├── css/
│   └── styles.css
├── js/
│   ├── code.js
│   └── md5.js
├── images/
│   └── background.png
├── index.html
├── color.html
├── .gitignore
├── README.md
└── LICENSE.md
```

## Setup Instructions

1. Set up a LAMP server (Linux, Apache, MySQL, PHP).
2. Create a MySQL database named `COP4331` with the following tables:
   - `Users` – columns: `ID`, `firstName`, `lastName`, `Login`, `Password`
   - `Colors` – columns: `ID`, `UserID`, `Name`
3. Clone this repository into your Apache web root (e.g., `/var/www/html/`).
4. Create the database config file at `LAMPAPI/db_config.php` with the following format:
   ```php
   <?php
       $db_host = "localhost";
       $db_user = "your_username";
       $db_pass = "your_password";
       $db_name = "COP4331";
   ?>
   ```
5. Update the `urlBase` variable in `js/code.js` to match your server's domain.

## How to Run

1. Navigate to your server's URL in a web browser (e.g., `http://your-domain.com/`).
2. Log in with a valid username and password from the `Users` table.
3. Once logged in, you can:
   - **Add a color** by typing a color name and clicking "Add Color."
   - **Search colors** by typing a search term and clicking "Search Color."
4. Click "Log Out" to end your session.

## AI Usage

AI (Claude) was used to assist with generating this README file. I provided the AI with context about my project structure and asked it to help draft the documentation.

**Prompt used:** "I have a LAMP stack project for my COP 4331 class that lets users log in and manage a list of colors. The backend is PHP with MySQL and the frontend is plain HTML, CSS, and JavaScript. Can you help me write a README that includes a project description, technologies used, setup instructions, and how to run the application?"

The AI generated a draft of the README which I then reviewed and edited to ensure accuracy with my actual project structure and configuration.

## Assumptions and Limitations

- The application assumes a pre-existing MySQL database with the required tables and user accounts already created.
- Passwords are stored and compared in plain text (MD5 hashing is available but currently commented out).
- Session management is handled via browser cookies with a 20-minute expiration.
- The application is intended for use on a single LAMP server and is not configured for production deployment.
