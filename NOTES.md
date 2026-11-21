Task Tracker – Week 1 Assessment Notes

 1. Improvements I Would Make

After exploring the frontend, backend, and database, I identified the following areas for improvement:

1. Better Error Handling

The frontend fetch requests do not have proper error handling. I would introduce error handling and user-friendly feedback so users know when an operation fails instead of having failures go unnoticed.

2. Input Validation

The application does not properly prevent empty task titles from being submitted. I would introduce validation on both the frontend and backend to ensure that required information is provided.

3. Responsive User Interface

The application currently uses a fixed width of 900px and basic inline styling. I would improve the layout to make it responsive and easier to use on mobile devices, tablets, and desktops.

4. Delete Confirmation

The application deletes tasks immediately when the Delete button is clicked. I would introduce a confirmation message to reduce accidental deletion.

2. AI Tools and Prompts Used

AI tool used: ChatGPT.

I used ChatGPT to explore the project structure, understand the frontend and backend implementation, examine database operations, and understand how data moves through the application.

The following prompts represent the main prompts used to guide my exploration:

Prompt 1: Frontend Exploration

Act as a Senior React Developer with strong experience in frontend and backend development and software architecture. I am exploring a Task Tracker application and want to understand its frontend. Examine the following codes and explain the React components, state management, hooks, event handlers, and user interface. Do not modify the code or assume functionality that is not present. Explain technical concepts in simple language and present the analysis in organised bullet points.

i used the above code to explore the app.jsx and main.jsx

Prompt 2: Backend Exploration

Act as a Senior Full-Stack Developer with strong experience in frontend and backend development. I am exploring a Task Tracker application  and want to understand its backend. Examine the following code and explain the backend logic, API endpoints, database operations, and how data flows between the frontend and backend. Do not modify code unless requested, and guide me step by step using simple explanations.

i used this to explore the server files codes

Prompt 3: Code Explanation

Act as a Senior Full-Stack Software Developer with experience in software development, debugging, and code architecture. Examine the code I provide and explain how it works, section by section. Identify possible bugs and errors. Do not invent functionality that is not present, and keep the explanation concise and beginner-friendly.

3. One Thing AI Got Wrong or Missed

During my exploration, I identified an important detail in the database implementation that needed closer examination.

The run() function in server/db.js retrieves last_insert_rowid() every time it executes, including during UPDATE and DELETE operations.

This returned ID is meaningful for an INSERT operation, but it may be stale or unrelated when the function performs an UPDATE or DELETE.

I noticed this by examining the actual implementation of run() and checking how the backend uses its return value. The server only relies on the returned ID when creating a task, so the existing update and delete operations still work.

This taught me that AI explanations should be checked against the actual source code rather than accepted without verification.