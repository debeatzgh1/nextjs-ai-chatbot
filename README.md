<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Debeatzgh AI Agents Hub</title>

<style>
/* ======== GLOBAL STYLES ======== */
body {
  font-family: Arial, sans-serif;
  margin: 0;
  background: #f4f4f4;
}

/* ===== FLOATING AI BUTTON ===== */
.floating-ai-btn {
  position: fixed;
  top: 20px;
  right: 20px;
  background: #0b8dff;
  color: #fff;
  padding: 12px 16px;
  font-size: 14px;
  border-radius: 50px;
  cursor: pointer;
  z-index: 9999;
  box-shadow: 0 4px 12px rgba(0,0,0,0.2);
  display: flex;
  align-items: center;
  gap: 6px;
}

.floating-ai-btn img {
  width: 22px;
  height: 22px;
  border-radius: 50%;
}

/* ===== MODAL BACKDROP ===== */
#agentModal {
  display: none;
  position: fixed;
  top: 0; left: 0;
  width: 100%; height: 100%;
  background: rgba(0,0,0,0.6);
  backdrop-filter: blur(4px);
  z-index: 99999;
}

/* ===== MODAL CONTAINER ===== */
.agent-modal-content {
  background: #fff;
  width: 95%;
  max-width: 900px;
  margin: 50px auto;
  border-radius: 10px;
  padding: 20px;
  position: relative;
}

/* Close Button */
.close-modal {
  position: absolute;
  top: 12px;
  right: 18px;
  font-size: 28px;
  cursor: pointer;
  color: #333;
}

/* ===== CAROUSEL STYLES ===== */
.carousel {
  position: relative;
  overflow: hidden;
}

.carousel-track {
  display: flex;
  transition: transform 0.4s ease-in-out;
}

.carousel-item {
  min-width: 100%;
  padding: 10px;
}

.agent-card {
  background: #fff;
  border-radius: 12px;
  padding: 15px;
  text-align: center;
}

.agent-thumbnail {
  width: 100%;
  max-height: 220px;
  object-fit: cover;
  border-radius: 12px;
  margin-bottom: 15px;
}

.view-btn {
  background: #0faa4b;
  color: #fff;
  padding: 12px 18px;
  border-radius: 8px;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  margin-top: 10px;
}

/* Carousel Navigation */
.carousel-nav {
  display: flex;
  justify-content: space-between;
  margin-top: 10px;
}

.carousel-btn {
  background: #0b8dff;
  color: #fff;
  padding: 8px 14px;
  border-radius: 8px;
  cursor: pointer;
}
</style>
</head>

<body>

<!-- FLOATING BUTTON -->
<div class="floating-ai-btn" onclick="openModal()">
  <img src="https://cdn-icons-png.flaticon.com/512/4712/4712100.png" alt="AI Icon">
  AI Agents
</div>

<!-- MODAL POPUP -->
<div id="agentModal">
  <div class="agent-modal-content">

    <span class="close-modal" onclick="closeModal()">&times;</span>

    <h2 style="text-align:center; margin-top:10px;">Debeatzgh AI Assistant Hub</h2>

    <!-- CAROUSEL -->
    <div class="carousel">
      <div class="carousel-track">

        <!-- ITEM 1 -->
        <div class="carousel-item">
          <div class="agent-card">
            <img class="agent-thumbnail" src="https://cdn-icons-png.flaticon.com/512/4712/4712100.png">
            <h3>Side Hustle AI Agent</h3>
            <p>Your personal guide to starting, building, and scaling profitable side hustles.</p>
            <a class="view-btn" href="#sideHustleAgent">View Agent</a>

            <div id="sideHustleAgent" style="margin-top:15px;">
              <iframe id="JotFormIFrame-0195479af1b879f3a82ea15cbaf3859eaa44"
                allow="geolocation; microphone; camera; fullscreen"
                src="https://agent.jotform.com/0195479af1b879f3a82ea15cbaf3859eaa44?embedMode=iframe&background=1&shadow=1"
                style="width:100%; height:680px; border:none;">
              </iframe>
            </div>
          </div>
        </div>

        <!-- ITEM 2 -->
        <div class="carousel-item">
          <div class="agent-card">
            <img class="agent-thumbnail" src="https://cdn-icons-png.flaticon.com/512/4712/4712100.png">
            <h3>Debeatzgh AI Assistant</h3>
            <p>Your all-round AI assistant for ideas, content, tools, and productivity.</p>
            <a class="view-btn" href="#mainAssistant">View Agent</a>

            <div id="mainAssistant" style="margin-top:15px;">
              <iframe id="JotFormIFrame-0195424fb5d47897a72080768094791e9c32"
                allow="geolocation; microphone; camera; fullscreen"
                src="https://agent.jotform.com/0195424fb5d47897a72080768094791e9c32?embedMode=iframe&background=1&shadow=1"
                style="width:100%; height:680px; border:none;">
              </iframe>
            </div>
          </div>
        </div>

        <!-- ITEM 3 -->
        <div class="carousel-item">
          <div class="agent-card">
            <img class="agent-thumbnail" src="https://cdn-icons-png.flaticon.com/512/4712/4712100.png">
            <h3>AI Companion Assistant</h3>
            <p>Your friendly, helpful AI partner for learning, tasks & personal support.</p>
            <a class="view-btn" href="#aiCompanion">View Agent</a>

            <div id="aiCompanion" style="margin-top:15px;">
              <iframe id="JotFormIFrame-0195482a4e8d72b894a09678ddb9b513d564"
                allow="geolocation; microphone; camera; fullscreen"
                src="https://agent.jotform.com/0195482a4e8d72b894a09678ddb9b513d564?embedMode=iframe&background=1&shadow=1"
                style="width:100%; height:680px; border:none;">
              </iframe>
            </div>
          </div>
        </div>

      </div>

      <!-- NAVIGATION -->
      <div class="carousel-nav">
        <button class="carousel-btn" onclick="moveCarousel(-1)">Prev</button>
        <button class="carousel-btn" onclick="moveCarousel(1)">Next</button>
      </div>

    </div>
  </div>
</div>


<!-- SCRIPTS -->
<script>
let index = 0;
function moveCarousel(direction) {
  const track = document.querySelector(".carousel-track");
  const items = document.querySelectorAll(".carousel-item");
  index += direction;
  if (index < 0) index = items.length - 1;
  if (index >= items.length) index = 0;
  track.style.transform = `translateX(-${index * 100}%)`;
}

function openModal() {
  document.getElementById("agentModal").style.display = "block";
}

function closeModal() {
  document.getElementById("agentModal").style.display = "none";
}
</script>

</body>
</html>
