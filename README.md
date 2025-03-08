# Intruder Detection for Modern Web Architectures

Project Description

With the rising concerns about unauthorized access and intrusions, there is a growing demand for robust security systems. This project aims to enhance security measures by leveraging advanced technologies to detect intruders promptly. The **Intruder Detection and Email Alerting System** is designed to identify unauthorized access and notify stakeholders via email and SMS alerts.

Features

- Real-time intruder detection using a connected camera and OpenCV.
- Captures and stores images of detected intruders.
- Sends an email and SMS alert with the captured image.
- Database storage to maintain logs of detection events.
- Facial recognition for authentication using OpenCV.
- Web-based interface for user management using Streamlit.
- Multi-layer verification to enhance security.
- 
Tech Stack

- **Programming Language:** Python
- **Frameworks/Libraries:** OpenCV, TensorFlow/Keras (if deep learning is used), Streamlit, Twilio (for SMS alerts), smtplib (for email notifications)
- **Database:** MySQL
- **Tools:** PyCharm/IntelliJ IDEA, Git
- 
Installation
1. Clone the repository:
   ```bash
   git clone 
   ```
2. Navigate to the project directory:
   ```bash
   cd IDSWA
   ```
3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
4. Set up the database:
   - Import `project_db.sql` into MySQL.
   - Configure database credentials in `project.py`.
   - 
Configuration

Email & SMS Alert Setup
1. Open `project.py` and configure the following SMTP settings:
   ```python
   EMAIL_ADDRESS = "your-email@gmail.com"
   EMAIL_PASSWORD = "your-email-password"
   SMTP_SERVER = "smtp.gmail.com"
   SMTP_PORT = 587
   RECEIVER_EMAIL = "recipient-email@gmail.com"
   ```
2. Configure Twilio settings for SMS alerts:
   ```python
   ACCOUNT_SID = "your-twilio-account-sid"
   AUTH_TOKEN = "your-twilio-auth-token"
   TWILIO_PHONE_NUMBER = "your-twilio-phone-number"
   RECIPIENT_NUMBER = "recipient-phone-number"
   ```
3. Enable **Less Secure Apps** for your email account or set up an **App Password** if using Gmail.
Database Structure
The MySQL database stores detection logs and user authentication details. Below is the schema:
```sql
CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    username VARCHAR(50) UNIQUE,
    password VARCHAR(255),
    email VARCHAR(100),
    image_path VARCHAR(255)
);

CREATE TABLE intrusions (
    id INT AUTO_INCREMENT PRIMARY KEY,
    timestamp DATETIME DEFAULT CURRENT_TIMESTAMP,
    image_path VARCHAR(255),
    status VARCHAR(50)
);
```
- `users` table stores login credentials and profile images.
- `intrusions` table logs intrusion detection events.
Usage
1. Start the application:
   ```bash
   python project.py
   ```
2. The system will start detecting intruders using the connected camera.
3. If an intruder is detected:
   - An image is captured and saved.
   - The image is stored in the database.
   - An email and SMS alert is sent to the registered contact.
Expected Output
When an intruder is detected, the console will display:
```
[ALERT] Intruder detected! Image saved as 'intruder_20240308.jpg'
[INFO] Email and SMS alert sent successfully.
```
Dependencies
- OpenCV
- NumPy
- Streamlit
- Twilio API
- CMake
- smtplib
- MySQL-connector-python
- TensorFlow/Keras (if deep learning is enabled)

