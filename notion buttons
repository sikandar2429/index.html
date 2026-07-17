<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1">
<title>Aesthetic Button Bar</title>
<style>
* {
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
    background: #191919; /* Warm off-black background */
    overflow: hidden;
    user-select: none;
}

/* Flex container to keep all buttons in one horizontal line */
.button-container {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: center;
    gap: 16px; /* Spacing between the buttons */
    flex-wrap: nowrap; /* Prevents them from breaking onto a new line */
}

/* Aesthetic capsule-shaped button style */
.button-link {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 10px;
    padding: 10px 24px;
    background: transparent;
    border: 1px solid #1c3d2d; /* Subtle dark green border */
    border-radius: 50px; /* Perfect pill shape */
    text-decoration: none;
    transition: all 0.2s ease-in-out;
    cursor: pointer;
}

/* Icons styling */
.icon-svg {
    width: 28px;
    height: 28px;
    display: block;
}

.youtube-icon {
    width: 28px;
    height: auto;
}

.examside-icon {
    font-family: 'Courier New', Courier, monospace;
    font-size: 15px;
    font-weight: bold;
    color: #ffffff;
    background: #0073e6; /* Bright blue for ExamSide branding */
    border-radius: 50%;
    width: 26px;
    height: 26px;
    display: flex;
    align-items: center;
    justify-content: center;
}

/* Elegant text formatting matching the system monospace font stack */
.button-text {
    font-family: 'Courier New', Courier, monospace;
    font-size: 18px;
    color: #ffffff;
    letter-spacing: 0.5px;
    white-space: nowrap;
}

/* Gentle interactive glow hover state */
.button-link:hover {
    background: rgba(77, 171, 122, 0.05); /* Very light green tint */
    border-color: #4DAB7A; /* Illuminates the clock's primary green */
    box-shadow: 0 0 12px rgba(77, 171, 122, 0.15);
}
</style>
</head>
<body>

<div class="button-container">

    <!-- 1. YouTube Button -->
    <a href="https://www.youtube.com" target="_blank" class="button-link">
        <svg class="youtube-icon" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path fill-rule="evenodd" clip-rule="evenodd" d="M23.498 6.163a3.003 3.003 0 0 0-2.11-2.11C19.517 3.545 12 3.545 12 3.545s-7.516 0-9.387.507a3.003 3.003 0 0 0-2.11 2.11C0 8.033 0 12 0 12s0 3.967.502 5.837a3.003 3.003 0 0 0 2.11 2.11c1.871.507 9.388.507 9.388.507s7.516 0 9.387-.507a3.003 3.003 0 0 0 2.11-2.11C24 15.967 24 12 24 12s0-3.967-.502-5.837z" fill="#FF0000"/>
            <path d="M9.545 8.668V15.332L15.364 12L9.545 8.668Z" fill="white"/>
        </svg>
        <span class="button-text">Youtube</span>
    </a>

    <!-- 2. PW Button (Official Icon with Full Name) -->
    <a href="https://www.pw.live" target="_blank" class="button-link">
        <svg class="icon-svg" viewBox="0 0 100 100" xmlns="http://www.w3.org/2000/svg">
            <!-- Official Solid Black Circle Base -->
            <circle cx="50" cy="50" r="48" fill="#0D0D0D"/>
            <!-- Perfectly proportioned bold brand typeface rendering -->
            <text x="49" y="62" 
                  font-family="-apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif" 
                  font-size="36" 
                  font-weight="900" 
                  fill="#FFFFFF" 
                  text-anchor="middle" 
                  letter-spacing="-1.5px">PW</text>
        </svg>
        <span class="button-text">Physics Wallah</span>
    </a>

    <!-- 3. ExamSide Button -->
    <a href="https://examside.com" target="_blank" class="button-link">
        <div class="examside-icon">ES</div>
        <span class="button-text">ExamSide</span>
    </a>

</div>

</body>
</html>
