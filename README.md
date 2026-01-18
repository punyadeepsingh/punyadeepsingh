<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Phone Control Dashboard</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
<div class="container">
    <header class="header">
        <h1>📱 Phone Control Dashboard</h1>
        <p class="subtitle">Control your device settings from anywhere</p>
    </header>

    <main class="main-content">

        <!-- Running Tracker -->
        <section class="card">
            <h2>🏃 Running Tracker</h2>
            <div id="gpsStatus">GPS inactive</div>
            <div class="info-grid">
                <div class="info-item">
                    <span class="label">Distance:</span>
                    <span class="value" id="distance">0.00 km</span>
                </div>
                <div class="info-item">
                    <span class="label">Speed:</span>
                    <span class="value" id="speed">0.0 km/h</span>
                </div>
            </div>
            <div style="margin-top:10px;">
                <button class="control-btn" id="startRun">START RUN</button>
                <button class="control-btn" id="stopRun">STOP</button>
            </div>
        </section>

        <!-- Device Info Section -->
        <section class="card device-info-card">
            <h2>Device Information</h2>
            <div class="info-grid">
                <div class="info-item">
                    <span class="label">Device:</span>
                    <span class="value" id="deviceInfo">Detecting...</span>
                </div>
                <div class="info-item">
                    <span class="label">Battery:</span>
                    <span class="value" id="batteryLevel">Detecting...</span>
                </div>
                <div class="info-item">
                    <span class="label">Connection:</span>
                    <span class="value" id="networkStatus">Checking...</span>
                </div>
                <div class="info-item">
                    <span class="label">Orientation:</span>
                    <span class="value" id="orientation">Portrait</span>
                </div>
            </div>
            <div class="battery-bar">
                <div class="battery-fill" id="batteryFill"></div>
            </div>
        </section>

        <!-- Display Controls -->
        <section class="card">
            <h2>Display Controls</h2>
            <div class="control-group">
                <div class="control-item">
                    <label>Brightness</label>
                    <input type="range" id="brightnessSlider" min="0" max="100" value="80" class="slider">
                    <span class="value-display" id="brightnessValue">80%</span>
                </div>
                <button class="control-btn" id="toggleFlashlight">💡 Flashlight</button>
            </div>
        </section>

        <!-- Audio Controls -->
        <section class="card">
            <h2>Audio Controls</h2>
            <div class="control-group">
                <div class="control-item">
                    <label>Volume</label>
                    <input type="range" id="volumeSlider" min="0" max="100" value="70" class="slider">
                    <span class="value-display" id="volumeValue">70%</span>
                </div>
                <div class="control-item">
                    <label>Sound Mode</label>
                    <div class="mode-buttons">
                        <button class="mode-btn active" data-mode="sound">🔊 Sound</button>
                        <button class="mode-btn" data-mode="vibrate">📳 Vibrate</button>
                        <button class="mode-btn" data-mode="silent">🔇 Silent</button>
                    </div>
                </div>
            </div>
        </section>

        <!-- Device Settings -->
        <section class="card">
            <h2>Device Settings</h2>
            <div class="settings-grid">
                <div class="setting-item"><span>🌍 Airplane Mode</span><input type="checkbox" id="airplaneMode"></div>
                <div class="setting-item"><span>📶 Mobile Data</span><input type="checkbox" id="mobileData" checked></div>
                <div class="setting-item"><span>📡 WiFi</span><input type="checkbox" id="wifi" checked></div>
                <div class="setting-item"><span>🔵 Bluetooth</span><input type="checkbox" id="bluetooth"></div>
                <div class="setting-item"><span>🔒 Auto-rotate</span><input type="checkbox" id="autoRotate" checked></div>
                <div class="setting-item"><span>🌙 Dark Mode</span><input type="checkbox" id="darkMode"></div>
            </div>
        </section>

        <!-- Device Actions -->
        <section class="card">
            <h2>Device Actions</h2>
            <div class="action-buttons">
                <button class="action-btn" id="vibrateBtn">📳 Vibrate</button>
                <button class="action-btn" id="screenshotBtn">📸 Screenshot</button>
                <button class="action-btn" id="lockScreenBtn">🔐 Lock Screen</button>
            </div>
        </section>

        <!-- System Info -->
        <section class="card">
            <h2>System Information</h2>
            <div class="system-info">
                <div class="info-row"><span>Storage Used:</span><div class="storage-bar"><div id="storageFill"></div></div><span id="storageValue">0 GB</span></div>
                <div class="info-row"><span>Memory Used:</span><div class="memory-bar"><div id="memoryFill"></div></div><span id="memoryValue">0 GB</span></div>
                <div class="info-row">
                    <span>Screen Timeout:</span>
                    <select id="screenTimeout">
                        <option value="15">15 seconds</option>
                        <option value="30">30 seconds</option>
                        <option value="60" selected>1 minute</option>
                        <option value="300">5 minutes</option>
                        <option value="600">10 minutes</option>
                        <option value="1800">30 minutes</option>
                    </select>
                </div>
            </div>
        </section>

        <!-- Quick Actions -->
        <section class="card">
            <h2>Quick Actions</h2>
            <div class="quick-actions">
                <button id="callEmergency">📞 Emergency</button>
                <button id="openCamera">📷 Camera</button>
                <button id="openSettings">⚙️ Settings</button>
                <button id="openGallery">🖼️ Gallery</button>
            </div>
        </section>

    </main>

    <footer class="footer">
        <p>Tip: Refreshing the page will sync with your device's current settings</p>
        <p id="lastUpdated">Last updated: Just now</p>
    </footer>
</div>

<script src="script.js"></script>
</body>
</html>
