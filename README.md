
<!DOCTYPE html>
<html>
<head>
    <title>Diamond Weight Calculator</title>
    <style>
        body { font-family: Arial; text-align: center; background:#f2f2f2; }
        .box { background:white; padding:20px; width:300px; margin:auto; margin-top:50px; border-radius:10px; }
        input, select, button { width:100%; padding:10px; margin:10px 0; }
        button { background:green; color:white; border:none; font-size:16px; }
    </style>
</head>
<body>

<div class="box">
    <h2>Diamond Weight Calculator</h2>

    <select id="shape">
        <option value="round">Round</option>
        <option value="fancy">Fancy</option>
    </select>

    <input type="number" id="diameter" placeholder="Diameter / Length">
    <input type="number" id="depth" placeholder="Depth %">

    <button onclick="calculate()">Calculate Weight</button>

    <h3 id="result"></h3>
</div>

<script>
function calculate() {

    let shape = document.getElementById("shape").value;
    let dia = parseFloat(document.getElementById("diameter").value);
    let depth = parseFloat(document.getElementById("depth").value);

    if(isNaN(dia) || isNaN(depth)){
        document.getElementById("result").innerHTML = "Please enter values";
        return;
    }

    let weight;

    if(shape === "round"){
        weight = dia * dia * depth * 0.0061;
    }
    else if(shape === "fancy"){
        weight = dia * dia * depth * 0.0059;
    }

    document.getElementById("result").innerHTML = 
        "Estimated Weight: " + weight.toFixed(3) + " Carat";
}
</script>

</body>
</html>
