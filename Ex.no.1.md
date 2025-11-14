
# NAME:DHARMALINGAM 
# REG NO:212223040037
 
# Aim: 
To design and implement a binary counter using a push button switch as input, a seven-segment display as output, and Arduino Uno as the controller. 
  
# Components Required: 
1.	Arduino Uno R3 board – 1 
 
2.	Common cathode Seven Segment Display – 1 
 
3.	Push Button switch – 1 
 
4.	220Ω resistors – 7 (for limiting current to seven segment LEDs) 
 
5.	Breadboard – 1 
 
6.	Jumper wires – as required 
 
7.	USB cable for Arduino Uno 
 
  
## Theory / Overview of Components: 
1.	Arduino Uno 
 
○ A microcontroller board based on ATmega328P. 
 
○ Provides 14 digital I/O pins and 6 analog inputs. 
 
○ Used here to control the seven-segment display and detect button presses. 
 
2.	Seven Segment Display (Common Cathode) 
 
○ An electronic display device for displaying decimal numbers (0–9). 
 
○ Composed of 7 LEDs (labeled a–g). 
 
○ By turning on/off combinations of LEDs, digits can be displayed. 
 
3.	Push Button Switch 
 
○ A momentary switch that changes state when pressed. 
 
○ Used here as input to increment the counter. 
 
  
# Connection Diagram (Description): 
●	Seven segment pins a–g connected to Arduino digital pins 2–8 via 220Ω resistors. 
 
●	Common cathode connected to GND. 
 
●	Push button one side connected to Arduino digital pin 9, other side to GND, with internal pull-up resistor enabled in code. 
 
 
 
 
 
## CODE:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dharmalingam | Front-End Developer</title>
    
    <style>
/* ---------------------------------
   ADVANCED STYLES 
   --------------------------------- */
body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; /* Modern, clean font */
    margin: 0;
    padding: 0;
    line-height: 1.6;
    background-color: #121212; /* Dark Mode Background */
    color: #e0e0e0; /* Light text for contrast */
}

/* Header & Profile */
header {
    background-color: #1f1f1f; /* Slightly lighter dark background */
    text-align: center;
    padding: 40px 20px;
    border-bottom: 3px solid #00aaff; /* Accent color line */
}

header img {
    border-radius: 50%;
    border: 4px solid #333; /* Subtle border */
    margin-bottom: 15px;
    transition: transform 0.3s ease;
}

header img:hover {
    transform: scale(1.05); /* Interactive hover effect */
}

header h1 {
    font-size: 2.5em;
    color: #ffffff;
    margin: 5px 0 0;
}

/* Section Layout and Cards */
main {
    padding: 20px;
}

.section {
    padding: 30px;
    max-width: 900px;
    margin: 30px auto;
    background: #1f1f1f; 
    border-radius: 10px;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.5); /* Deep shadow effect */
}

.section h2 {
    color: #00aaff; /* Consistent accent color for headings */
    margin-bottom: 15px;
    border-bottom: 2px solid #333;
    display: inline-block;
    padding-bottom: 8px;
    font-weight: 600;
    font-size: 1.8em;
}

/* Skills List - Using Flexbox for a horizontal layout */
.skills-list {
    display: flex;
    flex-wrap: wrap;
    list-style: none;
    padding: 0;
    gap: 10px;
}

.skills-list li {
    background-color: #333;
    color: #fff;
    padding: 8px 15px;
    border-radius: 20px; /* Pill shape */
    font-size: 0.9em;
    font-weight: 500;
    transition: background-color 0.3s;
}

.skills-list li:hover {
    background-color: #00aaff;
    color: #121212;
}

/* Project Cards */
.section article {
    margin-bottom: 20px;
    padding: 15px;
    border-left: 4px solid #555; /* Subtle separation */
    transition: border-left-color 0.3s;
}

.section article:hover {
    border-left-color: #00aaff; /* Highlight on hover */
    background-color: #242424;
}

.section article h3 {
    color: #ffffff;
    font-weight: 600;
    margin-top: 0;
}

.section article p {
    color: #c0c0c0;
    font-size: 0.95em;
}

/* Footer & Contact */
footer {
    background: #1f1f1f;
    color: #fff;
    text-align: center;
    padding: 25px;
    margin-top: 40px;
    border-top: 3px solid #00aaff;
}

footer h2 {
    display: none; /* Hiding the H2 in the footer for a cleaner look */
}

footer p {
    margin: 5px 0;
}

footer a {
    color: #00aaff;
    text-decoration: none;
    transition: color 0.3s;
}

footer a:hover {
    color: #ffffff;
    text-decoration: underline;
}
    </style>
</head>
<body>

    <header id="top">
        <img src="1.jpg" alt="My Photo" width="150">
        <h1>Dharmalingam</h1>
        <p style="color: #00aaff; font-size: 1.2em; margin-top: 5px;">Aspiring Front-End Developer | CSE Student</p>
    </header>

    <main>
        <section class="section">
            <h2>About Me</h2>
            <p>
                Hello! I'm Dharmalingam, a passionate Computer Science student diving deep into web development. I'm focused on creating responsive, performant user interfaces using modern standards. My ultimate goal is to evolve into a full-stack developer, bridging the gap between engaging front-end experiences and robust back-end logic.
            </p> 	
        </section>

        <section class="section">
            <h2>Skills & Technologies</h2>
            <ul class="skills-list">
                <li>HTML5 & Semantic Markup</li>
                <li>CSS3 & Flexbox/Grid</li>
                <li>JavaScript (ES6+)</li>
                <li>Java (Core)</li>
                <li>React (Beginner)</li>
                <li>Firebase (Database)</li>
            </ul>
        </section>

        <section class="section">
            <h2>Featured Projects</h2>
            <article>
                <h3>Smart Inventory and Billing Management System</h3>
                <p>A comprehensive system designed to manage stock levels and automate billing. This project strengthened my understanding of database integration and application architecture.</p>
            </article>
            <article>
                <h3>Fish Market Price Tracker (FMPT)</h3>
                <p>A real-time price tracker built with HTML, CSS, JavaScript, and Firebase. Key learning outcomes included asynchronous data handling and simple state management.</p>
            </article>
            <article>
                <h3>CareerCoach AI (React)</h3>
                <p>A web application utilizing AI guidance to suggest career paths for students. Developed using **React** for the front-end and Firebase for data persistence.</p>
            </article>
        </section>

        <section class="section">
            <h2>Achievements & Recognition</h2>
            <ul>
                <li>Participated in the IBM Datathon 2025, focusing on data analysis and visualization.</li>
                <li>Continuously contributing to small personal projects to build out my GitHub profile.</li>
            </ul>
        </section>
    </main>

    <footer>
        <p>Get in Touch</p>
        <p>Email: <a href="mailto:smkd3081@gmail.com">smkd3081@gmail.com</a></p>
        <p>LinkedIn: <a href="#">(Your LinkedIn Profile)</a></p>
    </footer>

</body>
</html>
```
## CIRCUIT DIAGRAM: 
<img width="1907" height="936" alt="image" src="https://github.com/user-attachments/assets/3ea03cfd-5b79-468d-862a-b4631c4db0c0" />
<img width="1897" height="936" alt="image" src="https://github.com/user-attachments/assets/ba05e20b-8fb4-49dc-9769-490a456b84f8" />
 <img width="1903" height="939" alt="image" src="https://github.com/user-attachments/assets/0e21ca2c-97e0-4a1f-8a57-44454b70a9eb" />

## OUTPUT: 
<img width="1216" height="828" alt="Screenshot 2025-08-29 154621" src="https://github.com/user-attachments/assets/23439ad4-6ff9-4bc4-a13b-2618208b16b7" />
 
## RESULT: 
  program to perform binary counter operation using switch, seven segment and 
Arduino controller is successfully executed 
