This project was made as a part of Superjoin Assignment



### Objective

Build a solution that enables real-time synchronization of data between a Google Sheet and a specified database (e.g., MySQL, PostgreSQL). The solution should detect changes in the Google Sheet and update the database accordingly, and vice versa.

### Problem Statement

Many businesses use Google Sheets for collaborative data management and databases for more robust and scalable data storage. However, keeping the data synchronised between Google Sheets and databases is often a manual and error-prone process. Your task is to develop a solution that automates this synchronisation, ensuring that changes in one are reflected in the other in real-time.

## Requirements

### Real-time Synchronization

- Implemented a system that detects changes in Google Sheets and updates the database accordingly.
- Similarly, detects changes in the database and updates the Google Sheet.

### CRUD Operations

- Supported Create, Read, Update, and Delete operations for both Google Sheets and the database.
- Maintained data consistency across both platforms.

### Optional Challenge: Scalability

- Ensured the solution can handle large datasets and high-frequency updates without performance degradation.
- Optimized for scalability and efficiency.

## Approach

### Overview

1. **Setup Flask Application**:

   - Created a Flask application to handle webhook requests from Google Sheets and update the database accordingly.
   - Implemented logging to track changes and actions taken during synchronization.

2. **Google Sheets Integration**:

   - Configured Google Sheets API to listen for changes using webhooks.
   - Set up endpoints to receive updates from Google Sheets and update the database in real-time.

3. **Database Integration**:

   - Developed functions to handle CRUD operations in the database.
   - Ensured updates made in the database are reflected back to Google Sheets.

4. **Logging**:

   - Implemented logging to record changes, actions, and conflicts during synchronization.
   - Logs are stored in `logs/db_changes.log` for easy tracking and debugging.

5. **Environment Configuration**:
   - Created a `.env` file for storing environment-specific variables.
   - Configured `credentials.json` for Google Sheets API access.

### Setup Instructions

1. **Clone the Repository**:
   ```bash
   git clone <repository-url>
   cd <repository-directory>
   ```

<!-- 2. **Create and Activate a Virtual Environment**:
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows use `venv\Scripts\activate`
   ``` -->

2. **Install Dependencies**:

   ```bash
   pip install -r requirements.txt
   ```

3. **Configure Environment Variables**:

   - Update the necessary details in `.env` file in the root directory with the following content:
     ```
     GOOGLE_SHEET_ID=<your-google-sheet-id>
     DB_HOST=<database-host>
     DB_USER=<database-user>
     DB_PASSWORD=<database-password>
     DB_NAME=<database-name>
     ```

4. **Set Up Google Sheets API**:

   - Update your API credentials in `config\credentials.json`

5. **Run Flask Application with Ngrok**:

   - Start the Flask application:
     ```bash
     python app.py
     ```
   - Use Ngrok to expose the Flask app to the internet:
     ```bash
     ngrok http 5000
     ```
   - Update the webhook URL in Google Sheets to point to the Ngrok URL.

6. **Add Google Apps Script**:
   - In your Google Sheets, go to Extensions > Apps Script.
   - Replace the existing code with the provided Apps Script to send updates to your Flask webhook.

## Developer's Section

### Video Demo

Here's a [demo video](https://drive.google.com/drive/folders/1xQ-O2TZ-53d1o_V5S1ytxvZbeFawYMUZ?usp=sharing) showcasing the working project.

### Approach Explanation

1. **Real-Time Synchronization**:

   - Implemented real-time synchronization by using webhooks from Google Sheets and a Flask application to handle updates.

2. **CRUD Operations**:

   - Added functionality to perform CRUD operations on both Google Sheets and the database, maintaining data consistency.

3. **Logging**:

   - Included logging to track changes and actions in `logs/db_changes.log`, helping in debugging and tracking.

4. **Scalability**:
   - Optimized the solution to handle large datasets and frequent updates.

### Comments

- The code is organized into logical modules for ease of maintenance and understanding.
- Detailed comments are included to explain the purpose of different functions and configurations.
