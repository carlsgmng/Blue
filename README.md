<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dental Appointment Booking</title>
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/flatpickr/dist/flatpickr.min.css">
    <style>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: 'Roboto', sans-serif;
    background-color: #f4f6f9;
    color: #333;
    line-height: 1.7;
}

header {
    background-color: #004d74; 
    color: white;
    padding: 30px 0;
    text-align: center;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}

header h1 {
    font-size: 42px;
    font-weight: 700;
    letter-spacing: 2px;
}

nav {
    display: flex;
    justify-content: center;
    gap: 25px;
    margin-top: 15px;
}

nav a {
    color: white;
    font-size: 20px;
    font-weight: 500;
    text-decoration: none;
    transition: color 0.3s ease;
}

nav a:hover {
    color: #ffeb3b; 
}

.hero {
    display: flex;
    justify-content: center;
    align-items: center;
    background: #b3e5fc;
    padding: 120px 20px;
    text-align: center;
}

.hero h2 {
    font-size: 52px;
    color: #0277bd;
    margin-bottom: 20px;
    font-weight: 700;
}

.hero p {
    font-size: 20px;
    color: #0277bd;
    margin-bottom: 40px;
}

.cta-button {
    background-color: #0288d1;
    color: white;
    padding: 18px 36px;
    font-size: 22px;
    border: none;
    border-radius: 6px;
    cursor: pointer;
    transition: background-color 0.3s ease;
    box-shadow: 0 6px 12px rgba(0, 0, 0, 0.1);
}

.cta-button:hover {
    background-color: #01579b;
    box-shadow: 0 6px 15px rgba(0, 0, 0, 0.2);
}

.container {
    width: 90%;
    max-width: 1200px;
    margin: 70px auto;
}

.section-title {
    text-align: center;
    font-size: 40px;
    color: #004d74;
    margin-bottom: 60px;
    font-weight: 700;
}

.appointment-form {
    display: flex;
    justify-content: space-between;
    gap: 35px;
    flex-wrap: wrap;
}

.form-group {
    width: 48%;
    background-color: white;
    padding: 35px;
    border-radius: 15px;
    box-shadow: 0 6px 20px rgba(0, 0, 0, 0.1);
    margin: auto;
}

.form-group h3 {
    font-size: 24px;
    color: #0277bd;
    margin-bottom: 20px;
    font-weight: 600;
}

.form-group input,
.form-group select {
    width: 100%;
    padding: 15px;
    margin-bottom: 25px;
    border-radius: 10px;
    border: 1px solid #ccc;
    font-size: 16px;
    background-color: #f9f9f9;
    box-sizing: border-box;
    transition: border-color 0.3s ease, box-shadow 0.3s ease;
}

.form-group input:focus,
.form-group select:focus {
    outline: none;
    border: 1px solid #0288d1;
    box-shadow: 0 0 8px rgba(0, 136, 209, 0.3);
}

.form-group button {
    width: 100%;
    background-color: #0288d1;
    color: white;
    padding: 16px;
    font-size: 18px;
    border-radius: 10px;
    border: none;
    cursor: pointer;
    transition: background-color 0.3s ease;
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
}

.form-group button:hover {
    background-color: #01579b;
    box-shadow: 0 6px 18px rgba(0, 0, 0, 0.2);
}

.payment-section {
    margin-top: 60px;
    padding: 35px;
    background-color: #ffffff;
    border-radius: 15px;
    box-shadow: 0 6px 20px rgba(0, 0, 0, 0.1);
}

.payment-section h3 {
    font-size: 28px;
    color: #0277bd;
    margin-bottom: 25px;
    text-align: center;
    font-weight: 600;
}

.payment-methods {
    display: flex;
    justify-content: space-around;
    gap: 35px;
}

.payment-method {
    text-align: center;
    width: 160px;
    cursor: pointer;
    transition: transform 0.3s ease;
}

.payment-method:hover {
    transform: scale(1.05);
}

.payment-method img {
    width: 110px;
    height: 110px;
    margin-bottom: 20px;
    transition: transform 0.3s ease;
    border-radius: 50%;
}

.payment-method img:hover {
    transform: scale(1.1);
}

.payment-method p {
    font-size: 16px;
    color: #0277bd;
    font-weight: 600;
}

.dentist-profiles {
    display: flex;
    justify-content: space-around;
    margin-top: 60px;
}

.dentist-profile {
    text-align: center;
    width: 220px;
    background: #fff;
    padding: 25px;
    border-radius: 12px;
    box-shadow: 0 6px 20px rgba(0, 0, 0, 0.1);
    cursor: pointer;
    transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.dentist-profile:hover {
    transform: scale(1.05);
}

.dentist-profile.selected {
    border: 2px solid #0288d1;
    box-shadow: 0 0 10px rgba(0, 136, 209, 0.4);
}

.dentist-profile img {
    width: 120px;
    height: 120px;
    border-radius: 50%;
    margin-bottom: 15px;
}

.dentist-profile h4 {
    font-size: 22px;
    margin-top: 12px;
    font-weight: 600;
}

.dentist-profile p {
    font-size: 16px;
    margin-top: 8px;
    color: #555;
}

footer {
    background-color: #004d74;
    color: white;
    text-align: center;
    padding: 25px 0;
    margin-top: 60px;
}

footer p {
    font-size: 16px;
}

.receipt {
    display: none;
    padding: 20px;
    background-color: #ffffff;
    border-radius: 15px;
    box-shadow: 0 6px 20px rgba(0, 0, 0, 0.1);
    margin-top: 30px;
    text-align: center;
}

.payment-info {
    font-size: 18px;
    color: #0277bd;
    margin-top: 20px;
}

.payment-info a {
    color: #0277bd;
    text-decoration: none;
}

.payment-info a:hover {
    text-decoration: underline;
}

    </style>
</head>
<body>
<header>
    <h1>Dental Care Appointment</h1>
    <nav>
        <a href="#home">Home</a>
        <a href="#services">Services</a>
        <a href="#appointment">Appointment</a>
        <a href="#dentist-profiles">Dentists</a>
        <a href="#contact-section">Contact</a>
    </nav>
</header>

<section class="hero" id="home">
    <div>
        <h2>Grace's Dental Clinic</h2>
        <p>Where your SMILE matters. Schedule your appointment now.</p>
        <button class="cta-button">Appointment Now</button>
    </div>
</section>

<div class="container">
    <section>
        <h2 class="section-title" id="appointment">Choose Your Appointment</h2>
        <div class="appointment-form">
            <div class="form-group">
                <h3>Patient Details</h3>
                <label for="name">Full Name</label>
                <input type="text" id="name" placeholder="Your Full Name" required>
                <label for="contact">Contact Number</label>
                <input type="text" id="contact" placeholder="Contact Number" required>
                <label for="email">Email Address</label>
                <input type="email" id="email" placeholder="Email Address" required>
                <span id="email-error" style="color: red; display: none;">Invalid email format.</span>
            </div>
            <div class="form-group">
                <h3>Appointment Details</h3>
                <label for="appointment-date">Appointment Date</label>
                <input type="text" id="appointment-date" placeholder="Select Appointment Date" required>
                <label for="appointment-time">Appointment Time</label>
                <input type="time" id="appointment-time" required>
                <label for="services">Select Service</label>
                <select id="services" required>
                    <option value="">(Select Service)</option>
                    <option value="Consultation">Consultation</option>
                    <option value="Teeth Cleaning">Teeth Cleaning</option>
                    <option value="Teeth Whitening">Teeth Whitening</option>
                    <option value="Full and Partial Denture">Full and Partial Denture</option>
                    <option value="Braces Installation">Braces Installation</option>
                    <option value="Odondectomy">Odondectomy</option>
                    <option value="Root Canal">Root Canal</option>
                    <option value="Restoration">Restoration</option>
                </select>
                <span id="form-error" style="color: red; display: none;">Please fill out all fields correctly.</span>
            </div>
        </div>

        <section id="dentist-profiles">
            <h3>Meet Our Dentists</h3>
            <div class="dentist-profiles">
                <div class="dentist-profile" onclick="selectDentist(this)">
                    <img src="https://ucmed.ph/wp-content/uploads/2019/04/ABUGAN-1X1-500x500.jpg" alt="Portrait of Dentist 1">
                    <h4>Dr. Maricel Doronilla</h4>
                    <p>Specialty: Orthodontist</p>
                </div>
                <div class="dentist-profile" onclick="selectDentist(this)">
                    <img src="https://peterattiamd.com/wp-content/uploads/2019/09/ronesh-1x1.jpeg" alt="Portrait of Dentist 2">
                    <h4>Dr. Carlos Ortiz</h4>
                    <p>Specialty: Cosmetic Dentistry Specialist</p>
                </div>
            </div>
        </section>
<br>
        <div class="payment-section">
            <h3>Select Payment Method</h3>
            <div class="payment-methods">
                <div class="payment-method" onclick="selectPayment(this, 'BPI')">
                    <img src="https://app.aranetacity.com/files/establishments/image/c5d2702e-107c-4d80-9363-9ad30843806d/bpi.jpg" alt="BPI logo">
                    <p>BPI</p>
                </div>
                <div class="payment-method" onclick="selectPayment(this, 'GCASH')">
                    <img src="https://play-lh.googleusercontent.com/QNP0Aj2hyumAmYiWVAsJtY2LLTQnzHxdW7-DpwFUFNkPJjgRxi-BXg7A4yI6tgYKMeU" alt="GCash logo">
                    <p>GCASH</p>
                </div>
                <div class="payment-method" onclick="selectPayment(this, 'BDO')">
                    <img src="https://yt3.googleusercontent.com/1w4gdfSFgHnInGHXE2tf9i6o_4aq9YIOl0S1-82GVT4o-nC8s1nqGVt0mxyuXaVrQ3V95dFm=s900-c-k-c0x00ffffff-no-rj" alt="BDO logo">
                    <p>BDO</p>
                </div>
            </div>
            <div id="payment-info" class="payment-info"></div>
        </div>
        <br>
        <div class="form-group">
            <div style="width: 100%;">
                <button onclick="validateAndConfirm()">Confirm Appointment</button>
            </div>
        </div>
    </section>

    <div class="receipt" id="receipt">
        <h3>Your Appointment Confirmation</h3>
        <p id="confirmation-message"></p>
    </div>
</div>

<footer>
    <p>&copy; 2024 Dental Care Clinic | All Rights Reserved</p>
</footer>

<script src="https://cdn.jsdelivr.net/npm/flatpickr"></script>
<script>
    flatpickr("#appointment-date", {
        minDate: "today",
        dateFormat: "Y-m-d",
    });

    let selectedDentist = null;
    let selectedPayment = null;

    function selectDentist(dentistElement) {
        const allDentists = document.querySelectorAll(".dentist-profile");
        allDentists.forEach(d => d.classList.remove("selected"));
        dentistElement.classList.add("selected");
        selectedDentist = dentistElement.querySelector("h4").textContent;
    }

    function selectPayment(paymentElement, method) {
        const allPayments = document.querySelectorAll(".payment-method");
        allPayments.forEach(p => p.classList.remove("selected"));
        paymentElement.classList.add("selected");
        selectedPayment = method;

        document.getElementById('payment-info').innerText = `Payment Method: ${method}`;
        let paymentInfo = '';
        if (method == 'BPI') {
            paymentInfo = 'Account Number: 1234-5678-9012. Please transfer the amount to this account.';
        } else if (method === 'GCASH') {
            paymentInfo = 'Please send payment to GCash number: 09123456789.';
        } else if (method === 'BDO') {
            paymentInfo = 'Account Number: 2345-6789-1234. Please transfer the amount to this account.';
    }
     document.getElementById('payment-info').innerText = paymentInfo;
    }

    function validateEmail(email) {
        const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
        return emailRegex.test(email);
    }

    function validateAndConfirm() {
        const name = document.getElementById("name").value.trim();
        const contact = document.getElementById("contact").value.trim();
        const email = document.getElementById("email").value.trim();
        const date = document.getElementById("appointment-date").value.trim();
        const service = document.getElementById("services").value;

        if (!name || !contact || !email || !date || !service || !validateEmail(email)) {
            document.getElementById("form-error").style.display = "block";
            document.getElementById("email-error").style.display = validateEmail(email) ? "none" : "block";
            return;
        }

        document.getElementById("form-error").style.display = "none";
        document.getElementById("email-error").style.display = "none";

        document.getElementById("confirmation-message").innerHTML = `
            <strong>Patient:</strong> ${name} <br>
            <strong>Contact:</strong> ${contact} <br>
            <strong>Email:</strong> ${email} <br>
            <strong>Service:</strong> ${service} <br>
            <strong>Appointment Date:</strong> ${date} <br>
            <strong>Selected Dentist:</strong> ${selectedDentist} <br>
            <strong>Payment Method:</strong> ${selectedPayment}
        `;
        document.getElementById("receipt").style.display = "block";
    }
</script>
</body>
</html>
