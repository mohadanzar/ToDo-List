
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ToDo List</title>
    <style>
        /* General styling */
        body {
            font-family: 'Arial', sans-serif;
            background: linear-gradient(135deg, #9ac2ff, #d2e0f7);
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            margin: 0;
            color: #444;
        }

        /* Container */
        .todo-container {
            background: #fff;
            padding: 20px 30px;
            border-radius: 10px;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
            max-width: 350px;
            width: 100%;
        }

        /* Title */
        h1 {
            text-align: center;
            margin-bottom: 20px;
            font-size: 24px;
            color: #333;
        }

        /* Input section */
        .input-group {
            display: flex;
            justify-content: space-between;
            margin-bottom: 20px;
        }

        #input {
            flex: 1;
            padding: 10px;
            border: 2px solid #ddd;
            border-radius: 5px;
            outline: none;
            font-size: 16px;
        }

        #input:focus {
            border-color: #9ac2ff;
        }

        button {
            padding: 10px 15px;
            border: none;
            border-radius: 5px;
            background: #85b1f3;
            color: white;
            font-size: 16px;
            cursor: pointer;
            margin-left: 10px;
        }

        button:hover {
            background: #9ac2ff;
        }

        /* List styling */
        #list-container {
            list-style: none;
            padding: 0;
        }

        li {
            display: flex;
            justify-content: space-between;
            align-items: center;
            background: #f9f9f9;
            padding: 10px 15px;
            border: 1px solid #ddd;
            border-radius: 5px;
            margin-bottom: 10px;
            transition: background 0.3s ease;
        }

        li:hover {
            background: #d2e0f7;
        }

        li button {
            background: #9ac2ff;
            font-size: 14px;
            padding: 5px 10px;
        }
    </style>
</head>

<body>
    <div class="todo-container">
        <h1>ToDo List</h1>
        <div class="input-group">
            <input id="input" type="text" placeholder="Add a new task...">
            <button onclick="add()">Add</button>
        </div>
        <ul id="list-container">
            <li>1St ToDo List
                <button onclick="deleteItem(event)">Delete</button>
            </li>
        </ul>
    </div>

    <script>
        var ul = document.getElementById("list-container");
        var input = document.getElementById("input");

        function add() {
            var task = input.value.trim();
            if (task) {
                var listItem = document.createElement("li");
                listItem.innerHTML =
                    task + " <button onclick='deleteItem(event)'>Delete</button>";
                ul.append(listItem);
                input.value = "";
                input.focus();
            } else {
                alert("Please enter a task!");
            }
        }

        function deleteItem(event) {
            event.target.parentElement.remove();
        }
    </script>
</body>

</html>
