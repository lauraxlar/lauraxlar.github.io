<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Roblox Trolling Union</title>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.11.4/gsap.min.js"></script>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    }

    body {
      background-color: #0f0f0f;
      color: #f0f0f0;
      overflow-x: hidden;
    }

    .cursor {
      position: fixed;
      width: 20px;
      height: 20px;
      border-radius: 50%;
      background-color: rgba(255, 0, 0, 0.5);
      pointer-events: none;
      z-index: 9999;
      transform: translate(-50%, -50%);
      transition: width 0.2s, height 0.2s;
      mix-blend-mode: difference;
    }

    .cursor-follower {
      position: fixed;
      width: 40px;
      height: 40px;
      border-radius: 50%;
      border: 2px solid rgba(255, 0, 0, 0.5);
      pointer-events: none;
      z-index: 9998;
      transform: translate(-50%, -50%);
      transition: 0.1s;
      mix-blend-mode: difference;
    }

    .particles {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      z-index: -1;
    }

    header {
      padding: 2rem;
      text-align: center;
      background: linear-gradient(135deg, #ff0000, #700000);
      position: relative;
      overflow: hidden;
    }

    .logo {
      font-size: 3rem;
      font-weight: bold;
      margin-bottom: 1rem;
      text-shadow: 0 0 10px rgba(255, 0, 0, 0.7);
      animation: pulse 2s infinite;
    }

    @keyframes pulse {
      0% { transform: scale(1); }
      50% { transform: scale(1.05); }
      100% { transform: scale(1); }
    }

    .tagline {
      font-size: 1.2rem;
      opacity: 0.9;
    }

    nav {
      background-color: #1a1a1a;
      border-bottom: 2px solid #ff0000;
      position: sticky;
      top: 0;
      z-index: 100;
    }

    .tabs {
      display: flex;
      justify-content: center;
      list-style: none;
      padding: 0;
    }

    .tab-item {
      padding: 1rem 2rem;
      font-size: 1.1rem;
      cursor: pointer;
      position: relative;
      transition: 0.3s;
    }

    .tab-item:hover {
      background-color: rgba(255, 0, 0, 0.2);
    }

    .tab-item.active {
      background-color: rgba(255, 0, 0, 0.3);
    }
    * {
  cursor: none !important;
}
    .tab-item::after {
      content: '';
      position: absolute;
      bottom: 0;
      left: 50%;  
      transform: translateX(-50%);
      width: 0;
      height: 3px;
      background-color: #ff0000;
      transition: width 0.3s;
    }

    .tab-item:hover::after,
    .tab-item.active::after {
      width: 80%;
    }

    .content {
      padding: 2rem;
      max-width: 1200px;
      margin: 0 auto;
    }

    .tab-content {
      display: none;
    }

    .tab-content.active {
      display: block;
      animation: fadeIn 0.5s;
    }

    @keyframes fadeIn {
      0% { opacity: 0; transform: translateY(10px); }
      100% { opacity: 1; transform: translateY(0); }
    }

    .script-card {
      background-color: #1a1a1a;
      border: 1px solid #333;
      border-radius: 8px;
      padding: 1.5rem;
      margin-bottom: 1.5rem;
      transition: 0.3s;
      position: relative;
      overflow: hidden;
    }

    .script-card:hover {
      transform: translateY(-5px);
      box-shadow: 0 10px 20px rgba(255, 0, 0, 0.1);
      border-color: #ff0000;
    }

    .script-card::before {
      content: '';
      position: absolute;
      top: 0;
      left: 0;
      width: 4px;
      height: 100%;
      background-color: #ff0000;
    }

    .script-title {
      font-size: 1.5rem;
      margin-bottom: 0.5rem;
      display: flex;
      align-items: center;
    }

    .verified-badge {
      background-color: #00aa00;
      color: white;
      padding: 0.2rem 0.5rem;
      border-radius: 4px;
      font-size: 0.8rem;
      margin-left: 1rem;
    }

    .script-description {
      color: #ccc;
      margin-bottom: 1rem;
    }

    .script-meta {
      display: flex;
      font-size: 0.9rem;
      color: #888;
    }

    .script-meta div {
      margin-right: 1rem;
    }

    .download-btn {
      background-color: #ff0000;
      color: white;
      border: none;
      padding: 0.5rem 1rem;
      border-radius: 4px;
      cursor: pointer;
      margin-top: 1rem;
      transition: 0.3s;
    }

    .download-btn:hover {
      background-color: #cc0000;
      transform: scale(1.05);
    }

    .member-card {
      display: flex;
      background-color: #1a1a1a;
      border-radius: 8px;
      padding: 1rem;
      margin-bottom: 1rem;
      align-items: center;
    }

    .member-avatar {
      width: 80px;
      height: 80px;
      border-radius: 8px;
      margin-right: 1rem;
      object-fit: cover;
      border: 2px solid #333;
    }

    .member-info {
      flex: 1;
    }

    .member-name {
      font-size: 1.2rem;
      margin-bottom: 0.5rem;
    }

    .member-role {
      color: #ff0000;
      font-size: 0.9rem;
      margin-bottom: 0.5rem;
    }

    .member-bio {
      color: #ccc;
      font-size: 0.9rem;
    }

    footer {
      background-color: #1a1a1a;
      text-align: center;
      padding: 2rem;
      margin-top: 2rem;
      border-top: 2px solid #ff0000;
    }

    .join-discord {
      display: inline-block;
      background-color: #5865F2;
      color: white;
      padding: 0.8rem 1.5rem;
      border-radius: 4px;
      text-decoration: none;
      margin-top: 1rem;
      transition: 0.3s;
    }

    .join-discord:hover {
      background-color: #4752c4;
      transform: translateY(-3px);
    }

    .announcement {
      background-color: rgba(255, 0, 0, 0.1);
      border-left: 4px solid #ff0000;
      padding: 1rem;
      margin-bottom: 2rem;
    }

    .tutorial {
      background-color: #1a1a1a;
      border-radius: 8px;
      padding: 1.5rem;
      margin-bottom: 1.5rem;
    }

    .tutorial ol {
      margin-left: 1.5rem;
      margin-top: 1rem;
    }

    .tutorial li {
      margin-bottom: 0.8rem;
      color: #ddd;
    }

    .faq-item {
      margin-bottom: 1.5rem;
    }

    .faq-question {
      font-size: 1.2rem;
      margin-bottom: 0.5rem;
      color: #ff5555;
    }

    .faq-answer {
      color: #ccc;
    }

    code {
      background-color: #252525;
      padding: 0.2rem 0.4rem;
      border-radius: 4px;
      font-family: monospace;
    }

    @media (max-width: 768px) {
      .tabs {
        flex-wrap: wrap;
      }
      
      .tab-item {
        padding: 0.8rem 1rem;
      }
    }
    
    .glitch {
      position: relative;
    }
    
    .glitch::before,
    .glitch::after {
      content: attr(data-text);
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
    }
    
    .glitch::before {
      left: 2px;
      text-shadow: -2px 0 #00fff2;
      clip: rect(44px, 450px, 56px, 0);
      animation: glitch-anim 5s infinite linear alternate-reverse;
    }
    
    .glitch::after {
      left: -2px;
      text-shadow: -2px 0 #ff00c1;
      clip: rect(44px, 450px, 56px, 0);
      animation: glitch-anim2 5s infinite linear alternate-reverse;
    }
    
    @keyframes glitch-anim {
      0% {
        clip: rect(31px, 9999px, 94px, 0);
      }
      4.16666667% {
        clip: rect(91px, 9999px, 43px, 0);
      }
      8.33333333% {
        clip: rect(15px, 9999px, 13px, 0);
      }
      12.5% {
        clip: rect(75px, 9999px, 57px, 0);
      }
      16.66666667% {
        clip: rect(46px, 9999px, 78px, 0);
      }
      20.83333333% {
        clip: rect(81px, 9999px, 38px, 0);
      }
      25% {
        clip: rect(13px, 9999px, 66px, 0);
      }
      29.16666667% {
        clip: rect(25px, 9999px, 98px, 0);
      }
      33.33333333% {
        clip: rect(47px, 9999px, 27px, 0);
      }
      37.5% {
        clip: rect(64px, 9999px, 85px, 0);
      }
      41.66666667% {
        clip: rect(64px, 9999px, 81px, 0);
      }
      45.83333333% {
        clip: rect(27px, 9999px, 87px, 0);
      }
      50% {
        clip: rect(7px, 9999px, 42px, 0);
      }
      54.16666667% {
        clip: rect(21px, 9999px, 49px, 0);
      }
      58.33333333% {
        clip: rect(80px, 9999px, 91px, 0);
      }
      62.5% {
        clip: rect(27px, 9999px, 59px, 0);
      }
      66.66666667% {
        clip: rect(54px, 9999px, 85px, 0);
      }
      70.83333333% {
        clip: rect(72px, 9999px, 57px, 0);
      }
      75% {
        clip: rect(66px, 9999px, 80px, 0);
      }
      79.16666667% {
        clip: rect(13px, 9999px, 55px, 0);
      }
      83.33333333% {
        clip: rect(66px, 9999px, 92px, 0);
      }
      87.5% {
        clip: rect(6px, 9999px, 6px, 0);
      }
      91.66666667% {
        clip: rect(60px, 9999px, 78px, 0);
      }
      95.83333333% {
        clip: rect(98px, 9999px, 75px, 0);
      }
      100% {
        clip: rect(70px, 9999px, 46px, 0);
      }
    }
    
    @keyframes glitch-anim2 {
      0% {
        clip: rect(65px, 9999px, 100px, 0);
      }
      4.16666667% {
        clip: rect(84px, 9999px, 51px, 0);
      }
      8.33333333% {
        clip: rect(75px, 9999px, 12px, 0);
      }
      12.5% {
        clip: rect(94px, 9999px, 94px, 0);
      }
      16.66666667% {
        clip: rect(62px, 9999px, 11px, 0);
      }
      20.83333333% {
        clip: rect(77px, 9999px, 63px, 0);
      }
      25% {
        clip: rect(43px, 9999px, 14px, 0);
      }
      29.16666667% {
        clip: rect(33px, 9999px, 3px, 0);
      }
      33.33333333% {
        clip: rect(72px, 9999px, 90px, 0);
      }
      37.5% {
        clip: rect(2px, 9999px, 66px, 0);
      }
      41.66666667% {
        clip: rect(92px, 9999px, 73px, 0);
      }
      45.83333333% {
        clip: rect(95px, 9999px, 46px, 0);
      }
      50% {
        clip: rect(42px, 9999px, 46px, 0);
      }
      54.16666667% {
        clip: rect(71px, 9999px, 24px, 0);
      }
      58.33333333% {
        clip: rect(81px, 9999px, 85px, 0);
      }
      62.5% {
        clip: rect(30px, 9999px, 8px, 0);
      }
      66.66666667% {
        clip: rect(41px, 9999px, 42px, 0);
      }
      70.83333333% {
        clip: rect(10px, 9999px, 63px, 0);
      }
      75% {
        clip: rect(51px, 9999px, 77px, 0);
      }
      79.16666667% {
        clip: rect(92px, 9999px, 57px, 0);
      }
      83.33333333% {
        clip: rect(21px, 9999px, 68px, 0);
      }
      87.5% {
        clip: rect(20px, 9999px, 15px, 0);
      }
      91.66666667% {
        clip: rect(72px, 9999px, 31px, 0);
      }
      95.83333333% {
        clip: rect(85px, 9999px, 100px, 0);
      }
      100% {
        clip: rect(96px, 9999px, 13px, 0);
      }
    }
  </style>
</head>
<body>
  <div class="cursor"></div>
  <div class="cursor-follower"></div>
  <div class="particles"></div>

  <header>
    <div class="logo glitch" data-text="ROBLOX TROLLING UNION">ROBLOX TROLLING UNION</div>
    <div class="tagline">Unleash Chaos, Unite Trollers</div>
  </header>

  <nav>
    <ul class="tabs">
      <li class="tab-item active" data-tab="home">Home</li>
      <li class="tab-item" data-tab="verified-scripts">Verified Scripts</li>
      <li class="tab-item" data-tab="tutorials">Tutorials</li>
      <li class="tab-item" data-tab="members">Members</li>
      <li class="tab-item" data-tab="faq">FAQ</li>
    </ul>
  </nav>

  <div class="content">
    <div class="tab-content active" id="home">
      <div class="announcement">
        <h2>🔥 Latest Update - April 12, 2025</h2>
        <p>Welcome to the new Roblox Trolling Union website! We've added new scripts and resources to help you become the ultimate troller.</p>
      </div>

      <h2>Welcome to the Roblox Trolling Union</h2>
      ‎ 

      <p>We are a community dedicated to the art of trolling in Roblox. Our mission is to provide high-quality, verified scripts and techniques to make your trolling experience more enjoyable and effective.</p>
      ‎ 
      
      <h3>What We Offer:</h3>
      <ul>
        <li>Verified and safe scripts that won't get you banned</li>
        <li>Tutorials on advanced trolling techniques</li>
        <li>A supportive community of like-minded trollers</li>
        <li>Regular updates and new script releases</li>
        ‎ 
            </ul>
      
      <h3>Getting Started</h3>
      <p>New to trolling? Check out our <a href="#" onclick="openTab('tutorials')">Tutorials</a> section to learn the basics. Already experienced? Head over to our <a href="#" onclick="openTab('verified-scripts')">Verified Scripts</a> page to find the latest tools for your trolling arsenal.</p>
    </div>

    <div class="tab-content" id="verified-scripts">
      <h2>Verified Scripts</h2>
      ‎ 

      <p>All scripts below have been tested and verified by our team. They are safe to use and regularly updated to work with the latest Roblox versions.</p>
      ‎ 

      <div class="script-card">
        <h3 class="script-title">washiez.lol <span class="verified-badge">Verified</span></h3>
        <p class="script-description">Has alot of functionallity, Good general purpose script.</p>
        <div class="script-meta">
          <div>Updated: April 12, 2025</div>
          <div>Creator: BurntRibs24</div>
          <div>Rating: ⭐⭐⭐⭐⭐</div>
        </div>
        <button class="download-btn">Copy Script</button>
      </div>

      <div class="script-card">
        <h3 class="script-title">lancet <span class="verified-badge">Verified</span></h3>
        <p class="script-description">Automatically kills cars using a good player fling method.</p>
        <div class="script-meta">
          <div>Updated: April 12, 2025</div>
          <div>Creator: Mye and Rosploiter</div>
          <div>Rating: ⭐⭐⭐⭐⭐</div>
        </div>
        <button class="download-btn">Copy Script</button>
      </div>
    </div>

    <div class="tab-content" id="tutorials">
      <h2>Trolling Tutorials</h2>
      ‎ 

      <p>Learn the art of trolling from the best in the community. These tutorials will help you master various techniques to become an elite troller.</p>
      ‎ 

      <div class="script-card" style="padding-left: 30px; margin-left: 20px;">
        <h3 class="script-title">Beginner's Guide to Trolling <span class="verified-badge">Tutorial</span></h3>
        <p class="script-description">Start your trolling journey with these basic techniques:</p>
        <ul class="tutorial-content">
          <li>Finding the right games to troll</li>
          <li>Basic script execution using our recommended executor</li>
          <li>How to avoid getting reported or banned</li>
          <li>Creating your first trolling persona</li>
        </ul>
        <div class="script-meta">
          <div>Skill Level: Beginner</div>
          <div>Last Updated: April 10, 2025</div>
        </div>
      </div>
    
      <div class="script-card" style="padding-left: 30px; margin-left: 20px;">
        <h3 class="script-title">Master Class: The Art of Deception <span class="verified-badge">Advanced</span></h3>
        <p class="script-description">Advanced trolling techniques for experienced trollers:</p>
        <ul class="tutorial-content">
          <li>Creating elaborate fake events in games</li>
          <li>Coordinating with other trollers for maximum impact</li>
          <li>Using social engineering to enhance your trolling</li>
          <li>Recording and sharing your best trolling moments</li>
        </ul>
        <div class="script-meta">
          <div>Skill Level: Expert</div>
          <div>Last Updated: April 12, 2025</div>
        </div>
      </div>
    </div>

    <div class="tab-content" id="members">
      <h2>Our Top Trollers</h2>
      ‎ 

      <p>Meet the elite members of our union who have mastered the art of trolling in Roblox.</p>
      ‎ 

      <div class="member-card">
        <img src="https://cdn.discordapp.com/avatars/1158839658738892872/e08c47d5f6d7478ff4abe47343da0e36.png?size=512" alt="BurntRibs24" class="member-avatar">
        <div class="member-info">
          <h3 class="member-name">BurntRibs</h3>
          <div class="member-role">Founder of RTU</div>
          <p class="member-bio">Created the union in 2024 and has developed over the year alot of trolling scripts. Known for creating the washiez.lol script.</p>
        </div>
      </div>

      <div class="member-card">
        <img src="https://cdn.discordapp.com/avatars/696951589801427035/c047ec241053d0bfd3dba926168699ed.png?size=512" alt="Force" class="member-avatar">
        <div class="member-info">
          <h3 class="member-name">Force</h3>
          <div class="member-role">Co owner@RTU</div>
          <p class="member-bio">Finds alot of chat bypasses, makes exposed documents , Co owner in rtu so that's cool.</p>
        </div>
      </div>

      <div class="member-card">
        <img src="https://cdn.discordapp.com/avatars/935992867552366602/18728841e7d1d3d369cb62686a78c2bb.png?size=512" alt="sus!" class="member-avatar">
        <div class="member-info">
          <h3 class="member-name">sus!</h3>
          <div class="member-role">Co Owner@RTU</div>
          <p class="member-bio">Makes scripts, Known for making a fling bypass.</p>
        </div>
      </div>
      <div class="member-card">
        <img src="https://cdn.discordapp.com/avatars/794345726103519272/78b9f4786c29e8f34b4f19d663885cc8.png?size=512" alt="Mye" class="member-avatar">
        <div class="member-info">
          <h3 class="member-name">Mye</h3>
          <div class="member-role">Script dev</div>
          <p class="member-bio">Makes new AC bypasses, Known for making the hatfling bypass which was OP until it was patched.</p>
        </div>
      </div>
      <div class="member-card">
        <img src="https://cdn.discordapp.com/avatars/1249664287987728386/8f80bbcf015e0d28894f6197f93190d4.png?size=512" alt="Africa" class="member-avatar">
        <div class="member-info">
          <h3 class="member-name">Africa</h3>
          <div class="member-role">Script dev</div>
          <p class="member-bio">Glitches alot in washiez, Known for good auto racist gun script.</p>
        </div>
      </div>  <div class="member-card">
        <img src="https://cdn.discordapp.com/avatars/1307448409518772305/54595017aeb8c9b830ade61658c53d9f.png?size=512" alt="Russia" class="member-avatar">
        <div class="member-info">
          <h3 class="member-name">Russia</h3>
          <div class="member-role">Script dev</div>
          <p class="member-bio">BEST washiez script dev, Made alot of cool shit and is og creator of lancet.</p>
        </div>
      </div>
    </div>

    <div class="tab-content" id="faq">
      <h2>Frequently Asked Questions</h2>
      ‎ 

      <p>Common questions about our scripts, community, and trolling practices.</p>
      ‎ 

      <div class="member-card faq-card">
        <div class="member-info">
          <h3 class="member-name">Are these scripts safe to use?</h3>
          <div class="member-role">Safety Concerns</div>
          <p class="member-bio">Yes, all scripts on our website are thoroughly tested and verified by our security team. We ensure they don't contain any malicious code and minimize the risk of getting your account banned.</p>
        </div>
      </div>
    
      <div class="member-card faq-card">
        <div class="member-info">
          <h3 class="member-name">What script executor should I use?</h3>
          <div class="member-role">Recommended Tools</div>
          <p class="member-bio">We recommend using trusted and well-maintained executors like Swift for PC, KRNL for Android, or Delta for IOS. Our scripts are designed to work with these popular executors.</p>
        </div>
      </div>
    
      <div class="member-card faq-card">
        <div class="member-info">
          <h3 class="member-name">How do I join the Roblox Trolling Union?</h3>
          <div class="member-role">Community Membership</div>
          <p class="member-bio">You can join our community by clicking the Discord button at the bottom of the page. After joining, introduce yourself and share some of your trolling experiences to get verified.</p>
        </div>
      </div>
    
      <div class="member-card faq-card">
        <div class="member-info">
          <h3 class="member-name">How often are scripts updated?</h3>
          <div class="member-role">Updates & Maintenance</div>
          <p class="member-bio">We update our scripts regularly to ensure they work with the latest Roblox updates. Major scripts are updated at least once a month, while smaller scripts may be updated less frequently.</p>
        </div>
      </div>
    
      <div class="member-card faq-card">
        <div class="member-info">
          <h3 class="member-name">Can I get banned for using these scripts?</h3>
          <div class="member-role">Risk Assessment</div>
          <p class="member-bio">While we design our scripts to be as safe as possible, there's always a risk when using any scripts in Roblox. We recommend using an alt account for trolling and following our safety guidelines to minimize risks.</p>
        </div>
      </div>
    </div>
  </div>

  <footer>
    <p>© 2025 Roblox Trolling Union | Not affiliated with Roblox Corporation</p>
    <p>Join our community of 700+ trollers:</p>
    <a href="#" class="join-discord">Join Our Discord</a>
  </footer>

  <script>
    const cursor = document.querySelector(".cursor");
    const cursorFollower = document.querySelector(".cursor-follower");

    document.addEventListener("mousemove", function(e) {
      gsap.to(cursor, {
        x: e.clientX,
        y: e.clientY,
        duration: 0.1
      });
      
      gsap.to(cursorFollower, {
        x: e.clientX,
        y: e.clientY,
        duration: 0.3
      });
    });
    document.querySelector('.join-discord').addEventListener('click', function(e) {
  e.preventDefault();
  window.open('https://discord.gg/robloxtrollers', '_blank');
});
    const hoverables = document.querySelectorAll("a, button, .tab-item, .script-card, .member-card");
    hoverables.forEach(hoverable => {
      hoverable.addEventListener("mouseenter", function() {
        cursor.style.width = "40px";
        cursor.style.height = "40px";
        cursorFollower.style.width = "60px";
        cursorFollower.style.height = "60px";
      });
      
      hoverable.addEventListener("mouseleave", function() {
        cursor.style.width = "20px";
        cursor.style.height = "20px";
        cursorFollower.style.width = "40px";
        cursorFollower.style.height = "40px";
      });
    });

    function openTab(tabId) {
      document.querySelectorAll('.tab-content').forEach(tab => {
        tab.classList.remove('active');
      });
      
      document.querySelectorAll('.tab-item').forEach(tab => {
        tab.classList.remove('active');
      });
      
      document.getElementById(tabId).classList.add('active');
      document.querySelector(`.tab-item[data-tab="${tabId}"]`).classList.add('active');
    }

    document.querySelectorAll('.tab-item').forEach(tab => {
      tab.addEventListener('click', function() {
        openTab(this.getAttribute('data-tab'));
      });
    });

    function createParticles() {
      const particlesContainer = document.querySelector('.particles');
      const particleCount = 50;
      
      for (let i = 0; i < particleCount; i++) {
        const particle = document.createElement('div');
        particle.style.position = 'absolute';
        particle.style.width = Math.random() * 4 + 1 + 'px';
        particle.style.height = particle.style.width;
        particle.style.backgroundColor = `rgba(255, ${Math.floor(Math.random() * 100)}, ${Math.floor(Math.random() * 100)}, ${Math.random() * 0.5 + 0.2})`;
        particle.style.borderRadius = '50%';
        particle.style.top = Math.random() * 100 + 'vh';
        particle.style.left = Math.random() * 100 + 'vw';
        particle.style.pointerEvents = 'none';
        
        const duration = Math.random() * 20 + 10;
        particle.style.animation = `float ${duration}s linear infinite`;
        
        const keyframes = `
        @keyframes float {
       0% {
            transform: translate(0, 0) rotate(0deg);
          }
          25% {
            transform: translate(${Math.random() * 100 - 50}px, ${Math.random() * 100 - 50}px) rotate(${Math.random() * 360}deg);
          }
          50% {
            transform: translate(${Math.random() * 100 - 50}px, ${Math.random() * 100 - 50}px) rotate(${Math.random() * 360}deg);
          }
          75% {
            transform: translate(${Math.random() * 100 - 50}px, ${Math.random() * 100 - 50}px) rotate(${Math.random() * 360}deg);
          }
          100% {
            transform: translate(0, 0) rotate(0deg);
          }
        }
        `;
        
        const style = document.createElement('style');
        style.innerHTML = keyframes;
        document.head.appendChild(style);
        
        particlesContainer.appendChild(particle);
      }
    }

    function initParallax() {
      document.addEventListener('mousemove', function(e) {
        const headerElements = document.querySelectorAll('header .logo, header .tagline');
        const x = e.clientX / window.innerWidth;
        const y = e.clientY / window.innerHeight;
        
        headerElements.forEach(element => {
          const speed = 20;
          const xPos = (0.5 - x) * speed;
          const yPos = (0.5 - y) * speed;
          
          element.style.transform = `translate(${xPos}px, ${yPos}px)`;
        });
      });
    }

const lancetScript = `loadstring(game:HttpGet("https://cdn.rtu.lol/autofling.lua"))()`;

const washiezScript = `loadstring(game:HttpGet('https://washiez.lol/script.lua'))()`;

document.querySelectorAll('.download-btn').forEach(button => {
    button.addEventListener('click', function() {
        const scriptCard = this.closest('.script-card');
        const scriptTitle = scriptCard.querySelector('.script-title').textContent.trim();
        const scriptName = scriptTitle.split(' ')[0].toLowerCase();
        
        let scriptContent = '';
        if (scriptName === 'lancet') {
            scriptContent = lancetScript;
        } else if (scriptName === 'washiez.lol') {
            scriptContent = washiezScript;
        } else {
            alert(`Script '${scriptName}' is not available for copying.`);
            return;
        }
        
        navigator.clipboard.writeText(scriptContent)
            .then(() => {
                alert(`Script '${scriptName}' has been copied to clipboard!`);
            })
            .catch(err => {
                console.error('Failed to copy script: ', err);
                alert('Failed to copy script. See console for details.');
            });
    });
});

    function initScrollReveal() {
      const cards = document.querySelectorAll('.script-card, .tutorial, .member-card, .faq-item');
      
      const observer = new IntersectionObserver((entries) => {
        entries.forEach(entry => {
          if (entry.isIntersecting) {
            entry.target.style.opacity = 1;
            entry.target.style.transform = 'translateY(0)';
          }
        });
      }, { threshold: 0.1 });
      
      cards.forEach(card => {
        card.style.opacity = 0;
        card.style.transform = 'translateY(20px)';
        card.style.transition = 'opacity 0.5s ease, transform 0.5s ease';
        observer.observe(card);
      });
    }

    document.addEventListener('DOMContentLoaded', function() {
      createParticles();
      initParallax();
      initScrollReveal();
      
      console.log("%cWelcome to the Roblox Trolling Union!", "color: red; font-size: 20px; font-weight: bold;");
      console.log("%cIf you're reading this, you might have what it takes to join our elite team.", "color: white; font-size: 14px;");
    });

    const mediaQuery = window.matchMedia('(max-width: 768px)');
    function handleMobileChanges(e) {
      if (e.matches) {
        document.querySelector('.cursor').style.display = 'none';
        document.querySelector('.cursor-follower').style.display = 'none';
      } else {
        document.querySelector('.cursor').style.display = 'block';
        document.querySelector('.cursor-follower').style.display = 'block';
      }
    }
    
    mediaQuery.addListener(handleMobileChanges);
    handleMobileChanges(mediaQuery);
    
    function showNotification(message) {
      const notification = document.createElement('div');
      notification.style.position = 'fixed';
      notification.style.bottom = '20px';
      notification.style.right = '20px';
      notification.style.backgroundColor = 'rgba(255, 0, 0, 0.8)';
      notification.style.color = 'white';
      notification.style.padding = '15px 20px';
      notification.style.borderRadius = '5px';
      notification.style.zIndex = '9999';
      notification.style.boxShadow = '0 4px 8px rgba(0, 0, 0, 0.2)';
      notification.style.animation = 'fadeIn 0.5s, fadeOut 0.5s 3.5s';
      notification.style.animationFillMode = 'forwards';
      notification.textContent = message;
      
      document.body.appendChild(notification);
      
      setTimeout(() => {
        notification.remove();
      }, 4000);
    }
    
    setTimeout(() => {
      showNotification("Welcome to the Roblox Trolling Union! Explore our latest scripts!");
    }, 3000);
    
    const notificationStyles = document.createElement('style');
    notificationStyles.innerHTML = `
      @keyframes fadeIn {
        from { opacity: 0; transform: translateY(20px); }
        to { opacity: 1; transform: translateY(0); }
      }
      @keyframes fadeOut {
        from { opacity: 1; transform: translateY(0); }
        to { opacity: 0; transform: translateY(-20px); }
      }
    `;
    document.head.appendChild(notificationStyles);
  </script>
</body>
</html>
