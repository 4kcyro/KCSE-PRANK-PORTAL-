<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>KNEC Results Portal</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f2f2f2;
      text-align: center;
      padding: 40px;
    }
    .container {
      background: white;
      padding: 30px;
      max-width: 500px;
      margin: auto;
      border-radius: 10px;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
    }
    h1 {
      color: #006400;
    }
    input {
      width: 90%;
      padding: 10px;
      margin: 10px 0;
      border: 1px solid #ccc;
      border-radius: 5px;
    }
    button {
      background: #006400;
      color: white;
      padding: 10px 20px;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }
    .results {
      display: none;
      margin-top: 20px;
      text-align: left;
    }
    .badge {
      width: 80px;
      margin-bottom: 10px;
    }
    .footer {
      margin-top: 30px;
      font-size: 0.9em;
      color: gray;
    }
  </style>
</head>
<body>
  <div class="container">
    <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/4/4e/Coat_of_arms_of_Kenya_%28Official%29.svg/1200px-Coat_of_arms_of_Kenya_%28Official%29.svg.png" class="badge" alt="KNEC Badge"/>
    <h1>KNEC KCSE Results Portal</h1>
    <p>Enter your details below to view your 2025 KCSE results</p>
    <input type="text" id="name" placeholder="NAME: (Three Names)" />
    <input type="text" id="index" placeholder="INDEX: (11-digit number)" />
    <button onclick="showResults()">Check Results</button>

    <div class="results" id="results">
      <h2>KCSE 2025 Results</h2>
      <p><strong>Name:</strong> <span id="rName"></span></p>
      <p><strong>Index Number:</strong> <span id="rIndex"></span></p>
      <table style="width:100%; text-align:left; margin-top:10px;">
        <tr><th>Subject</th><th>Grade</th></tr>
        <tr><td>English</td><td id="s1"></td></tr>
        <tr><td>Kiswahili</td><td id="s2"></td></tr>
        <tr><td>Mathematics</td><td id="s3"></td></tr>
        <tr><td>Biology</td><td id="s4"></td></tr>
        <tr><td>Chemistry</td><td id="s5"></td></tr>
        <tr><td>Physics</td><td id="s6"></td></tr>
        <tr><td>CRE</td><td id="s7"></td></tr>
        <tr><td>History</td><td id="s8"></td></tr>
      </table>
      <p><strong>Mean Grade:</strong> <span id="mean"></span></p>
      <p style="color:red;"><em>Candidate advised to explore alternative talents such as TikTok, boda logistics, or maize roasting.</em></p>
    </div>

    <div class="footer">
      © 2026 Kenya National Examinations Comedy (KNEC) – Powered by Vibes & Inshallah™
    </div>
  </div>

  <script>
    const grades = ["D+", "D", "D-", "E"];
    function randomGrade() {
      return grades[Math.floor(Math.random() * grades.length)];
    }
    function showResults() {
      const name = document.getElementById("name").value;
      const index = document.getElementById("index").value;
      if (name.length < 5 || index.length !== 11) {
        alert("Please enter valid name and 11-digit index number.");
        return;
      }
      document.getElementById("rName").innerText = name;
      document.getElementById("rIndex").innerText = index;
      for (let i = 1; i <= 8; i++) {
        document.getElementById("s" + i).innerText = randomGrade();
      }
      document.getElementById("mean").innerText = randomGrade();
      document.getElementById("results").style.display = "block";
    }
  </script>
</body>
</html>
