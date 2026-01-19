# Verification-ai-based-
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Recharge Verification</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background: #f2f2f2;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }

        .box {
            background: white;
            padding: 20px;
            width: 300px;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0,0,0,0.2);
            text-align: center;
        }

        input {
            width: 90%;
            padding: 10px;
            margin: 10px 0;
        }

        button {
            padding: 10px;
            width: 100%;
            background: green;
            color: white;
            border: none;
            cursor: pointer;
            border-radius: 5px;
        }

        #result {
            margin-top: 15px;
            font-weight: bold;
        }
    </style>
</head>
<body>

<div class="box">
    <h2>Recharge Verification</h2>

    <input type="text" id="mobile" placeholder="Enter Mobile Number">

    <button onclick="verify()">Verify</button>

    <div id="result"></div>
</div>

<script>
    function verify() {
        let number = document.getElementById("mobile").value;
        let result = document.getElementById("result");

        if (number.length !== 10 || isNaN(number)) {
            result.style.color = "red";
            result.innerHTML = "❌ Invalid Mobile Number";
            return;
        }

        let first = number.charAt(0);
        let operator = "";

        if (first === "6" || first === "7") {
            operator = "Jio";
        } else if (first === "8") {
            operator = "Airtel";
        } else {
            operator = "VI";
        }

        result.style.color = "green";
        result.innerHTML = `
            ✅ Number Verified <br>
            📡 Operator: ${operator} <br>
            👤 Name: Demo User <br>
            📍 Circle: Tamil Nadu
        `;
    }
</script>

</body>
</html>
