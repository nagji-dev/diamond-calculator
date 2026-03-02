
<!DOCTYPE html>
<html>
<head>
    <title>Diamond Calculator</title>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        body {
            font-family: Arial;
            text-align: center;
            padding: 20px;
        }
        input {
            padding: 10px;
            margin: 5px;
            width: 80%;
            font-size: 16px;
        }
        button {
            padding: 10px 20px;
            font-size: 16px;
        }
        h2 {
            color: green;
        }
    </style>
</head>
<body>

<h1>Diamond Weight Calculator</h1>

<input type="number" id="diameter" placeholder="Enter Diameter (mm)">
<br>
<input type="number" id="depth" placeholder="Enter Total Depth (mm)">
<br>
<button onclick="calculate()">Calculate</button>

<h2 id="result"></h2>

<script>
function calculate() {
    var d = document.getElementById("diameter").value;
    var h = document.getElementById("depth").value;

    var weight = (d * d * h * 0.0061).toFixed(3);

    document.getElementById("result").innerHTML = 
        "Estimated Weight: " + weight + " carat";
}
</script>

</body>
</html>
