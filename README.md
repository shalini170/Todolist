# Ex03 To-Do List using JavaScript
## Date:21/08/2026

## AIM
To create a To-do Application with all features using JavaScript.

## ALGORITHM
### STEP 1
Build the HTML structure (index.html).

### STEP 2
Style the App (style.css).

### STEP 3
Plan the features the To-Do App should have.

### STEP 4
Create a To-do application using Javascript.

### STEP 5
Add functionalities.

### STEP 6
Test the App.

### STEP 7
Open the HTML file in a browser to check layout and functionality.

### STEP 8
Fix styling issues and refine content placement.

### STEP 9
Deploy the website.

### STEP 10
Upload to GitHub Pages for free hosting.

## PROGRAM

## index.html
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>To-Do List</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

<div class="todo-container">
    <h1>To-Do List</h1>

    <div class="input-box">
        <input type="text" id="taskInput" placeholder="Enter a task">
        <button onclick="addTask()">Add</button>
    </div>

    <ul id="taskList"></ul>
</div>

<script src="script.js"></script>

</body>
</html>
```
## CSS
```
body {
    font-family: Arial, sans-serif;
    background: #f2f2f2;
    display: flex;
    justify-content: center;
    padding-top: 50px;
}

.todo-container {
    background: white;
    width: 400px;
    padding: 25px;
    border-radius: 10px;
}

h1 {
    text-align: center;
}

.input-box {
    display: flex;
    gap: 10px;
}

input {
    flex: 1;
    padding: 10px;
}

button {
    padding: 10px 15px;
    cursor: pointer;
}

li {
    display: flex;
    justify-content: space-between;
    margin-top: 10px;
    padding: 10px;
    background: #eee;
}

.completed {
    text-decoration: line-through;
}

.actions button {
    margin-left: 5px;
}
```

## JS
```
function addTask() {
    const input = document.getElementById("taskInput");
    const task = input.value.trim();

    if (task === "") {
        alert("Please enter a task");
        return;
    }

    const li = document.createElement("li");

    const span = document.createElement("span");
    span.textContent = task;

    span.onclick = function () {
        span.classList.toggle("completed");
    };

    const actions = document.createElement("div");
    actions.className = "actions";

    const editButton = document.createElement("button");
    editButton.textContent = "Edit";

    editButton.onclick = function () {
        const newTask = prompt("Edit task:", span.textContent);

        if (newTask !== null && newTask.trim() !== "") {
            span.textContent = newTask.trim();
        }
    };

    const deleteButton = document.createElement("button");
    deleteButton.textContent = "Delete";

    deleteButton.onclick = function () {
        li.remove();
    };

    actions.appendChild(editButton);
    actions.appendChild(deleteButton);

    li.appendChild(span);
    li.appendChild(actions);

    document.getElementById("taskList").appendChild(li);

    input.value = "";
}
```


## OUTPUT

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/6466878d-64c8-4b94-a01e-917070852fc4" />

## RESULT
The program for creating To-do list using JavaScript is executed successfully.
