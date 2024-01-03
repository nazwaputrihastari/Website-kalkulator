<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Kalkulator Matematik Segitiga</title>
    <link rel="stylesheet" href="css/styles.css">
</head>
<body>
    <div class="calculator">
        <h2>Kalkulator Segitiga</h2>

        <div class="triangle" id="triangle"></div>

        <label for="base">Alas: </label>
        <input type="number" id="base" placeholder="Masukkan panjang alas">

        <br>

        <label for="height">Tinggi: </label>
        <input type="number" id="height" placeholder="Masukkan tinggi">

        <br>

        <button onclick="calculate()">Hitung</button>
body {
    font-family: Arial, sans-serif;
    text-align: center;
    margin: 50px;
}

.calculator {
    border: 2px solid #ddd;
    padding: 20px;
    max-width: 300px;
    margin: 0 auto;
}

.triangle {
    width: 0;
    height: 0;
    border-left: 50px solid transparent;
    border-right: 50px solid transparent;
    border-bottom: 86.6px solid #3498db;
    margin: 10px auto;
}

input {
    padding: 8px;
    margin: 5px;
}

button {
    padding: 10px;
    margin-top: 10px;
    cursor: pointer;
}
function calculate() {
    const base = parseFloat(document.getElementById('base').value);
    const height = parseFloat(document.getElementById('height').value);

    if (!isNaN(base) && !isNaN(height)) {
        const area = 0.5 * base * height;
        const perimeter = base + (2 * calculateHypotenuse(base, height));
        
        document.getElementById('area').innerText = area.toFixed(2);
        document.getElementById('perimeter').innerText = perimeter.toFixed(2);
        displayTriangle(base, height);
    } else {
        alert("Masukkan angka yang valid.");
    }
}

function calculateHypotenuse(base, height) {
    return Math.sqrt(Math.pow(base, 2) + Math.pow(height, 2));
}

function displayTriangle(base, height) {
    const triangle = document.getElementById('triangle');
    triangle.style.borderLeftWidth = base + 'px';
    triangle.style.borderRightWidth = base + 'px';
    triangle.style.borderBottomWidth = height + 'px';
}
