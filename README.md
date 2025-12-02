<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Debeatzgh AI Agents Hub</title>

<style>
body {
  margin: 0;
  font-family: Arial, sans-serif;
  overflow-y: auto !important;    /* PREVENT SCROLL LOCK */
}

/* Floating button */
.floating-ai-btn {
  position: fixed;
  top: 20px;
  right: 20px;
  background: #0b8dff;
  color: #fff;
  padding: 10px 16px;
  border-radius: 50px;
  font-size: 14px;
  display: flex;
  align-items: center;
  gap: 5px;
  cursor: pointer;
  z-index: 99999;
}

.floating-ai-btn img {
  width: 20px;
  height: 20px;
}

/* Modal (NO SCROLL BLOCKING) */
#agentModal {
  display: none;
  position: fixed;
  inset: 0;
  background: rgba(0,0,0,0.55);
  z-index: 999999;
  overflow-y: auto !important;     /* MAKE MODAL SCROLLABLE */
  padding: 20px 0;
}

/* Modal Window */
.agent-modal-content {
  background: #fff;
  width: 95%;
  max-width: 900px;
  margin: auto;
  border-radius: 12px;
  padding: 20px;
  position: relative;
}

.close-modal {
  position: absolute;
  top: 12px;
  right: 20px;
  font-size: 28px;
  cursor: pointer;
}

/******** CAROUSEL ********/
.carousel {
  overflow: hidden;
}

.carousel-track {
  display: flex;
  transition: transform 0.4s ease-in-out;
}

.carousel-item {
  min-width: 100%;
}

.agent-card {
  text-align: center;
}

.agent-thumbnail {
  width: 100%;
  max-height: 220px;
  object-fit: cover;
  border-radius: 12px;
}

/***** SCROLLABLE IFRAME FIX ******/
.agent-iframe-wrapper {
  width: 100%;
  height: 650px;
  overflow-y: scroll !important;
  border: 1px solid #ddd;
  border-radius: 10px;
  margin-top: 15px;
  background: #fff;
}

.agent-iframe-wrapper iframe {
  width: 100%;
  height: 1000px;  /* large so user scrolls inside wrapper */
  border: none;
}

/* Buttons */
.view-btn {
  background: #0faa4b;
  padding: 10px 16px;
  color: #fff;
  border-radius: 8px;
  text-decoration: none;
  display: inline-block;
  margin-top: 10px;
}

.carousel-nav {
  display: flex;
  justify-content: space-between;
  margin-top: 12px;
}

.carousel-btn {
  background: #0b8dff;
  padding: 8px 14px;
  color: #fff;
  border-radius: 8px;
  cursor: pointer;
}
</style>
</head>

<body>

<div class="floating-ai-btn" onclick="openModal()">
  <img src="https://cdn-icons-png.flaticon.com/512/4712/4712100.png" />
  AI Agents
</div>

<!-- Modal -->
<div id="agentModal">
  <div class="agent-modal-content">

    <span class="close-modal" onclick="closeModal()">&times;</span>
    <h2 style="text-align:center;">Debeatzgh AI Agent Hub</h2>

    <div class="carousel">
      <div class="carousel-track">

        <!-- Item 1 -->
        <div class="carousel-item">
          <div class="agent-card">
            <img class="agent-thumbnail" src="https://cdn-icons-png.flaticon.com/512/4712/4712100.png">
            <h3>Side Hustle AI Agent</h3>
            <p>Your personal guide for building profitable AI side hustles.</p>

            <a class="view-btn" onclick="scrollInto('agent1')">View Agent</a>

            <div id="agent1" class="agent-iframe-wrapper">
              <iframe src="https://agent.jotform.com/0195479af1b879f3a82ea15cbaf3859eaa44?embedMode=iframe&background=1&shadow=1"></iframe>
            </div>
          </div>
        </div>

        <!-- Item 2 -->
        <div class="carousel-item">
          <div class="agent-card">
            <img class="agent-thumbnail" src="https://cdn-icons-png.flaticon.com/512/4712/4712100.png">
            <h3>Debeatzgh AI Assistant</h3>
            <p>Ideas, creativity, and productivity support for your digital journey.</p>

            <a class="view-btn" onclick="scrollInto('agent2')">View Agent</a>

            <div id="agent2" class="agent-iframe-wrapper">
              <iframe src="https://agent.jotform.com/0195424fb5d47897a72080768094791e9c32?embedMode=iframe&background=1&shadow=1"></iframe>
            </div>
          </div>
        </div>

        <!-- Item 3 -->
        <div class="carousel-item">
          <div class="agent-card">
            <img class="agent-thumbnail" src="https://cdn-icons-png.flaticon.com/512/4712/4712100.png">
            <h3>AI Companion Assistant</h3>
            <p>Your friendly learning and productivity partner.</p>

            <a class="view-btn" onclick="scrollInto('agent3')">View Agent</a>

            <div id="agent3" class="agent-iframe-wrapper">
              <iframe src="https://agent.jotform.com/0195482a4e8d72b894a09678ddb9b513d564?embedMode=iframe&background=1&shadow=1"></iframe>
            </div>
          </div>
        </div>

      </div>
    </div>

    <div class="carousel-nav">
      <button class="carousel-btn" onclick="moveCarousel(-1)">Prev</button>
      <button class="carousel-btn" onclick="moveCarousel(1)">Next</button>
    </div>

  </div>
</div>

<script>
let index = 0;

function moveCarousel(dir) {
  const track = document.querySelector(".carousel-track");
  const items = document.querySelectorAll(".carousel-item");

  index += dir;
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

function scrollInto(id) {
  document.getElementById(id).scrollIntoView({ behavior: "smooth" });
}
</script>

</body>
</html>
