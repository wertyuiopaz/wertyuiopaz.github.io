<!DOCTYPE html>
<html>
<head>
    <title>Custom Console</title>
</head>
<body>
    <h1>Custom Console Example</h1>

    <button id="showConsole">Show Console</button>

    <div id="console" style="display: none;">
        <h2>Console Output</h2>
        <textarea id="output" rows="10" cols="50" readonly></textarea>
        <input type="text" id="command" placeholder="Enter a command">
        <button id="execute">Execute</button>
    </div>

    <script>
        const showConsoleButton = document.getElementById("showConsole");
        const consoleDiv = document.getElementById("console");
        const outputTextarea = document.getElementById("output");
        const commandInput = document.getElementById("command");
        const executeButton = document.getElementById("execute");

        showConsoleButton.addEventListener("click", () => {
            consoleDiv.style.display = "block";
        });

        executeButton.addEventListener("click", () => {
            const command = commandInput.value;
            // You can execute custom JavaScript commands here and display the output.
            try {
                const result = eval(command);
                outputTextarea.value += `> ${command}\n${result}\n`;
            } catch (error) {
                outputTextarea.value += `> ${command}\nError: ${error}\n`;
            }
            commandInput.value = "";
        });
    </script>
</body>
</html>
