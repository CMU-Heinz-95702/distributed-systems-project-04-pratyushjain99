[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/JRWw4q8L)

### Screenshots are attached in the PDF.
# Project 4 – pratyusj

**Name:** Pratyush Jain  
**Email:** pratyusj@andrew.cmu.edu  

**Walkthrough:** [Narrated Screencast](https://youtu.be/8zqges5eskQ)  
If the link doesn’t work, please let me know at pratyusj@andrew.cmu.edu  

---

### **API Information**
- **API Name:** The Movie DB (TMDb)  
- **API Documentation:** [Getting Started](https://developer.themoviedb.org/docs/getting-started)  
- **Short Description:**  
  This application allows users to search for a movie or actor and retrieve essential details like release dates, ratings, and posters using the TMDb API. The app provides a simple way to access movie information without needing to search multiple platforms.

---

## **Project Overview**

### **1. Native Android Application**  
The Android app enables users to search for actors and recommends three movies from their filmography. The UI is built with components like TextView, EditText, Button, and RecyclerView. Users can enter an actor's name, and the app makes an HTTP request to the backend service, parses the JSON response, and displays movie details such as titles, release dates, and posters. Graceful error handling ensures that the app shows a "No movies found" message if the search yields no results.

---

### **2. Web Service**  
The backend web service is implemented in Java using Servlets, hosted initially on TomEE-plus and later deployed to GitHub Codespaces. It accepts an HTTP GET request with the actor's name as a query parameter, interacts with the TMDb API to fetch movie details, and returns the data in JSON format. The service ensures consistency in responses, logs requests, and processes third-party API responses to integrate seamlessly with the Android app.

---

### **3. Error Handling**  
Error handling is implemented on both the app and backend. The app validates input and displays meaningful error messages for network issues or invalid responses. The backend responds with a 400 Bad Request for invalid actor names and a 500 Internal Server Error for failures in communicating with TMDb. It filters out incomplete or missing data, such as missing names or bad API calls, ensuring a smooth user experience.

---

### **4. Logging Information**  
The backend logs six critical data points for each request:  
1. Actor's name.  
2. HTTP status code.  
3. Number of movies/pages returned.  
4. Timestamp.  
5. Origin of the request (app vs. other).  

This data is invaluable for debugging and analytics, enabling detailed tracking of app usage. The dashboard also displays all logs for transparency.

---

### **5. Persistent Logging with MongoDB**  
Logs are stored persistently in MongoDB Atlas, ensuring accessibility across application restarts. Each log entry includes the actor's name, status code, movie count, and timestamp. MongoDB’s Java Driver is used for CRUD operations (excluding deletions), ensuring efficient storage and retrieval of log data. The database enables detailed analysis and tracking.

---

### **6. Dashboard with Analytics and Logs**  
The dashboard is built using JSP and displays detailed analytics and logs in a web-based interface. Analytics include:  
- Total requests made.  
- Number of successful requests (HTTP 200).  
- Most searched actor.  
- Average number of movies returned.  
- Unique actors searched.  
- Success rate of requests.  

Logs are displayed in a tabular format, showing detailed information for each request, including timestamps, actor names, and results. This information is followed by a complete log list for reference.

---

### **7. Deployment to GitHub Codespaces**  
The web service was containerized and deployed to GitHub Codespaces. The deployment ensures that the service is accessible via a public URL, enabling seamless communication with the Android app. Rigorous testing validated successful integration, error handling, and API reliability.

---

**Walkthrough:** [Narrated Screencast](https://youtu.be/8zqges5eskQ)  
**Initial GitHub Repository:** [Project4-pratyusj](https://github.com/pratyushjain99/Project4-pratyusj)  
