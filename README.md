# Ankit--Jadon
This is my Git Repository.
<br>
Author- Ankit Jadon
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>To-Do List App</title>
  <style>
    body {
      font-family: Arial;
      background:skyblue;
      display: flex;
      justify-content: center;
      margin-top: 50px;
    }

    .container {
      background: #fff;
      padding: 20px;
      width: 400px;
      border-radius: 10px;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
    }

    h2 {
      text-align: center;
    }

    input {
      width: 70%;
      padding: 8px;
    }

    button {
      padding: 8px;
      cursor: pointer;
    }

    ul {
      list-style: none;
      padding: 0;
    }

    li {
      background: #eee;
      margin: 5px 0;
      padding: 8px;
      display: flex;
      justify-content: space-between;
    }

    li.completed {
      text-decoration: line-through;
      color: gray;
    }
  </style>
</head>
<body>

<div class="container">
  <h2>To-Do List</h2>
  <input type="text" id="taskInput" placeholder="Enter task">
  <button onclick="addTask()">Add</button>

  <ul id="taskList"></ul>
</div>

<script>
  function addTask() {
    let input = document.getElementById("taskInput");
    let task = input.value;

    if (task === "") return;

    let li = document.createElement("li");
    li.innerText = task;

    // Mark complete
    li.onclick = function () {
      li.classList.toggle("completed");
    };

    // Delete button
    let delBtn = document.createElement("button");
    delBtn.innerText = "X";
    delBtn.onclick = function () {
      li.remove();
    };

    li.appendChild(delBtn);
    document.getElementById("taskList").appendChild(li);

    input.value = "";
  }
</script>

</body>
</html>
