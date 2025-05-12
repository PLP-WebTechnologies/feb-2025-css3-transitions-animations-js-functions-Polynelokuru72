<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Interactive Webpage</title>
    <style>
        /* Define the CSS animation */
        @keyframes moveBox {
            0% {
                transform: translateX(0);
            }
            100% {
                transform: translateX(300px);
            }
        }

        /* Styling for the box */
        .box {
            width: 100px;
            height: 100px;
            background-color: red;
            margin: 20px;
            transition: transform 2s ease-in-out;
        }

        /* Class to trigger the animation */
        .animate {
            animation: moveBox 2s ease-in-out forwards;
        }

        /* Simple button style */
        button {
            padding: 10px 20px;
            font-size: 16px;
            cursor: pointer;
        }
    </style>
</head>
<body>

    <h1>Interactive Webpage with Animation and Local Storage</h1>

    <!-- Box to animate -->
    <div id="myBox" class="box"></div>

    <!-- Button to trigger animation -->
    <button id="animateBtn">Start Animation</button>

    <br><br>

    <!-- Store username in localStorage and display -->
    <h2>Enter your name:</h2>
    <input type="text" id="usernameInput">
    <button id="saveUsernameBtn">Save Username</button>

    <p id="greeting"></p>

    <script>
        // Store username in localStorage
        document.getElementById('saveUsernameBtn').addEventListener('click', function() {
            const username = document.getElementById('usernameInput').value;
            if (username) {
                localStorage.setItem('username', username);  // Save the username in localStorage
                document.getElementById('greeting').textContent = `Hello, ${username}! Welcome back.`;
            }
        });

        // Check if username is already stored in localStorage
        const storedUsername = localStorage.getItem('username');
        if (storedUsername) {
            document.getElementById('greeting').textContent = `Hello, ${storedUsername}! Welcome back.`;
        }

        // Trigger the animation when button is clicked
        document.getElementById('animateBtn').addEventListener('click', function() {
            document.getElementById('myBox').classList.add('animate');
        });
    </script>

</body>
</html>
