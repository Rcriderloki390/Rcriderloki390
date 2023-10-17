<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Controlled Brightness White Bulb</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #222;
            margin: 0;
        }

        #bulb {
            width: 200px;
            height: 200px;
            background-color: #fff;
            border-radius: 50%;
            box-shadow: 0 0 40px rgba(255, 255, 255, 0.5);
            transition: box-shadow 0.5s, background-color 0.5s;
        }
    </style>
</head>
<body>
    <div id="bulb"></div>
    <input type="range" id="brightnessControl" min="0" max="100" step="1" value="100">

    <script>
        const bulb = document.getElementById("bulb");
        const brightnessControl = document.getElementById("brightnessControl");

        brightnessControl.addEventListener("input", () => {
            const brightness = brightnessControl.value;
            const boxShadow = `0 0 ${brightness / 10}px rgba(255, 255, 255, 0.5)`;
            bulb.style.boxShadow = boxShadow;
            const newColor = `hsl(0, 0%, ${brightness}%)`;
            bulb.style.backgroundColor = newColor;
        });
    </script>
</body>
</html>
