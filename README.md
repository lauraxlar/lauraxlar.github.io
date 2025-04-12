
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>washiez.lol</title>
  <link rel="icon" href="https://washiez.lol/icon.ico" type="image/x-icon" />
  <link rel="apple-touch-icon" href="https://washiez.lol/icon.png" />
  <meta property="og:title" content="washiez.lol" />
  <meta property="og:description" content="The ultimate free script for Washiez on Roblox." />
  <meta property="og:image" content="https://washiez.lol/icon.png" />
  <meta property="og:url" content="https://washiez.lol" />
  <meta name="twitter:card" content="summary" />
  <meta name="theme-color" content="#3b82f6" />
  <link href="https://unpkg.com/aos@2.3.1/dist/aos.css" rel="stylesheet" />
  <style>
    * {
      box-sizing: border-box;
    }
    body {
      margin: 0;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      background: linear-gradient(to bottom right, #0a0a0a, #14142b);
      color: white;
      overflow-x: hidden;
    }
    h1 {
      font-size: 4rem;
      text-shadow: 0 0 10px #ffffff50;
      text-align: center;
      margin-top: 60px;
    }
    p {
      font-size: 1.2rem;
      color: #ccc;
      text-align: center;
      margin-bottom: 30px;
    }
    .btn-group {
      display: flex;
      justify-content: center;
      gap: 20px;
      margin-bottom: 50px;
      padding: 20px;
      backdrop-filter: blur(12px);
      background-color: rgba(17, 24, 39, 0.4);
      border-radius: 20px;
      width: fit-content;
      margin-left: auto;
      margin-right: auto;
      flex-wrap: wrap;
    }
    .btn {
      padding: 12px 24px;
      border: none;
      border-radius: 10px;
      font-size: 1rem;
      font-weight: bold;
      cursor: pointer;
      transition: all 0.3s ease;
      text-decoration: none;
    }
    .btn-primary {
      background-color: #3b82f6;
      color: white;
    }
    .btn-primary:hover {
      background-color: #2563eb;
    }
    .btn-secondary {
      background-color: #111827;
      color: #9ca3af;
      border: 1px solid #374151;
    }
    .btn-secondary:hover {
      background-color: #1f2937;
    }
    .grid-bg {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background-image: linear-gradient(to right, #ffffff10 1px, transparent 1px), 
                        linear-gradient(to bottom, #ffffff10 1px, transparent 1px);
      background-size: 50px 50px;
      z-index: -1;
    }
    .custom-toast {
      position: fixed;
      bottom: 30px;
      right: 30px;
      background-color: #1f2937;
      color: #d1d5db;
      padding: 16px 24px;
      border-radius: 12px;
      box-shadow: 0 4px 20px rgba(0, 0, 0, 0.5);
      opacity: 0;
      transform: translateY(20px);
      animation: fadeInUp 0.3s forwards, fadeOut 0.5s forwards 2.5s;
      font-size: 0.95rem;
      z-index: 9999;
    }
    @keyframes fadeInUp {
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }

    @keyframes fadeOut {
      to {
        opacity: 0;
        transform: translateY(20px);
      }
    }
    .section {
      max-width: 1000px;
      margin: 0 auto;
      padding: 60px 20px;
      text-align: center;
    }
    .section img {
      max-width: 100%;
      border-radius: 20px;
      box-shadow: 0 0 20px #00000050;
    }
    .features {
      display: flex;
      flex-direction: column;
      gap: 12px;
      margin-top: 30px;
      font-size: 1.1rem;
      color: #d1d5db;
      backdrop-filter: blur(10px);
      background-color: rgba(17, 24, 39, 0.5);
      padding: 30px;
      border-radius: 20px;
    }
    .footer {
      text-align: center;
      padding: 20px;
      font-size: 0.8rem;
      color: #666;
    }
    @media (max-width: 768px) {
      h1 {
        font-size: 2.5rem;
      }

      p {
        font-size: 1rem;
      }

      .btn-group {
        flex-direction: column;
        width: 90%;
      }

      .section {
        padding: 40px 16px;
      }

      .features {
        font-size: 1rem;
        padding: 20px;
      }
      .custom-toast {
        right: 16px;
        bottom: 20px;
        padding: 14px 20px;
        font-size: 0.9rem;
      }
      .section img {
        border-radius: 14px;
      }
    }
  </style>
</head>
<body>
  <div class="grid-bg"></div>
  <h1>washiez.lol</h1>
  <p>The ultimate free script for Washiez on Roblox</p>
  <div class="btn-group" data-aos="zoom-in">
    <button class="btn btn-primary" onclick="copyScript()">Copy Script</button>
    <a href="https://discord.gg/GP9jJ9t4kJ" class="btn btn-secondary" target="_blank">Join Discord</a>
  </div>
  <div class="section" data-aos="fade-up">
    <h2>Script Showcase</h2>
    <img src="https://washiez.lol/showcase.png" alt="Script Showcase" />
  </div>
  <div class="section" data-aos="fade-up">
    <h2>Features</h2>
    <div class="features">
      <div>✔️ Rayfield UI</div>
      <div>✔️ Auto Obby</div>
      <div>✔️ HR/MR Scanner</div>
      <div>✔️ Vehicle Modifications (noclip)</div>
      <div>✔️ Teleporters (including training center)</div>
    </div>
<div class="section" data-aos="fade-up">
  <h2>How to Use</h2>
  <div class="features">
    <div><strong>PC:</strong></div>
    <div>1. Download an executor. I recommend Swift 
      <a href="https://getswift.gg" target="_blank" class="btn btn-secondary" style="font-size: 0.85rem; display: inline-flex; align-items: center; gap: 6px;">Open 
        <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-box-arrow-up-right" viewBox="0 0 16 16">
          <path d="M11.5 1.5a.5.5 0 0 1 .5.5v4.793l2.146-2.147a.5.5 0 1 1 .707.707L12.207 7H16a.5.5 0 0 1 .5.5v8a.5.5 0 0 1-.5.5H1a.5.5 0 0 1-.5-.5V1a.5.5 0 0 1 .5-.5h10z"/>
        </svg>
      </a>
    </div>
    <div>2. Setup the executor. You may need to turn off your antivirus or whitelist the executor.</div>
    <div>3. Once it is all setup, open the executor and join a Roblox game.</div>
    <div>4. Inject your executor.</div>
    <div>5. Paste the script in from above and hit Start.</div>
    <div>6. You're ready to go!</div>
    <br><br>
    <div><strong>Mobile:</strong></div>
    <div>Coming Soon...</div>
  </div>
</div>
<div class="section" data-aos="fade-up">
  <h2>Partners</h2>
  <div class="features">
    <div>🤝 <strong>Roblox Trolling Union</strong></div>
    <div class="partner-buttons">
      <a href="https://robloxtrollers.xyz" target="_blank" class="btn btn-secondary">Visit Website</a>
      <a href="https://discord.gg/robloxtrollers" target="_blank" class="btn btn-secondary">Join Discord</a>
    </div>
  </div>
</div>
<style>
  .partner-buttons {
    display: flex;
    gap: 20px;
    justify-content: center;
    margin-top: 20px;
  }
  .partner-buttons a {
    text-align: center;
    flex: 1;
  }
  @media (max-width: 768px) {
    .partner-buttons {
      flex-direction: row;
    }
  }
</style>
  </div>
  <div class="footer">
    We are not partnered or affiliated with the Washiez game, or any Washiez owned projects or places.<br>Copyright © 2025 washiez.lol - All rights reserved
  </div>
  <script src="https://unpkg.com/aos@2.3.1/dist/aos.js"></script>
  <script>AOS.init();</script>
  <script>
    function copyScript() {
      const script = "loadstring(game:HttpGet('https://washiez.lol/script.lua'))()";
      navigator.clipboard.writeText(script).then(() => {
        showToast("Copied script to clipboard.");
      }).catch(err => {
        showToast("Failed to copy script.");
        console.error(err);
      });
    }

    function showToast(message) {
      const toast = document.createElement("div");
      toast.className = "custom-toast";
      toast.textContent = message;
      document.body.appendChild(toast);
      setTimeout(() => {
        toast.remove();
      }, 3000);
    }
  </script>
</body>
</html>
