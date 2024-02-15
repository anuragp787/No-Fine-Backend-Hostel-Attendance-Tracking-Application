# No Fine - Hostel Attendance Tracking Application

**No Fine** is an application designed for Christ University Hostel (K E Hall, Jonas Hall etc.) residents to track their attendance. It automates the attendance tracking process and notifies users to mark their attendance to avoid fines imposed for non-compliance. The Python backend script of the application listens for HTTP POST requests from the Android frontend. The request payload includes the username, password, and timestamp. Subsequently, the script logs into the user's Knowledge Pro profile and retrieves attendance data. Based on this data, the script responds with 'P' for 'Present' and 'A' for 'Absent'.

The backend functionality is summarized as follows:
1. Automated login and data extraction are facilitated through the use of the Selenium package.
2. An ML model, trained on Knowledge Pro Captchas, is employed for login authentication.

## Deployment

A free-tier AWS VPS can be used for hosting this project. To deploy and run this project on your personal VPS, follow these steps:

1. Clone the repository:

    ```bash
    git clone https://github.com/anuragp787/No-Fine-Backend-Hostel-Attendance-Tracking-Application.git
    ```
    
3. Install the following python libraries:
   
    ```bash
    pip install Flask
    pip install selenium
    pip install pillow
    pip install opencv-python-headless
    pip install tensorflow
    pip install mltu
    pip install numpy
    ```
    
4. Run the main.py file. Subsequently, the script will run on http://localhost:5000/ , actively listening to incoming POST requests.

5. Download and authenticate ngrok from https://ngrok.com/ .

6. Run the ngrok.exe file and execute the following command:
   
   ```bash
    ngrok.exe http 5000
    ```

7. Paste the tunnel link provided by ngrok and substitute it for the 'url' variable in the MainActivity.kt file in the frontend.

   ```bash
    your_ngrok_link/login
    ```
   A sample link might look like: https://73a9-13-200-255-111.ngrok-free.app .

8. To test your backend, you can run the following command on Windows Powershell to mimic the POST requests:

   ```bash
    Invoke-RestMethod -Uri "your_ngrok_tunnel_link/login" -Method POST -ContentType "application/json" -Body '{"username": "your_kp_username", "password": "your_kp_password", "time": "1"}'
    ```

   In the request payload, setting the 'time' parameter to 0 corresponds to morning attendance tracking, while setting it to 1 corresponds to night attendance tracking.

## Screenshots

<p align="center"><img src="https://res.cloudinary.com/dgh9mcfxu/image/upload/v1707934140/Screenshot_2024-02-14-22-46-20-18_e3dfd801bae453b1d34e24dd12bbba4f_exkdso.jpg" alt="Alt text" width="420" height="800"></p>

<p align="center"><img src="https://res.cloudinary.com/dgh9mcfxu/image/upload/v1707934139/Screenshot_2024-02-14-08-40-15-95_b783bf344239542886fee7b48fa4b892_jw7le3.jpg" alt="Alt text" width="420" height="800">

## Download

**To uphold security and ensure data privacy, it is advisable to build your own APK and host the backend on a personal VPS server**

Download the application from the release section of the repository or scan this QR. Please note that the application may require maintenance, and the version you download might not function properly at the time of download. It's advisable to obtain the source code and build the application for optimal performance.

<img src="https://res.cloudinary.com/dgh9mcfxu/image/upload/v1707963789/No_FIne_Download_cymew2.png" alt="Alt text" width="300" height="300">
