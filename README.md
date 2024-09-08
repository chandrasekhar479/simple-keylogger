<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Simple Keylogger Example</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 20px;
            background-color: red;
        }
        #log {
            width: 100%;
            height: 300px;
            background-color: #fff;
            border: 1px solid #ccc;
            padding: 10px;
            overflow-y: scroll;
            font-family: monospace;
            white-space: pre-wrap;
        }
        p {
            font-size: 1.2em;
        }
    </style>
</head>
<body>
    <h1>Simple Keylogger Example</h1>
    <p>Start typing in the input box below, and your keystrokes will be logged:</p>
    <input type="text" id="inputBox" placeholder="Type something here..." style="width: 100%; padding: 10px; font-size: 1.2em;">
    <h2>Logged Keystrokes:</h2>
    <div id="log"></div>

    <script>
        const inputBox = document.getElementById('inputBox');
        const logDiv = document.getElementById('log');

        
        inputBox.addEventListener('keydown', function(event) {
            const key = event.key;
            logDiv.textContent += key;
        });

        
        function saveLogToFile(log) {
            const blob = new Blob([log], { type: 'text/plain' });
            const anchor = document.createElement('a');
            anchor.href = URL.createObjectURL(blob);
            anchor.download = 'keylog.txt';
            anchor.click();
        }

    </script>
</body>
</html>
