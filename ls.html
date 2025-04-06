<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Daily Torah Feed</title>
  <meta name="viewport" content="width=device-width, initial-scale=1">

  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f8f9fa;
      color: #222;
      margin: 0;
      padding: 2rem;
    }

    .container {
      max-width: 900px;
      margin: auto;
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 2rem;
    }

    .section {
      background: white;
      padding: 1.5rem;
      border-radius: 12px;
      box-shadow: 0 0 10px rgba(0,0,0,0.05);
    }

    h2 {
      margin-top: 0;
      color: #1026cc;
      font-size: 1.3rem;
    }

    ul {
      list-style: none;
      padding-left: 0;
    }

    .date {
      font-size: 1.2rem;
      margin-bottom: 1rem;
    }

    .clock {
      font-size: 2rem;
      margin-top: 0.5rem;
    }

    .footer {
      text-align: center;
      margin-top: 3rem;
      font-size: 0.9rem;
      color: #888;
    }

    @media (max-width: 768px) {
      .container {
        grid-template-columns: 1fr;
      }
    }
  </style>
</head>

<body>
  <div class="container">

    <!-- Date & Time Section -->
    <div class="section">
      <h2>Current Date & Time</h2>
      <div class="date" id="gregorian-date"></div>
      <div class="date" id="hebrew-date"></div>
      <div class="clock" id="clock"></div>
    </div>

    <!-- Rambam Study -->
    <div class="section">
      <h2>Rambam Daily Study</h2>
      <ul id="rambam-feed"></ul>
    </div>

    <!-- Omer Counter -->
    <div class="section">
      <h2>Omer Counter</h2>
      <div id="omer-count">Loading...</div>
    </div>

    <!-- Candle Lighting -->
    <div class="section" id="candle-section" style="display:none;">
      <h2>Shabbat Candle Lighting</h2>
      <div id="candle-lighting-time">Loading...</div>
    </div>
  </div>

  <div class="footer">Site powered by GitHub Pages • Built with ❤️</div>

  <!-- Scripts -->
  <script>
    // 12-hour Clock
    function updateClock() {
      const now = new Date();
      let hours = now.getHours();
      const minutes = now.getMinutes().toString().padStart(2, '0');
      const seconds = now.getSeconds().toString().padStart(2, '0');
      const ampm = hours >= 12 ? 'PM' : 'AM';
      hours = hours % 12 || 12;
      document.getElementById('clock').textContent = `${hours}:${minutes}:${seconds} ${ampm}`;
    }
    setInterval(updateClock, 1000);
    updateClock();

    // Gregorian + Hebrew Date
    const today = new Date();
    document.getElementById('gregorian-date').textContent = today.toDateString();

    const pad2 = (n) => n.toString().padStart(2, '0');
    const isoDate = `${today.getFullYear()}-${pad2(today.getMonth() + 1)}-${pad2(today.getDate())}`;
    fetch(`https://www.hebcal.com/converter?cfg=json&gy=${today.getFullYear()}&gm=${today.getMonth()+1}&gd=${today.getDate()}&g2h=1`)
      .then(res => res.json())
      .then(data => {
        document.getElementById('hebrew-date').textContent = `${data.hebrew}`;
      });

    // Rambam RSS Feed
    fetch('https://api.rss2json.com/v1/api.json?rss_url=https://www.chabad.org/tools/rss/rambam.xml')
      .then(response => response.json())
      .then(data => {
        const list = document.getElementById('rambam-feed');
        data.items.slice(0, 3).forEach(item => {
          const li = document.createElement('li');
          li.innerHTML = `<a href="${item.link}" target="_blank">${item.title}</a>`;
          list.appendChild(li);
        });
      });

    // Omer RSS Feed
    fetch('https://api.rss2json.com/v1/api.json?rss_url=https://www.chabad.org/tools/rss/omer_rss.xml')
      .then(response => response.json())
      .then(data => {
        const todayOmer = data.items.find(item => {
          const pubDate = new Date(item.pubDate);
          return pubDate.toDateString() === new Date().toDateString();
        });
        if (todayOmer) {
          document.getElementById('omer-count').textContent = todayOmer.title;
        } else {
          document.getElementById('omer-count').textContent = "Not counting today.";
        }
      });

    // Candle Lighting (only show on Fridays)
    if (today.getDay() === 5) {
      document.getElementById('candle-section').style.display = 'block';
      const locationId = '90035'; // Beverly Hills
      const url = `https://www.hebcal.com/shabbat?cfg=json&geo=zip&zip=${locationId}&m=50`;
      fetch(url)
        .then(response => response.json())
        .then(data => {
          const candleEvent = data.items.find(item => item.category === "candles");
          if (candleEvent) {
            document.getElementById('candle-lighting-time').textContent = candleEvent.title;
          } else {
            document.getElementById('candle-lighting-time').textContent = "No candle lighting time today.";
          }
        });
    }
  </script>
</body>
</html>
