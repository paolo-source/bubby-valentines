<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Will You Be My Valentine?</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Dancing+Script:wght@400;700&display=swap');
        
        body {
            font-family: 'Dancing Script', cursive;
            text-align: center;
            background: url('https://api16-normal-useast1a.lemon8-app.com/seo/image?item_id=7330353983586370054&index=2&sign=4f619e0e671811be28246c66e7feef06') no-repeat center center/cover;
            color: white;
            margin: 0;
            padding: 0;
            display: flex;
            flex-direction: column;
            justify-content: center;
            height: 100vh;
        }
        .container {
            background: rgba(0, 0, 0, 0.6);
            padding: 30px;
            border-radius: 10px;
            display: inline-block;
        }
        h1, h2 {
            font-size: 40px;
            font-weight: bold;
        }
        button {
            padding: 15px 25px;
            font-size: 22px;
            margin: 10px;
            cursor: pointer;
            border: none;
            border-radius: 5px;
            transition: background-color 0.3s, transform 0.2s;
        }
        .yes-btn { background-color: #ff4d6d; color: white; }
        .no-btn { background-color: #999; color: white; }
        button:hover {
            filter: brightness(1.2);
            transform: scale(1.05);
        }
        button:active, button.clicked {
            filter: brightness(0.9);
        }
        .hidden { display: none; }
    </style>
</head>
<body>
    <div class="container" id="question">
        <h1>Will you be my Valentine, my love?</h1>
        <button class="yes-btn" onclick="showDateOptions(this)">Yes</button>
        <button class="no-btn" onclick="alert('Maybe next time! 😢')">No</button>
    </div>
    
    <div class="container hidden" id="date-options">
        <h2>Select a date:</h2>
        <button onclick="showDinnerOptions(this, 'Feb 14, 2025')">February 14, 2025</button>
        <button onclick="showDinnerOptions(this, 'Feb 15, 2025')">February 15, 2025</button>
    </div>
    
    <div class="container hidden" id="dinner-options">
        <h2>Where do you want to go for dinner?</h2>
        <button onclick="sendResponse(this, 'Sentro')">Sentro</button>
        <button onclick="sendResponse(this, 'Ribs and Bibs')">Ribs and Bibs</button>
        <button onclick="sendResponse(this, 'New Spot in Taguanao')">New Spot in Taguanao</button>
        <button onclick="sendResponse(this, 'High Ridge')">High Ridge</button>
    </div>

    <script>
        function showDateOptions(btn) {
            document.getElementById('question').classList.add('hidden');
            document.getElementById('date-options').classList.remove('hidden');
            btn.classList.add('clicked');
        }

        function showDinnerOptions(btn, date) {
            localStorage.setItem('selectedDate', date);
            document.getElementById('date-options').classList.add('hidden');
            document.getElementById('dinner-options').classList.remove('hidden');
            btn.classList.add('clicked');
        }

        function sendResponse(btn, place) {
            const date = localStorage.getItem('selectedDate');
            const email = "montesinespaolojames@gmail.com";
            
            const mailtoLink = `mailto:${email}?subject=Valentine's Response&body=Yes! I chose ${date} for our date at ${place}.`;
            window.location.href = mailtoLink;
            alert('Response sent! ❤️');
            btn.classList.add('clicked');
        }
    </script>
</body>
</html>
