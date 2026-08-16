<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Simple Interest Calculator</title>

    <style>
        * {
            box-sizing: border-box;
        }

        body {
            margin: 0;
            font-family: Arial, sans-serif;
            background: #f2f5f7;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
        }

        .calculator {
            background: white;
            width: 350px;
            padding: 30px;
            border-radius: 12px;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.15);
        }

        h1 {
            text-align: center;
            margin-bottom: 25px;
            color: #222;
        }

        label {
            display: block;
            margin-top: 15px;
            margin-bottom: 5px;
            font-weight: bold;
        }

        input {
            width: 100%;
            padding: 12px;
            border: 1px solid #ccc;
            border-radius: 6px;
            font-size: 16px;
        }

        button {
            width: 100%;
            margin-top: 25px;
            padding: 12px;
            border: none;
            border-radius: 6px;
            background: #218838;
            color: white;
            font-size: 17px;
            cursor: pointer;
        }

        button:hover {
            background: #1e7e34;
        }

        .result {
            margin-top: 25px;
            padding: 15px;
            background: #f0f8f0;
            border-radius: 6px;
            text-align: center;
            display: none;
        }

        .result p {
            margin: 8px 0;
            font-size: 17px;
        }
    </style>
</head>

<body>

    <div class="calculator">
        <h1>Simple Interest Calculator</h1>

        <label for="principal">Principal Amount (₹)</label>
        <input type="number" id="principal" placeholder="Enter principal">

        <label for="rate">Rate of Interest (%)</label>
        <input type="number" id="rate" placeholder="Enter annual rate">

        <label for="time">Time (Years)</label>
        <input type="number" id="time" placeholder="Enter time">

        <button onclick="calculateInterest()">Calculate</button>

        <div class="result" id="result">
            <p>Simple Interest: ₹<span id="interest">0</span></p>
            <p>Total Amount: ₹<span id="total">0</span></p>
        </div>
    </div>

    <script>
        function calculateInterest() {
            const principal = parseFloat(document.getElementById("principal").value);
            const rate = parseFloat(document.getElementById("rate").value);
            const time = parseFloat(document.getElementById("time").value);

            if (isNaN(principal) || isNaN(rate) || isNaN(time) ||
                principal < 0 || rate < 0 || time < 0) {
                alert("Please enter valid positive values.");
                return;
            }

            // Simple Interest = (P × R × T) / 100
            const simpleInterest = (principal * rate * time) / 100;
            const totalAmount = principal + simpleInterest;

            document.getElementById("interest").textContent =
                simpleInterest.toFixed(2);

            document.getElementById("total").textContent =
                totalAmount.toFixed(2);

            document.getElementById("result").style.display = "block";
        }
    </script>

</body>
</html>
