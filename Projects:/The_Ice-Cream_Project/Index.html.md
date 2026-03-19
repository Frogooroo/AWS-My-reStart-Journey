<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>The Ice-Cream Project</title>
  <style>
    :root {
      --lavender: #d4abee;
      --soft-pink: #fea6be;
      --rose-pink: #e27ca5;
      --mint: #a0d2c0;
      --teal: #79aaa7;
      --sky: #86d8ff;
      --lemon: #ffe66d;
      --cream: #fffafc;
      --white: #ffffff;
      --text: #3c3550;
      --shadow: 0 12px 30px rgba(121, 170, 167, 0.16);
      --radius: 24px;
    }

    * {
      box-sizing: border-box;
      scroll-behavior: smooth;
    }

    body {
      margin: 0;
      font-family: Arial, Helvetica, sans-serif;
      color: var(--text);
      background:
        radial-gradient(circle at top left, rgba(212,171,238,0.30), transparent 30%),
        radial-gradient(circle at top right, rgba(254,166,190,0.25), transparent 28%),
        linear-gradient(180deg, #fffafd 0%, #f8ffff 55%, #fff8fb 100%);
    }

    img {
      max-width: 100%;
      display: block;
    }

    a {
      text-decoration: none;
      color: inherit;
    }

    nav {
      position: sticky;
      top: 0;
      z-index: 50;
      display: flex;
      justify-content: center;
      gap: 24px;
      flex-wrap: wrap;
      padding: 16px 20px;
      background: rgba(255,255,255,0.88);
      backdrop-filter: blur(10px);
      border-bottom: 1px solid rgba(226,124,165,0.15);
    }

    nav a {
      font-weight: 700;
      color: var(--rose-pink);
    }

    nav a:hover {
      color: var(--teal);
    }

    .hero {
      max-width: 1200px;
      margin: 0 auto;
      padding: 56px 20px 32px;
      display: grid;
      grid-template-columns: 1.05fr 0.95fr;
      gap: 28px;
      align-items: center;
    }

    .hero-text {
      background: rgba(255,255,255,0.82);
      padding: 36px;
      border-radius: var(--radius);
      box-shadow: var(--shadow);
    }

    .badge {
      display: inline-block;
      background: linear-gradient(135deg, var(--lavender), var(--soft-pink));
      color: white;
      font-weight: 700;
      border-radius: 999px;
      padding: 10px 16px;
      margin-bottom: 18px;
      font-size: 0.92rem;
    }

    h1 {
      font-size: 3.3rem;
      line-height: 1.05;
      margin: 0 0 16px;
      color: #3f3350;
    }

    .hero p {
      font-size: 1.08rem;
      line-height: 1.7;
      margin-bottom: 24px;
    }

    .hero-buttons {
      display: flex;
      gap: 14px;
      flex-wrap: wrap;
    }

    .btn {
      border: none;
      padding: 14px 20px;
      border-radius: 14px;
      font-weight: 700;
      cursor: pointer;
      font-size: 1rem;
      transition: transform 0.18s ease, box-shadow 0.18s ease;
    }

    .btn:hover {
      transform: translateY(-2px);
      box-shadow: 0 8px 20px rgba(0,0,0,0.08);
    }

    .btn-primary {
      background: linear-gradient(135deg, var(--rose-pink), var(--soft-pink));
      color: white;
    }

    .btn-secondary {
      background: linear-gradient(135deg, var(--mint), var(--sky));
      color: #20414d;
    }

    .hero-image {
      border-radius: 32px;
      overflow: hidden;
      box-shadow: 0 18px 40px rgba(226,124,165,0.18);
      min-height: 540px;
    }

    .hero-image img {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }

    .section {
      max-width: 1200px;
      margin: 0 auto;
      padding: 28px 20px 22px;
    }

    .section-title {
      text-align: center;
      margin-bottom: 24px;
    }

    .section-title h2 {
      margin: 0 0 10px;
      font-size: 2.2rem;
      color: var(--rose-pink);
    }

    .section-title p {
      margin: 0 auto;
      max-width: 760px;
      line-height: 1.7;
    }

    .card {
      background: rgba(255,255,255,0.88);
      border-radius: var(--radius);
      box-shadow: var(--shadow);
      padding: 24px;
    }

    .about-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 24px;
      align-items: center;
    }

    .about-grid img {
      border-radius: 24px;
      height: 420px;
      width: 100%;
      object-fit: cover;
    }

    .menu-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
      gap: 24px;
      margin-top: 20px;
    }

    .menu-card {
      background: rgba(255,255,255,0.92);
      border-radius: 24px;
      overflow: hidden;
      box-shadow: var(--shadow);
      display: flex;
      flex-direction: column;
    }

    .menu-card img {
      width: 100%;
      height: 260px;
      object-fit: cover;
    }

    .menu-card-content {
      padding: 20px;
    }

    .menu-card h3 {
      margin: 0 0 8px;
      color: var(--teal);
      font-size: 1.2rem;
    }

    .menu-card p {
      margin: 0 0 10px;
      line-height: 1.6;
    }

    .price {
      font-weight: 800;
      color: var(--rose-pink);
      font-size: 1.05rem;
    }

    .two-column {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 24px;
      margin-top: 20px;
    }

    .shop-highlight {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 18px;
    }

    .shop-highlight img {
      border-radius: 20px;
      height: 220px;
      width: 100%;
      object-fit: cover;
    }

    form {
      display: grid;
      gap: 14px;
    }

    label {
      font-size: 0.95rem;
      font-weight: 700;
      margin-bottom: 4px;
      display: block;
    }

    input, select, textarea {
      width: 100%;
      padding: 13px 14px;
      border: 2px solid #f0d8e5;
      border-radius: 14px;
      font-size: 1rem;
      background: white;
      color: var(--text);
    }

    input:focus, select:focus, textarea:focus {
      outline: none;
      border-color: var(--soft-pink);
      box-shadow: 0 0 0 4px rgba(254,166,190,0.15);
    }

    .status-box {
      background: linear-gradient(135deg, rgba(160,210,192,0.22), rgba(134,216,255,0.16));
      padding: 14px 16px;
      border-radius: 16px;
      margin-bottom: 16px;
      font-weight: 700;
      color: #24505a;
    }

    .hidden {
      display: none;
    }

    .contact-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 24px;
      align-items: center;
    }

    .contact-image img {
      border-radius: 24px;
      height: 360px;
      object-fit: cover;
      width: 100%;
    }

    footer {
      margin-top: 36px;
      background: linear-gradient(135deg, var(--teal), var(--mint), var(--sky));
      color: white;
      text-align: center;
      padding: 28px 20px;
    }

    .small-note {
      font-size: 0.92rem;
      color: #6d647b;
      line-height: 1.6;
    }

    @media (max-width: 980px) {
      .hero,
      .about-grid,
      .two-column,
      .contact-grid,
      .shop-highlight {
        grid-template-columns: 1fr;
      }

      .hero-image {
        min-height: 360px;
      }

      h1 {
        font-size: 2.6rem;
      }
    }

    @media (max-width: 640px) {
      h1 {
        font-size: 2.1rem;
      }

      .section-title h2 {
        font-size: 1.8rem;
      }

      nav {
        gap: 14px;
      }
    }
  </style>
</head>
<body>

  <nav>
    <a href="#about">About</a>
    <a href="#shop">Shop</a>
    <a href="#menu">Menu</a>
    <a href="#login">Customer Login</a>
    <a href="#order">Order</a>
    <a href="#booking">Event Booking</a>
    <a href="#contact">Contact</a>
  </nav>

  <header class="hero">
    <div class="hero-text">
      <span class="badge">Coffee • Ice Cream • Events • Happy Moments</span>
      <h1>The Ice-Cream Project</h1>
      <p>
        A fresh, playful coffee and ice-cream destination where specialty drinks,
        artisan scoops, and colorful vibes come together. Whether you want a quick treat,
        a takeaway order, or a private celebration, The Ice-Cream Project is designed to
        feel bright, welcoming, and unforgettable.
      </p>
      <div class="hero-buttons">
        <a class="btn btn-primary" href="#menu">Explore the Menu</a>
        <a class="btn btn-secondary" href="#booking">Book an Event</a>
      </div>
    </div>

    <div class="hero-image">
      <img src="tasty-coffee-near-beautiful-flower-vase-wooden-table.jpg" alt="The Ice-Cream Project shop atmosphere">
    </div>
  </header>

  <section class="section" id="about">
    <div class="section-title">
      <h2>About Us</h2>
      <p>
        The Ice-Cream Project is all about joyful flavours, cheerful design, and memorable little breaks in the day.
        We serve handcrafted ice cream, specialty coffee, and indulgent desserts in a bright and friendly atmosphere.
      </p>
    </div>

    <div class="about-grid">
      <div class="card">
        <h3 style="color:#79aaa7; margin-top:0;">A sweet concept with personality</h3>
        <p>
          Our space is made for people who love fresh coffee, beautiful desserts, and colorful experiences.
          From creamy lattes to playful scoops and event-friendly treats, every detail is designed to feel uplifting.
        </p>
        <p>
          Ideal for families, students, weekend visitors, casual meet-ups, and small private events,
          our shop blends quality, comfort, and fun into one visually vibrant destination.
        </p>
      </div>

      <img src="coffee-cup-table-cafe.jpg" alt="Coffee served inside the shop">
    </div>
  </section>

  <section class="section" id="shop">
    <div class="section-title">
      <h2>The Shop Experience</h2>
      <p>
        A glimpse of the atmosphere, textures, colours, and signature mood of The Ice-Cream Project.
      </p>
    </div>

    <div class="shop-highlight">
      <img src="tasty-coffee-near-beautiful-flower-vase-wooden-table.jpg" alt="Shop ambiance with coffee and flowers">
      <img src="coffee-cup-table-cafe.jpg" alt="Bright cafe table with coffee">
    </div>
  </section>

  <section class="section" id="menu">
    <div class="section-title">
      <h2>Menu Highlights</h2>
      <p>
        Here are some of our signature drinks and frozen favourites, each illustrated with your attached product imagery.
      </p>
    </div>

    <div class="menu-grid">
      <article class="menu-card">
        <img src="coffee-latte-side-view.jpg" alt="Lemon sunshine latte">
        <div class="menu-card-content">
          <h3>Lemon Sunshine Latte</h3>
          <p>A bright, creamy latte with a soft, velvety finish and a cheerful morning feel.</p>
          <div class="price">$5.50</div>
        </div>
      </article>

      <article class="menu-card">
        <img src="latte-machiatto-coffee-with-steamed-milk-chocolate-coffee-beans-table.jpg" alt="Pink cloud macchiato">
        <div class="menu-card-content">
          <h3>Pink Cloud Macchiato</h3>
          <p>A smooth layered macchiato with airy foam and a playful signature presentation.</p>
          <div class="price">$5.95</div>
        </div>
      </article>

      <article class="menu-card">
        <img src="ice-cream-cone-with-caramel-sauce-food-photography.jpg" alt="Vanilla honey cone">
        <div class="menu-card-content">
          <h3>Vanilla Honey Cone</h3>
          <p>Rich vanilla ice cream in a chocolate-dipped cone finished with flowing honey caramel.</p>
          <div class="price">$6.20</div>
        </div>
      </article>

      <article class="menu-card">
        <img src="top-view-delicious-creamy-ice-cream.jpg" alt="Signature four-cone selection">
        <div class="menu-card-content">
          <h3>Signature Scoop Selection</h3>
          <p>A crowd-pleasing range of creamy flavours for customers who want variety and indulgence.</p>
          <div class="price">$8.50</div>
        </div>
      </article>

      <article class="menu-card">
        <img src="still-life-cookies-ice-cream.jpg" alt="Cookie pop cone">
        <div class="menu-card-content">
          <h3>Cookie Pop Cone</h3>
          <p>A fun, colorful cone packed with texture, crunch, and bold scoop flavours.</p>
          <div class="price">$6.80</div>
        </div>
      </article>

      <article class="menu-card">
        <img src="side-view-hand-holding-ice-cream-cup.jpg" alt="Strawberry sky cup">
        <div class="menu-card-content">
          <h3>Strawberry Sky Cup</h3>
          <p>A refreshing pink scoop served in a bright cup for easy takeaway enjoyment.</p>
          <div class="price">$5.80</div>
        </div>
      </article>

      <article class="menu-card">
        <img src="advertisement-dessert-with-ice-cream.jpg" alt="Berry burst soft serve">
        <div class="menu-card-content">
          <h3>Berry Burst Soft Serve</h3>
          <p>A striking soft serve finished with berry pieces and a dramatic, premium dessert look.</p>
          <div class="price">$6.40</div>
        </div>
      </article>

      <article class="menu-card">
        <img src="tasty-coffee-near-beautiful-flower-vase-wooden-table.jpg" alt="House coffee">
        <div class="menu-card-content">
          <h3>Project House Coffee</h3>
          <p>Our warm, comforting signature coffee served in a cozy setting with floral charm.</p>
          <div class="price">$4.90</div>
        </div>
      </article>
    </div>
  </section>

  <section class="section" id="login">
    <div class="section-title">
      <h2>Customer Login</h2>
      <p>
        Customers can log in before placing an order. This version is a front-end demo suitable for a static S3 site.
      </p>
    </div>

    <div class="two-column">
      <div class="card">
        <div id="loginStatus" class="status-box">You are currently not logged in.</div>

        <form id="loginForm">
          <div>
            <label for="loginEmail">Email</label>
            <input type="email" id="loginEmail" name="loginEmail" placeholder="customer@email.com" required>
          </div>

          <div>
            <label for="loginPassword">Password</label>
            <input type="password" id="loginPassword" name="loginPassword" placeholder="Enter password" required>
          </div>

          <button class="btn btn-primary" type="submit">Log In</button>
          <button class="btn btn-secondary" type="button" id="logoutBtn">Log Out</button>
        </form>

        <p class="small-note" style="margin-top:14px;">
          Demo only: this login is stored in the browser and is not a secure authentication system.
        </p>
      </div>

      <div class="card">
        <img src="coffee-latte-side-view.jpg" alt="Coffee for login section" style="border-radius:20px; height:320px; width:100%; object-fit:cover;">
      </div>
    </div>
  </section>

  <section class="section" id="order">
    <div class="section-title">
      <h2>Place an Order</h2>
      <p>
        Customers must log in before submitting an order in this static-site version.
      </p>
    </div>

    <div class="two-column">
      <div class="card">
        <div id="orderAccessMessage" class="status-box">
          Please log in first to access ordering.
        </div>

        <form id="orderForm" class="hidden">
          <div>
            <label for="customerName">Full Name</label>
            <input type="text" id="customerName" name="customerName" placeholder="Your full name" required>
          </div>

          <div>
            <label for="customerEmail">Email</label>
            <input type="email" id="customerEmail" name="customerEmail" placeholder="Your email" required>
          </div>

          <div>
            <label for="customerPhone">Phone</label>
            <input type="tel" id="customerPhone" name="customerPhone" placeholder="Your phone number" required>
          </div>

          <div>
            <label for="product">Choose a product</label>
            <select id="product" name="product" required>
              <option value="">Select an item</option>
              <option>Lemon Sunshine Latte</option>
              <option>Pink Cloud Macchiato</option>
              <option>Vanilla Honey Cone</option>
              <option>Signature Scoop Selection</option>
              <option>Cookie Pop Cone</option>
              <option>Strawberry Sky Cup</option>
              <option>Berry Burst Soft Serve</option>
              <option>Project House Coffee</option>
            </select>
          </div>

          <div>
            <label for="quantity">Quantity</label>
            <input type="number" id="quantity" name="quantity" min="1" placeholder="Quantity" required>
          </div>

          <div>
            <label for="pickupMethod">Pickup Method</label>
            <select id="pickupMethod" name="pickupMethod" required>
              <option value="">Select pickup method</option>
              <option>In-store Pickup</option>
              <option>Takeaway</option>
            </select>
          </div>

          <div>
            <label for="orderNotes">Special Instructions</label>
            <textarea id="orderNotes" name="orderNotes" rows="5" placeholder="Allergies, toppings, or special requests"></textarea>
          </div>

          <button class="btn btn-primary" type="submit">Submit Order</button>
        </form>

        <p class="small-note" style="margin-top:14px;">
          In this static version, the order redirects to <code>order-confirmation.html</code>.
        </p>
      </div>

      <div class="card">
        <img src="side-view-hand-holding-ice-cream-cup.jpg" alt="Takeaway ice cream cup" style="border-radius:20px; height:320px; width:100%; object-fit:cover;">
      </div>
    </div>
  </section>

  <section class="section" id="booking">
    <div class="section-title">
      <h2>Book an Event</h2>
      <p>
        Reserve the shop for birthdays, celebrations, creative workshops, and private gatherings.
      </p>
    </div>

    <div class="two-column">
      <div class="card">
        <form id="bookingForm">
          <div>
            <label for="name">Your Full Name</label>
            <input type="text" id="name" name="name" placeholder="Your full name" required>
          </div>

          <div>
            <label for="email">Your Email</label>
            <input type="email" id="email" name="email" placeholder="Your email" required>
          </div>

          <div>
            <label for="phone">Your Phone Number</label>
            <input type="tel" id="phone" name="phone" placeholder="Your phone number" required>
          </div>

          <div>
            <label for="date">Preferred Date</label>
            <input type="date" id="date" name="date" required>
          </div>

          <div>
            <label for="guests">Number of Guests</label>
            <input type="number" id="guests" name="guests" min="1" placeholder="Number of guests" required>
          </div>

          <div>
            <label for="eventType">Event Type</label>
            <select id="eventType" name="eventType" required>
              <option value="">Select event type</option>
              <option>Birthday Party</option>
              <option>Private Celebration</option>
              <option>Corporate Event</option>
              <option>Workshop</option>
              <option>Other</option>
            </select>
          </div>

          <div>
            <label for="notes">Event Details</label>
            <textarea id="notes" name="notes" rows="5" placeholder="Tell us about your event and any special requests"></textarea>
          </div>

          <button class="btn btn-primary" type="submit">Submit Booking Request</button>
        </form>
      </div>

      <div class="card">
        <img src="advertisement-dessert-with-ice-cream.jpg" alt="Event dessert inspiration" style="border-radius:20px; height:320px; width:100%; object-fit:cover;">
      </div>
    </div>
  </section>

  <section class="section" id="contact">
    <div class="section-title">
      <h2>Contact Us</h2>
      <p>
        Come by for coffee, stay for ice cream, and get in touch for events or large orders.
      </p>
    </div>

    <div class="contact-grid">
      <div class="card">
        <h3 style="margin-top:0; color:#79aaa7;">Visit The Ice-Cream Project</h3>
        <p><strong>Address:</strong> 123 Rainbow Avenue, Miami, FL</p>
        <p><strong>Phone:</strong> (305) 555-2048</p>
        <p><strong>Email:</strong> hello@theicecreamproject.com</p>
        <p><strong>Opening Hours:</strong> Monday to Sunday, 9:00 AM – 10:00 PM</p>
      </div>

      <div class="contact-image">
        <img src="ice-cream-cone-with-caramel-sauce-food-photography.jpg" alt="Ice cream contact visual">
      </div>
    </div>
  </section>

  <footer>
    <p>&copy; 2026 The Ice-Cream Project. All rights reserved.</p>
  </footer>

  <script>
    const loginForm = document.getElementById("loginForm");
    const logoutBtn = document.getElementById("logoutBtn");
    const loginStatus = document.getElementById("loginStatus");
    const orderForm = document.getElementById("orderForm");
    const orderAccessMessage = document.getElementById("orderAccessMessage");

    function updateLoginState() {
      const loggedInUser = localStorage.getItem("ticpUser");

      if (loggedInUser) {
        loginStatus.textContent = "Logged in as: " + loggedInUser;
        orderAccessMessage.textContent = "Welcome back. You can now place your order.";
        orderForm.classList.remove("hidden");

        const emailField = document.getElementById("customerEmail");
        if (emailField && !emailField.value) {
          emailField.value = loggedInUser;
        }
      } else {
        loginStatus.textContent = "You are currently not logged in.";
        orderAccessMessage.textContent = "Please log in first to access ordering.";
        orderForm.classList.add("hidden");
      }
    }

    loginForm.addEventListener("submit", function(event) {
      event.preventDefault();

      const email = document.getElementById("loginEmail").value.trim();
      const password = document.getElementById("loginPassword").value.trim();

      if (!email || !password) {
        alert("Please enter both email and password.");
        return;
      }

      localStorage.setItem("ticpUser", email);
      alert("Login successful.");
      updateLoginState();
      loginForm.reset();
      window.location.hash = "order";
    });

    logoutBtn.addEventListener("click", function() {
      localStorage.removeItem("ticpUser");
      alert("You have been logged out.");
      updateLoginState();
    });

    document.getElementById("bookingForm").addEventListener("submit", function(event) {
      event.preventDefault();
      const formData = new FormData(this);
      const params = new URLSearchParams(formData).toString();
      window.location.href = "booking-confirmation.html?" + params;
    });

    document.getElementById("orderForm").addEventListener("submit", function(event) {
      event.preventDefault();

      const loggedInUser = localStorage.getItem("ticpUser");
      if (!loggedInUser) {
        alert("Please log in before placing an order.");
        window.location.hash = "login";
        return;
      }

      const formData = new FormData(this);
      const params = new URLSearchParams(formData).toString();
      window.location.href = "order-confirmation.html?" + params;
    });

    updateLoginState();
  </script>

</body>
</html>
