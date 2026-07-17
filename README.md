<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1">
<title>Aesthetic Minimalist Clock</title>

<style>
*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    width: 100vw;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    background: #191919; /* Warm aesthetic off-black */
    overflow: hidden;
    user-select: none;
}

.clock {
    width: 260px;
    height: 260px;
    position: relative;
}

/* 12 Hour Ticks */
.ticks {
    position: absolute;
    width: 100%;
    height: 100%;
}

/* Standard Minor Ticks (1, 2, 4, 5, 7, 8, 10, 11) */
.tick {
    position: absolute;
    width: 1.5px;
    height: 10px;
    background: #4DAB7A;
    opacity: 0.6;
    left: 50%;
    top: 0;
    transform-origin: 50% 130px; /* Pivots around center (260px / 2) */
    margin-left: -0.75px;
}

/* Major Ticks (12, 3, 6, 9) - Same width, just slightly longer */
.tick.major {
    height: 14px; 
    opacity: 0.8;  
}

/* Hands Configuration with Backwards-Extending Tail */
.hand-container {
    position: absolute;
    top: 50%;
    left: 50%;
    width: 0;
    height: 0;
}

.hand {
    position: absolute;
    left: 50%;
    background: #4DAB7A;
}

.hour {
    width: 3.5px;
    height: 75px; 
    bottom: -15px; /* Aesthetic 15px tail */
    transform-origin: 50% calc(100% - 15px);
    margin-left: -1.75px;
    opacity: 0.95;
    border-radius: 10px;
}

.minute {
    width: 2.2px;
    height: 110px; 
    bottom: -15px; /* Aesthetic 15px tail */
    transform-origin: 50% calc(100% - 15px);
    margin-left: -1.1px;
    opacity: 0.85;
    border-radius: 10px;
}

/* Proportioned elegant second hand */
.second {
    width: 1px;
    height: 115px; 
    bottom: -20px; /* Subtle 20px tail extending past center pivot */
    transform-origin: 50% calc(100% - 20px);
    margin-left: -0.5px;
    opacity: 0.6; 
    background: #4DAB7A;
}

/* Solid Aesthetic Pivot Dot */
.center-dot {
    position: absolute;
    width: 8px;
    height: 8px;
    background: #4DAB7A;
    border-radius: 50%;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
    z-index: 10;
}

/* Shifted Display Info Layout */
.center {
    position: absolute;
    left: 50%;
    top: 62%; 
    transform: translateX(-50%);
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    z-index: 5; 
}

/* Updated Typography - Regular weight for real aesthetic */
.time {
    font-family: 'Courier New', Courier, monospace;
    font-size: 27px;
    font-weight: normal;
    letter-spacing: 0.5px;
    color: #4DAB7A;
    white-space: nowrap;
}

.date {
    margin-top: 4px;
    font-family: 'Courier New', Courier, monospace;
    font-size: 15px;
    font-weight: normal;
    color: #527c65; 
    white-space: nowrap;
}
</style>
</head>

<body>

<div class="clock">
    <!-- Hour Ticks -->
    <div class="ticks" id="ticks"></div>

    <!-- Clock Hands -->
    <div class="hand-container">
        <div id="hour" class="hand hour"></div>
        <div id="minute" class="hand minute"></div>
        <div id="second" class="hand second"></div>
    </div>
    
    <!-- Central Pivot Dot -->
    <div class="center-dot"></div>

    <!-- Digital Overlay -->
    <div class="center">
        <div class="time" id="digital"></div>
        <div class="date" id="date"></div>
    </div>
</div>

<script>
// Generate 12 dial ticks dynamically
const ticksContainer = document.getElementById("ticks");
for (let i = 0; i < 12; i++) {
    const tick = document.createElement("div");
    tick.className = "tick";
    
    // Target 12, 3, 6, and 9 o'clock
    if (i % 3 === 0) {
        tick.classList.add("major");
    }
    
    tick.style.transform = `rotate(${i * 30}deg)`;
    ticksContainer.appendChild(tick);
}

function update(){
    const now = new Date();

    let h = now.getHours();
    const m = now.getMinutes();
    const s = now.getSeconds();
    const ms = now.getMilliseconds(); 
    
    const ampm = h >= 12 ? 'PM' : 'AM'; 
    const displayHour = h % 12 === 0 ? 12 : h % 12;

    // Continuous smooth angle calculations
    const secondAngle = (s * 6) + (ms * 0.006);
    const minuteAngle = (m * 6) + (s * 0.1);
    const hourAngle = ((h % 12) * 30) + (m * 0.5);

    document.getElementById("hour").style.transform = `rotate(${hourAngle}deg)`;
    document.getElementById("minute").style.transform = `rotate(${minuteAngle}deg)`;
    document.getElementById("second").style.transform = `rotate(${secondAngle}deg)`;

    // Time format alignment: force hour space so layout stays identical size-wise
    const hourStr = String(displayHour).padStart(2, "0");
    const minStr = String(m).padStart(2, "0");

    document.getElementById("digital").textContent = `${hourStr}:${minStr} ${ampm}`;

    const days = ["Sun", "Mon", "Tue", "Wed", "Thu", "Fri", "Sat"];
    const months = ["Jan", "Feb", "Mar", "Apr", "May", "Jun", "Jul", "Aug", "Sep", "Oct", "Nov", "Dec"];

    document.getElementById("date").textContent = 
        days[now.getDay()] + " " + 
        months[now.getMonth()] + " " + 
        now.getDate();
        
    requestAnimationFrame(update);
}

// Kickstart animation loop
requestAnimationFrame(update);
</script>

</body>
</html>
