

To Do List App

A simple, clean, and user-friendly web-based **To-Do List application** built with HTML, CSS, and JavaScript. This app allows users to add, mark, and remove tasks efficiently.

## Features

- Add new tasks easily using the input box or the Enter key.  
- Mark tasks as completed with a single click.  
- Display “Completed” status beside finished tasks.  
- Remove tasks using the delete button (X).  
- Fully responsive and styled with clean UI design.

## Technologies Used

- **HTML5** – for page structure and layout.  
- **CSS3** – for styling, layout, and hover effects.  
- **JavaScript (Vanilla JS)** – for dynamic task creation, completion toggle, and deletion.

CODEING

<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>To-Do List App</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: Arial, sans-serif;
        }

   body {
            background: #f3f3f3;
            display: flex;
            justify-content: center;
            padding-top: 60px;
        }

   .todo-container {
            width: 350px;
            background: white;
            padding: 20px;
            border-radius: 12px;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
        }

  h1 {
            text-align: center;
            margin-bottom: 20px;
        }

   .input-section {
            display: flex;
            gap: 10px;
            margin-bottom: 20px;
        }

   #taskInput {
            flex: 1;
            padding: 10px;
            border: 1px solid #ccc;
            border-radius: 8px;
        }
    #addBtn {
            padding: 10px 15px;
            background: #4CAF50;
            color: white;
            border: none;
            border-radius: 8px;
            cursor: pointer;
        }

  #addBtn:hover {
            background: #45a049;
        }

   #taskList {
            list-style: none;
        }

  .task {
            display: flex;
            justify-content: space-between;
            align-items: center;
            background: #fafafa;
            padding: 10px;
            margin-bottom: 10px;
            border-radius: 8px;
        }

  .task.completed {
            text-decoration: line-through;
            color: gray;
        }

  .remove-btn {
            background: red;
            border: none;
            color: white;
            padding: 5px 8px;
            border-radius: 5px;
            cursor: pointer;
        }

      .remove-btn:hover {
           background: darkred;
      }
  </style>
</head>

<body>
   <div class="todo-container">
        <h1>To-Do List</h1>

  <div class="input-section">
            <input type="text" id="taskInput" placeholder="Enter your task..." />
            <button id="addBtn">Add</button>
        </div>

  <ul id="taskList"></ul>
    </div>
     <script>
       
 let addBtn = document.getElementById("addBtn");
        let taskInput = document.getElementById("taskInput");
        let taskList = document.getElementById("taskList");
    addBtn.addEventListener("click", addTask);

        
 taskInput.addEventListener("keypress", function (e) {
            if (e.key === "Enter") {
                addTask();
            }
        });

   
function addTask() {

  if (taskInput.value.trim() === "") {
        alert("Please enter a task!");
        return;
    }

   let li = document.createElement("li");
    li.className = "task";

   let taskText = document.createElement("span");
    taskText.textContent = taskInput.value;

    
   let statusText = document.createElement("span");
    statusText.textContent = "Completed";
    statusText.style.color = "green";
    statusText.style.fontSize = "12px";
    statusText.style.display = "none";

   taskText.addEventListener("click", function () {
    li.classList.toggle("completed");

   if (li.classList.contains("completed")) {
            statusText.style.display = "inline-block"; 
        } else {
            statusText.style.display = "none"; 
        }
    });

    
   let removeBtn = document.createElement("button");
    removeBtn.textContent = "X";
    removeBtn.className = "remove-btn";

   removeBtn.addEventListener("click", function () {
        li.remove();
    });

   // Append all items
    li.appendChild(taskText);
    li.appendChild(statusText);
    li.appendChild(removeBtn);

   taskList.appendChild(li);

   taskInput.value = "";
    taskInput.focus();
}

   </script>
</body>

</html>


OUTPUT

<img width="1900" height="999" alt="Screenshot 2025-11-17 202436" src="https://github.com/user-attachments/assets/6ebbd713-3b36-475f-9c73-8f2d4b75b2dd" />





