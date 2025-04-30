# moDesigningfortheUserExperience-
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="BidBuy - Buy, Sell, and Discover with Ease">
    <title>BidBuy Marketplace</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
    <style>
        body {
            font-family: Arial, sans-serif;
        }

        header, footer {
            background-color: #343a40;
            color: white;
            padding: 1rem;
        }

        .section {
            padding: 3rem 1rem;
        }

        .category-card {
            text-align: center;
            padding: 1rem;
            border: 1px solid #ddd;
            border-radius: 8px;
        }
    </style>
</head>

<body>
    <!-- Header -->
    <header class="text-center">
        <h1>BidBuy Marketplace</h1>
        <nav>
            <a href="#home" class="text-white m-2">Home</a>
            <a href="#categories" class="text-white m-2">Categories</a>
            <a href="#contact" class="text-white m-2">Contact</a>
        </nav>
    </header>

    <!-- Home Section -->
    <section id="home" class="section container">
        <div class="row">
            <div class="col-md-6">
                <h2>Welcome to BidBuy</h2>
                <p>Discover the easiest way to buy and sell products online. Safe, secure, and simple.</p>
            </div>
            <div class="col-md-6">
                <img src="https://via.placeholder.com/500x300" alt="Shopping banner" class="img-fluid">
            </div>
        </div>
    </section>

    <!-- Categories Section -->
    <section id="categories" class="section bg-light">
        <div class="container">
            <h2 class="text-center mb-4">Popular Categories</h2>
            <div class="row">
                <div class="col-md-4">
                    <div class="category-card">
                        <h4>Gadgets</h4>
                        <p>Phones, accessories, and more.</p>
                    </div>
                </div>
                <div class="col-md-4">
                    <div class="category-card">
                        <h4>Clothing</h4>
                        <p>Trendy and affordable fashion.</p>
                    </div>
                </div>
                <div class="col-md-4">
                    <div class="category-card">
                        <h4>Beauty</h4>
                        <p>Cosmetics, skincare, and wellness.</p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section with Weather API -->
    <section id="contact" class="section container">
        <h2 class="text-center mb-4">Contact Us</h2>
        <form>
            <div class="mb-3">
                <label for="email" class="form-label">Email address</label>
                <input type="email" class="form-control" id="email" placeholder="name@example.com">
            </div>
            <div class="mb-3">
                <label for="message" class="form-label">Message</label>
                <textarea class="form-control" id="message" rows="3"></textarea>
            </div>
            <button type="submit" class="btn btn-primary">Send</button>
        </form>
        <div id="weather" class="mt-4">
            <h5>Current Weather</h5>
            <p id="weather-info">Loading weather data...</p>
        </div>
    </section>

    <!-- Footer -->
    <footer class="text-center">
        <p>&copy; 2025 BidBuy. All rights reserved.</p>
    </footer>

    <!-- Scripts -->
    <script>
        // Example weather API integration using OpenWeatherMap
        const apiKey = 'YOUR_API_KEY'; // Replace with your actual OpenWeatherMap API key
        const city = 'London';

        fetch(`https://api.openweathermap.org/data/2.5/weather?q=${city}&appid=${apiKey}&units=metric`)
            .then(response => response.json())
            .then(data => {
                const weatherInfo = `Temperature in ${city}: ${data.main.temp}°C, ${data.weather[0].description}`;
                document.getElementById('weather-info').innerText = weatherInfo;
            })
            .catch(error => {
                document.getElementById('weather-info').innerText = 'Unable to fetch weather data.';
                console.error('Weather API error:', error);
            });
    </script>
</body>

</html>
