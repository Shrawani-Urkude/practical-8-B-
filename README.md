# practical-8-B-
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>College Registration Form</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #f0f5f9;
      padding: 20px;
    }
    h2 {
      text-align: center;
      color: #2c3e50;
    }
    form {
      background-color: #fff;
      padding: 20px;
      border-radius: 10px;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
      max-width: 500px;
      margin: 0 auto;
    }
    label {
      display: block;
      margin-top: 10px;
      font-weight: bold;
    }
    input, select {
      width: 100%;
      padding: 8px;
      margin-top: 5px;
      border-radius: 5px;
      border: 1px solid #ccc;
    }
    button {
      margin-top: 15px;
      padding: 10px 15px;
      background-color: #3498db;
      border: none;
      color: white;
      border-radius: 5px;
      cursor: pointer;
      width: 100%;
      font-size: 16px;
    }
    button:hover {
      background-color: #2980b9;
    }
    #message {
      margin-top: 20px;
      text-align: center;
      font-weight: bold;
    }
  </style>
</head>
<body>

  <h2>College Registration Form</h2>
  <form id="regForm">
    <label>Full Name:</label>
    <input type="text" id="name" placeholder="Enter your full name">

    <label>Age:</label>
    <input type="number" id="age" placeholder="Enter your age">

    <label>Email:</label>
    <input type="email" id="email" placeholder="Enter your email">

    <label>Phone Number:</label>
    <input type="text" id="phone" placeholder="Enter your phone number">

    <label>Gender:</label>
    <select id="gender">
      <option value="">--Select Gender--</option>
      <option>Male</option>
      <option>Female</option>
      <option>Other</option>
    </select>

    <label>Course:</label>
    <select id="course">
      <option value="">--Select Course--</option>
      <option>B.Sc Computer Science</option>
      <option>B.Com</option>
      <option>B.A English</option>
      <option>BBA</option>
    </select>

    <button type="button" onclick="validateForm()">Register</button>
  </form>

  <div id="message"></div>

  <script>
    // Function to validate form
    function validateForm() {
      // Get form values
      let name = document.getElementById("name").value.trim();
      let age = parseInt(document.getElementById("age").value);
      let email = document.getElementById("email").value.trim();
      let phone = document.getElementById("phone").value.trim();
      let gender = document.getElementById("gender").value;
      let course = document.getElementById("course").value;
      let msg = document.getElementById("message");

      // Conditional Statements for Validation
      if (name === "" || isNaN(age) || email === "" || phone === "" || gender === "" || course === "") {
        msg.style.color = "red";
        msg.innerHTML = "⚠️ Please fill all the fields!";
      } 
      else if (age < 18) {
        msg.style.color = "orange";
        msg.innerHTML = "⚠️ You must be at least 18 years old to register.";
      } 
      else {
        msg.style.color = "green";
        msg.innerHTML = "✅ Registration Successful! Welcome, " + name + "!";
      }
    }
  </script>

</body>
</html>
