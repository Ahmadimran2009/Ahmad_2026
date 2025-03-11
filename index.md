---
layout: base
title: Trimester 2 restrospective final
description: Home page
hide: true
---
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Floating Stopwatch</title>
    <style>
        body {
            height: 200vh;
            font-family: Arial, sans-serif;
        }
        .stopwatch {
            position: fixed;
            bottom: 20px;
            right: 20px;
            background: black;
            color: white;
            padding: 15px;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.3);
            text-align: center;
        }
        button {
            margin: 5px;
            padding: 5px 10px;
            border: none;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <div class="stopwatch">
        <h2 id="display">00:00:00</h2>
        <button onclick="start()">Start</button>
        <button onclick="stop()">Stop</button>
        <button onclick="reset()">Reset</button>
    </div>
    <script>
        let timer;
        let seconds = 0, minutes = 0, hours = 0;
        let running = false;
        function start() {
            if (!running) {
                running = true;
                timer = setInterval(updateTime, 1000);
            }
        }
        function stop() {
            running = false;
            clearInterval(timer);
        }
        function reset() {
            stop();
            seconds = 0;
            minutes = 0;
            hours = 0;
            document.getElementById("display").innerText = "00:00:00";
        }
        function updateTime() {
            seconds++;
            if (seconds == 60) {
                seconds = 0;
                minutes++;
            }
            if (minutes == 60) {
                minutes = 0;
                hours++;
            }
            document.getElementById("display").innerText = 
                (hours < 10 ? "0" : "") + hours + ":" +
                (minutes < 10 ? "0" : "") + minutes + ":" +
                (seconds < 10 ? "0" : "") + seconds;
        }
    </script>
</body>


# introduction

Take A Byte is a website to find new recipies of many cuisines. Users can spin a wheel to help design or ask the AI chatbot. They can also post their own recipies that aren't on the website to further expand options.

I worked on the fridge feature. It is accessable through the main page and users can add their grocery to the fridge, and have their own virtual fridge

link to Khanban board-<a href="https://github.com/lalita1809/flocker_frontend_period4/issues/35">fridge feature</a>

#  5 points - 5 things you did over 12 weeks, Issues, burndown, presentation

## 1. fully functioning database that works with my feature

I added static data to begin with just for the formation of the database, but then was able to connect it with my feature and no have a fully functioning database

<img src="{{site.baseurl}}/images/database.png" alt="image">

## 2. CPT requirements

over the course of the whole trimester, I implemented the CPT requirements into my code as it is important for the college board exam and overall helped my code in general

Examples

Use of lists (rows), dictionaries (columns) for the databse.

The project uses a list (or database) to store groceries names and their quantities.
Data is fetched from a backend API and displayed dynamically in a table. (show database)

<img src="{{site.baseurl}}/images/dictionary.png" alt="image">
<img src="{{site.baseurl}}/images/list.png" alt="image">


Sequencing, selection, iteration

<img src="{{site.baseurl}}/images/iteration.png" alt="image">


## 3. CRUD operations

using postman/ inspect/ debugger, backend first then connect to frontend

My backend code consisted of all the CRUD operations which is is get, post, put and delete which I all successfully implemented into my feature(SHOW IT WORKING)

<img src="{{site.baseurl}}/images/api.png" alt="image">

## 4. refined frontend for better user experience

For my feature, the fridge I added confirmations when adding, deleting and editing items which ensures the best user experience and overall a smoother use of my feature

<img src="{{site.baseurl}}/images/confirmation.png" alt="image">


## 5. Played a key role in deployment

Encountered and resolved deployment errors:

Iterated through the deployment workflow.
Identified CORS issues preventing communication between the server and client.
Troubleshot outdated Nginx errors.
Resolved frontend fetch error by updating the Python URI.
Managed database updates by re-running db init whenever model files changed.

# 2 points - Full Stack Project Demo, including CPT requirement highlights, and N@tM feedback

<img src="{{site.baseurl}}/images/fridge.png" alt="image">

link to Fridge blog-<a href="http://127.0.0.1:4100/Ahmad_2026/2024/10/09/ahmads-random-stuff_IPYNB_2_.html">fridge feature</a>

# Big Ideas

# 🛠 Big Idea 1: Creative Development

My project solves a real-world problem by helping users manage their ingredients efficiently.
The user interface is interactive, making it easy to add, edit, and remove ingredients.
Creative problem-solving: The project helps users minimize food waste and discover recipes based on available ingredients.

# 📊 Big Idea 2: Data

The project collects and organizes ingredient data, allowing users to input, update, and remove items.
Data abstraction: Ingredients are stored in a structured format (list, table, or database).
Users can modify expiration dates and track ingredient usage, demonstrating effective data management.

# 🤖 Big Idea 3: Algorithms and Programming

Custom functions like addIngredient() process user input and update the UI.
Uses selection (if-statements for expiration warnings), iteration (loops to check ingredient lists), and sequencing to manage inventory dynamically.
Event-driven programming: Functions execute when users interact with buttons (e.g., adding/removing ingredients).

# 🌐 Big Idea 4: Computing Systems and Networks

Frontend communicates with a backend API, demonstrating networking concepts.
Uses HTTP requests to store and retrieve ingredient data from a server.
Shows how distributed computing enables real-time inventory tracking.

# 🌍 Big Idea 5: Impact of Computing

The project helps users track food supplies and reduce waste.
It promotes sustainability and smart meal planning by suggesting recipes based on available ingredients.
Shows how computing improves organization and efficiency in daily life.

# 🔥 Summary

✅ Creativity – Solves a real-world problem (food management).
✅ Data – Uses structured data storage for ingredients.
✅ Algorithms – Implements functions for tracking and managing food.
✅ Networking – Uses API for data persistence and updates.
✅ Impact – Helps users reduce waste and optimize meal planning.

This project demonstrates all five AP CSP Big Ideas in a meaningful way! 🚀

# N@M experience

## Armaghan's group

study buddy website which is a website where students can learn and track their studying
cool features such as quizzes in different topics, chat bot, Study session planers and more
Showcased a strong focus on creativity and dynamic study tips

## Travel- Arhaan's group

Developed a travel app focused on Paris vacations with a visually rich and structured design.
Integrated a location-based tool for real-time weather updates and outfit suggestions.
Featured high-quality imagery and an engaging layout for an immersive experience.
Used bold purple accents on the Paris page, which could be better aligned with the overall design.
Delivered a dynamic and captivating presentation that kept the audience engaged.

# Neptune: A Club Hub for Students 

Explored Neptune, a website for finding and joining clubs.
Features a clean design and smooth navigation for easy browsing.
Includes a leadership application system for direct position applications.
Could improve with:
A more engaging theme for better visuals.
Interactive club pages with events and messaging.
A personalized recommendation system based on interests.
Overall, a great tool that could be even better with updates.

<img src="{{site.baseurl}}/images/high.png" alt="image">
<img src="{{site.baseurl}}/images/night.png" alt="image">
<img src="{{site.baseurl}}/images/gta.png" alt="image">
<img src="{{site.baseurl}}/images/shayan.png" alt="image">


# 1 point - Project Feature blog write up, using CPT/FRQ language

<img src="{{site.baseurl}}/images/frq.png" alt="image">

Instructions for input: Users enter groceries and quantities into a virtual fridge, interacting with the system through a user interface.

Use of a collection type: A list (or database) is used to store groceries and their quantities. This data is retrieved from a backend API and displayed in a structured table.

A procedure that contributes to the program’s purpose:

addGrocery() is defined to accept user input, retrieve the current fridge data, and send a POST request to update the database.
This procedure includes parameters for grocery name and quantity.
An algorithm that includes sequencing, selection, and iteration:

Sequencing: The function follows a step-by-step process to take input, validate it, and send the data to the backend.
Selection: Error handling ensures that invalid inputs are managed appropriately.
Iteration: Loops process multiple groceries when retrieving or displaying data.
Calls to student-developed procedures:

fetchItems() retrieves all groceries stored in the fridge.
removeItem() locates a specific grocery item and removes it from the database.
Instructions for output: The program dynamically updates a table displaying the stored groceries. Users can interact with buttons to update or delete entries based on their input.

# 1 point - MCQ

Total score 59/67 (huge improvement from last time)

Total time spent- 03:26:23

<img src="{{site.baseurl}}/images/newmcq.png" alt="image">

## weaknesses and how I will improve

Legal and ethical concerns- The one question I got wrong was number 51, as I did not fully understand all of the temrinology. I need to remember Creative Commons licensing allows copyright owners to specify the ways in which their works can be used or distributed. This allows individuals to access or modify these works without the risk of violating copyright laws.

Binary- I understand binary to a level but i find it difficult when binary is combined with other aspects. I will review the questions I got wrong, rewatch AP videos, and try to learn as much binary I can with the help of my dad who is really good binary

Identifying and correcting errors- Evaluate all options. I have a general idea of the answers because I got at least one question correct, but I need to be more careful when evaluating the second option and should read all choices rather than finding an option and moving on. Rewatch 1.4 Daily AP Videos 1-3.

# 10th point (hopefullyyy)

# Reflection on project by creating next steps plans, strengths, weaknesses

## Strengths of the Project:

Well-organized and structured approach to problem-solving.
Innovative features that improve user experience.
Strong application of computer science principles for reliable functionality.

## Weaknesses of the Project:

Certain areas need further refinement and testing.
Some design and functionality aspects could be improved based on user feedback.

## Next Steps:

Enhance coding skills to improve implementation.
Gather feedback for fresh perspectives and to avoid a narrow focus.
Refine features and usability based on testing results.
Continuously iterate to add more value and functionality.

## Strengths:

Determined – Stay focused on solving problems, even when they are difficult.
Composed – Stay level-headed under pressure, enabling clear decision-making.
Flexible – Adapt quickly to new challenges and learn from mistakes.
Creative – Think outside the box to find unique solutions.
Well-Organized – Maintain structure and efficiency in tasks.

## Weaknesses:

Limited coding experience – Occasionally struggle with technical implementation.
Tunnel vision – Sometimes focus too much on one approach instead of considering alternatives.

## career 

I aim to pursue a career in biomedical engineering, combining my interests in medicine and technology. As a high school student, the closest opportunities to the medical field are through research and internships, so I plan to apply for various positions using my CSP skills and expand on them. In 12th grade, I intend to take CSA to strengthen my programming knowledge. In college, I want to major in neuroscience, allowing me to apply my CS skills to biomedical research. With this foundation, I can explore neural networks to understand how the brain processes information and build a strong CS and biomedical portfolio for future opportunities.

## Review preperation

<img src="{{site.baseurl}}/images/help.png" alt="image">

## Self grade 

| **Category** | **Points** | **Score** | **Notes** |
|-------------|-----------|-----------|----------|
| **5 Things Over 12 Weeks** | 5 | 0.9 each | Issues, burndown, presentation: 4/5 |
| **Full Stack Project Demo** | 2 | 0.9 each | Could be more specific on CPT requirements |
| **Project Feature Blog Write-up** | 1 | 0.9 | Should bold CPT/FRQ language, use explicit examples |
| **MCQ** | 1 | 0.93 | Scored 9/10 |
| **Retrospective Reflection** | 1 | 0.9 | Could be more detailed |
| **Engagement at N@tM** | 1 | 0.9 | Took interest in other projects, personalization |
| **Helping a New Person** | 1 | 1.0 | Helped Armaghan Zarak P2 with exam prep |
| **Future Plans in CompSci** | 1 | 0.91 | Needs more detail |
| **Strengths & Weaknesses Reflection** | 1 | 0.9 | Could be more detailed |
| **Next Steps for Project** | 1 | 0.9 | Did not mention, but chatbot improvement needed |
| **Summary Sent 24 Hours Before Review** | - | 1.0 | Included honest self-grade assessment |
| **Final Average** | **10** | **9.1** | - |
