# lift-n-haul-website

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Lift N Haul - Moving Company</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
            color: #333;
        }
        header {
            background-color: #FFD700;
            padding: 20px;
            text-align: center;
        }
        header img {
            max-width: 150px;
        }
        nav {
            display: flex;
            justify-content: center;
            background-color: #333;
            padding: 10px;
        }
        nav a {
            color: #fff;
            text-decoration: none;
            margin: 0 15px;
            padding: 10px 20px;
        }
        nav a:hover {
            background-color: #FFD700;
            color: #333;
        }
        section {
            padding: 20px;
            margin: 20px;
            background-color: #fff;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        .quote-calculator input, .quote-calculator select {
            width: 100%;
            padding: 10px;
            margin: 10px 0;
            border-radius: 5px;
            border: 1px solid #ccc;
        }
        .quote-calculator button {
            padding: 10px 20px;
            background-color: #333;
            color: #fff;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
        .quote-calculator button:hover {
            background-color: #FFD700;
            color: #333;
        }
        footer {
            text-align: center;
            padding: 20px;
            background-color: #333;
            color: #fff;
        }
    </style>
</head>
<body>

    <header>
        <img src="your-logo-file-path-here" alt="Lift N Haul Logo">
        <h1>Lift N Haul - Moving Company</h1>
    </header>

    <nav>
        <a href="#about">About Us</a>
        <a href="#services">Services</a>
        <a href="#pricing">Pricing</a>
        <a href="#contact">Contact</a>
    </nav>

    <section id="about">
        <h2>About Us</h2>
        <p>Welcome to <strong>Lift N Haul</strong>! We are a proud independent, locally owned moving company based in Tacoma, Washington. For the past four years, we've been dedicated to providing top-notch moving services that prioritize <strong>safety and hospitality</strong> for every client we serve.</p>
        <p>As a <strong>veteran-owned</strong> business, we are committed to giving back to those who have served our country by actively hiring veterans. We believe in the values of discipline, commitment, and excellence, which our team embodies every day.</p>
        <p>We are also in partnership with <strong>E&E Private Protection</strong>, ensuring that our services are not only efficient but also secure, giving you peace of mind throughout your moving process.</p>
        <p>At Lift N Haul, our mission is to make your move as smooth and stress-free as possible, whether you're moving across town or across the country. Let us handle the heavy lifting so you can focus on the exciting journey ahead.</p>
    </section>

    <section id="services">
        <h2>Our Services</h2>
        <p>We offer a range of moving services tailored to meet your needs, including local moves, long-distance moves, and single or dual item moves.</p>
    </section>

    <section id="pricing">
        <h2>Pricing</h2>
        <ul>
            <li><strong>Local Moves:</strong></li>
            <ul>
                <li>$90 per hour for a two-person team and a truck.</li>
                <li>$125 per hour for a three-person team and a truck.</li>
                <li>$160 per hour for a four-person team and a truck.</li>
            </ul>
            <li><strong>Long-Distance Moves:</strong></li>
            <ul>
                <li>$1,400 base fee plus $0.70 per mile for moves under 1,000 miles.</li>
                <li>$3,300 base fee plus $0.60 per mile for cross-country moves (over 2,000 miles).</li>
            </ul>
            <li><strong>Volume and Weight-Based Pricing:</strong> $0.50 per pound or $2.75 per cubic foot (whichever is higher) for long-distance moves.</li>
            <li><strong>Single or Dual Item Move:</strong> Base Service Fee: $75 flat fee for the initial setup and local transportation. Labor Charges: $50 per mover per hour.</li>
        </ul>
    </section>

    <section id="quote-calculator" class="quote-calculator">
        <h2>Get a Quote</h2>
        <p>Select your options below to calculate an estimate:</p>
        <form>
            <label for="move-type">Type of Move:</label>
            <select id="move-type">
                <option value="local">Local Move</option>
                <option value="long-distance">Long-Distance Move</option>
                <option value="single-dual">Single/Dual Item Move</option>
            </select>

            <label for="team-size">Team Size:</label>
            <select id="team-size">
                <option value="2-person">2-Person Team</option>
                <option value="3-person">3-Person Team</option>
                <option value="4-person">4-Person Team</option>
            </select>

            <label for="distance">Distance (in miles or hours):</label>
            <input type="number" id="distance" placeholder="Enter distance in miles for long-distance or hours for local">

            <label for="volume-weight">Volume/Weight (for long-distance moves):</label>
            <input type="number" id="volume-weight" placeholder="Enter total weight in pounds or volume in cubic feet">

            <button type="button" onclick="calculateQuote()">Calculate Quote</button>
        </form>
        <p id="quote-result"></p>
    </section>

    <section id="contact">
        <h2>Contact Us</h2>
        <p>If you're ready to move or have any questions, we'd love to hear from you!</p>
        <p><strong>Phone:</strong> 253-459-9595</p>
        <p><strong>Email:</strong> <a href="mailto:liftnhaulco@gmail.com">liftnhaulco@gmail.com</a></p>
    </section>

    <footer>
        <p>Lift N Haul &copy; 2024 | All Rights Reserved</p>
        <p>Social Media Links and Live Chat Coming Soon</p>
    </footer>

    <script>
        function calculateQuote() {
            let moveType = document.getElementById('move-type').value;
            let teamSize = document.getElementById('team-size').value;
            let distance = parseFloat(document.getElementById('distance').value) || 0;
            let volumeWeight = parseFloat(document.getElementById('volume-weight').value) || 0;
            let quote = 0;

            // Local Move
            if (moveType === 'local') {
                if (teamSize === '2-person') quote = 90 * distance;
                if (teamSize === '3-person') quote = 125 * distance;
                if (teamSize === '4-person') quote = 160 * distance;
            }

            // Long-Distance Move
            if (moveType === 'long-distance') {
                if (distance < 1000) quote = 1400 + (0.70 * distance);
                if (distance >= 1000) quote = 3300 + (0.60 * distance);
                if (volumeWeight > 0) {
                    let volumeWeightCharge = Math.max(0.50 * volumeWeight, 2.75 * volumeWeight);
                    quote += volumeWeightCharge;
                }
            }

            // Single/Dual Item Move
            if (moveType === 'single-dual') {
                quote = 75 + (50 * teamSize);
            }

            document.getElementById('quote-result').innerText = `Estimated Quote: $${quote.toFixed(2)}`;
        }
    </script>

</body>
</html>
