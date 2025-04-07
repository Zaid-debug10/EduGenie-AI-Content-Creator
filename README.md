# EduGenie-AI-Content-Creator
Capstone project for Internshala Generative AI Course - A web-based tool to generate educational content using AI.
# EduGenie: AI-Powered Educational Content Creator

![EduGenie Screenshot](edugenie_screenshot.png)

A web-based tool to generate educational content, developed as a capstone project for the Internshala Generative AI Course.

## Project Overview
EduGenie is a web application that generates educational content based on a user-provided course title. It produces a course objective, sample syllabus, three measurable learning outcomes (aligned with Bloom's Taxonomy), assessment methods, and recommended readings. This project was developed to showcase skills in Generative AI, web development, and API integration (mock response used in this version).

## Features
- **User-Friendly Interface:** Input field for course title and a "Generate Content" button.
- **Content Generation:** Creates structured educational content, including objectives, syllabus, learning outcomes, assessments, and readings.
- **Bloom's Taxonomy Alignment:** Learning outcomes are designed to align with Bloom's Taxonomy levels (Analysis, Synthesis, Evaluation).
- **Error Handling:** Alerts the user if the course title is empty.
- **Copy Functionality:** Includes a "Copy" button to easily copy the generated content.
- **Data Privacy:** User inputs are not stored or logged, ensuring privacy.
- **Loading State:** Displays a "Generating content, please wait..." message during content generation.

## Tech Stack
- **Frontend:** HTML, CSS, JavaScript
- **API Integration:** Designed to work with OpenAI's API (mock response used in this version)
- **Future Scope:** Can be extended with a Python Flask backend for actual OpenAI API integration

Code 

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>EduGenie: AI-Powered Educational Content Creator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            max-width: 800px;
            margin: 0 auto;
            padding: 20px;
            background-color: #f4f4f4;
        }
        h1 {
            text-align: center;
            color: #333;
        }
        .input-section {
            margin-bottom: 20px;
        }
        input[type="text"] {
            width: 70%;
            padding: 10px;
            margin-right: 10px;
            border: 1px solid #ccc;
            border-radius: 4px;
        }
        button {
            padding: 10px 20px;
            background-color: #007bff;
            color: white;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }
        button:hover {
            background-color: #0056b3;
        }
        #output {
            background-color: white;
            padding: 20px;
            border-radius: 4px;
            box-shadow: 0 0 10px rgba(0,0,0,0.1);
            margin-top: 20px;
            white-space: pre-wrap;
        }
        #copyButton {
            background-color: #28a745;
            margin-top: 10px;
        }
        #copyButton:hover {
            background-color: #218838;
        }
        .privacy-notice {
            font-size: 0.9em;
            color: #666;
            margin-top: 20px;
            text-align: center;
        }
        #loading {
            display: none;
            color: #007bff;
            margin-top: 10px;
        }
    </style>
</head>
<body>
    <h1>EduGenie: AI-Powered Educational Content Creator</h1>
    <div class="input-section">
        <label for="courseTitle">Course Title:</label><br>
        <input type="text" id="courseTitle" placeholder="Enter the course title">
        <button onclick="generateContent()">Generate Content</button>
    </div>
    <div id="loading">Generating content, please wait...</div>
    <div id="output"></div>
    <button id="copyButton" style="display: none;" onclick="copyOutput()">Copy</button>
    <div class="privacy-notice">
        Data Privacy Notice: Your input data is used only to generate educational content and is not stored or logged.
    </div>

    <script>
        function generateContent() {
            const courseTitle = document.getElementById("courseTitle").value.trim();
            const outputDiv = document.getElementById("output");
            const loadingDiv = document.getElementById("loading");
            const copyButton = document.getElementById("copyButton");

            // Error handling: Check if course title is empty
            if (!courseTitle) {
                alert("Please enter a course title!");
                return;
            }

            // Show loading message
            loadingDiv.style.display = "block";
            outputDiv.innerHTML = "";
            copyButton.style.display = "none";

            // Simulate API call (mock response since we can't call OpenAI API directly here)
            setTimeout(() => {
                // Mock response based on the expected output for "Operating Systems"
                const mockResponse = `
Objective of the Course:
This course aims to provide students with a comprehensive understanding of operating systems, their design, and implementation to build efficient operating systems.

Sample Syllabus:
1. Introduction to Operating Systems
2. Process Management
3. Memory Management
4. File Systems
5. I/O Systems

Measurable Learning Outcomes:
1. Students will be able to analyze (Bloom's Taxonomy: Analysis) the performance of different process scheduling algorithms.
2. Students will be able to design (Bloom's Taxonomy: Synthesis) a memory management system for a given operating system.
3. Students will be able to evaluate (Bloom's Taxonomy: Evaluation) the effectiveness of various file system implementations.

Assessment Methods:
1. Weekly quizzes to test understanding of concepts.
2. A mid-term project to design a component of an operating system.
3. Final exam covering all topics with practical and theoretical questions.

Recommended Readings:
1. "Operating System Concepts" by Abraham Silberschatz, Peter B. Galvin, and Greg Gagne.
2. "Modern Operating Systems" by Andrew S. Tanenbaum.
3. "Operating Systems: Internals and Design Principles" by William Stallings.
                `;

                // Display the output
                loadingDiv.style.display = "none";
                outputDiv.innerHTML = mockResponse;
                copyButton.style.display = "block";
            }, 2000); // Simulate a 2-second API call delay
        }

        function copyOutput() {
            const outputText = document.getElementById("output").innerText;
            navigator.clipboard.writeText(outputText).then(() => {
                alert("Content copied to clipboard!");
            }).catch(err => {

   Author
Zaid Selia

LinkedIn: Zaid Selia
Email: [zaidselia61@gmail.com]
Acknowledgments
Internshala for providing the Generative AI Course and project guidelines.
                alert("Failed to copy content: " + err);
            });
        }
    </script>
</body>
</html>
