# DuaMate1
From Emotion To Devotion
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>DuaMate - Your Spiritual Companion</title>

<style>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}

body {
    background: linear-gradient(135deg, #ffe6f2, #ffd6ec);
    min-height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 20px;
}

.container {
    background: white;
    width: 100%;
    max-width: 700px;
    padding: 30px;
    border-radius: 20px;
    box-shadow: 0 10px 30px rgba(255, 79, 160, 0.15);
}

/* Header & Live Clock */
header {
    text-align: center;
    margin-bottom: 25px;
}

h1 {
    color: #ff4fa0;
    font-size: 2.5rem;
    margin-bottom: 5px;
}

.subtitle {
    color: #666;
    font-size: 1rem;
    margin-bottom: 15px;
}

.datetime-container {
    background: #fff0f7;
    padding: 10px;
    border-radius: 12px;
    display: inline-block;
    color: #ff2f8f;
    font-weight: bold;
    font-size: 0.9rem;
    border: 1px dashed #ffb3d9;
}

/* Navigation Bar */
nav {
    display: flex;
    justify-content: space-around;
    background: #fff0f7;
    padding: 10px;
    border-radius: 12px;
    margin-bottom: 25px;
}

nav button {
    background: none;
    border: none;
    color: #ff4fa0;
    font-size: 1rem;
    font-weight: 600;
    cursor: pointer;
    padding: 8px 16px;
    border-radius: 8px;
    transition: all 0.3s ease;
}

nav button.active, nav button:hover {
    background: #ff4fa0;
    color: white;
}

/* Page Content (Tabs) */
.page {
    display: none;
    animation: fadeIn 0.5s ease;
}

.page.active {
    display: block;
}

@keyframes fadeIn {
    from { opacity: 0; transform: translateY(10px); }
    to { opacity: 1; transform: translateY(0); }
}

/* Form & UI Elements */
label {
    font-weight: bold;
    color: #444;
    display: block;
    margin-bottom: 8px;
}

select {
    width: 100%;
    padding: 12px;
    border-radius: 10px;
    border: 2px solid pink;
    font-size: 16px;
    outline: none;
    transition: border-color 0.3s;
}

select:focus {
    border-color: #ff4fa0;
}

.primary-btn {
    margin-top: 15px;
    width: 100%;
    padding: 12px;
    border: none;
    background: #ff4fa0;
    color: white;
    font-size: 17px;
    border-radius: 10px;
    cursor: pointer;
    font-weight: bold;
    transition: background 0.3s;
}

.primary-btn:hover {
    background: #ff2f8f;
}

.clear-btn {
    background: #ffccd5;
    color: #d9383a;
    margin-top: 15px;
}

.clear-btn:hover {
    background: #ffb3c1;
}

/* Cards */
.card {
    margin-top: 20px;
    padding: 20px;
    background: #fff0f7;
    border-radius: 15px;
    border-left: 5px solid #ff4fa0;
}

.card h2 {
    color: #ff4fa0;
    margin-bottom: 12px;
    font-size: 1.3rem;
}

#doa, #dailyDua {
    font-size: 16px;
    line-height: 1.7;
    color: #333;
    white-space: pre-line;
}

/* History List */
.history-list {
    list-style: none;
    margin-top: 10px;
}

.history-item {
    background: #fff0f7;
    padding: 12px 15px;
    border-radius: 10px;
    margin-bottom: 10px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    border-left: 4px solid #ffb3d9;
}

.history-emotion {
    font-weight: bold;
    color: #ff4fa0;
}

.history-time {
    font-size: 0.85rem;
    color: #777;
}

/* Footer */
footer {
    margin-top: 30px;
    text-align: center;
    color: gray;
    font-size: 14px;
}
</style>
</head>
<body>

<div class="container">
    <header>
        <h1>🌸 DuaMate</h1>
        <p class="subtitle">Find comfort through duas based on your emotions.</p>
        <div class="datetime-container">
            📅 <span id="live-date">Loading date...</span> | 🕒 <span id="live-time">Loading time...</span>
        </div>
    </header>

    <!-- Navigation Bar untuk tukar "Page" -->
    <nav>
        <button class="nav-btn active" onclick="switchPage('home')">🏠 Home</button>
        <button class="nav-btn" onclick="switchPage('emotion-page')">😊 Emotion</button>
        <button class="nav-btn" onclick="switchPage('dua-page')">🌼 Dua of the Day</button>
        <button class="nav-btn" onclick="switchPage('history-page')">📝 History</button>
    </nav>

    <!-- 1. HOME PAGE -->
    <div id="home" class="page active">
        <div class="card" style="border-left: 5px solid #ff2f8f; text-align: center;">
            <h2>Welcome to DuaMate 🤍</h2>
            <p style="color: #555; margin-bottom: 15px;">Your small sanctuary to seek calmness and connect to Allah through beautiful duas tailored to what your heart feels today.</p>
            <button class="primary-btn" onclick="switchPage('emotion-page')">Start Sharing Your Emotion ✨</button>
        </div>
    </div>

    <!-- 2. EMOTION PAGE -->
    <div id="emotion-page" class="page">
        <label for="emotion">How are you feeling right now?</label>
        <select id="emotion">
            <option value="">-- Choose Emotion --</option>
            <option>Happy 😊</option>
            <option>Sad 😢</option>
            <option>Anxious 😟</option>
            <option>Angry 😠</option>
            <option>Grateful 🤍</option>
            <option>Stressed 😫</option>
            <option>Lonely 🥺</option>
            <option>Confused 😕</option>
        </select>

        <button class="primary-btn" onclick="showDua()">Get My Dua</button>

        <div class="card">
            <h2>Suggested Dua</h2>
            <p id="doa">Choose your emotion first above to receive a suitable dua.</p>
        </div>
    </div>

    <!-- 3. DUA OF THE DAY PAGE -->
    <div id="dua-page" class="page">
        <div class="card">
            <h2>🌼 Today's Special Dua</h2>
            <p id="dailyDua">Loading your dua of the day...</p>
        </div>
    </div>

    <!-- 4. HISTORY PAGE -->
    <div id="history-page" class="page">
        <h2>📝 Your Emotion History</h2>
        <p style="color: #777; font-size: 0.9rem; margin-bottom: 10px;">Track your past emotions and the exact time you sought comfort.</p>
        
        <ul id="historyList" class="history-list">
            <!-- History items will be injected here -->
        </ul>
        
        <button class="primary-btn clear-btn" onclick="clearHistory()">Clear History</button>
    </div>

    <footer>
        Made with ❤️ by DuaMate
    </footer>
</div>

<script>
// Database Doa
const duas = {
    "Happy 😊": "Alhamdulillahi Rabbil 'Alamin.\n\nMeaning: All praise belongs to Allah.",
    "Sad 😢": "Hasbunallahu wa ni'mal wakeel.\n\nMeaning: Allah is sufficient for us and He is the best disposer of affairs.",
    "Anxious 😟": "Allahumma inni a'udhu bika minal hammi wal hazan.\n\nMeaning: O Allah, I seek refuge in You from anxiety and sorrow.",
    "Angry 😠": "A'udhu billahi minash shaitanir rajim.\n\nMeaning: I seek refuge in Allah from Satan.",
    "Grateful 🤍": "Allahumma a'inni 'ala zikrika wa syukrika wa husni ibadatik.\n\nMeaning: O Allah, help me remember You and thank You.",
    "Stressed 😫": "La hawla wa la quwwata illa billah.\n\nMeaning: There is no power except with Allah.",
    "Lonely 🥺": "Rabbi inni lima anzalta ilayya min khairin faqir.\n\nMeaning: My Lord, I am truly in need of whatever good You send me.",
    "Confused 😕": "Rabbi zidni ilma.\n\nMeaning: My Lord, increase me in knowledge."
};

const dailyDuas = [
    "Rabbi yassir wa la tu'assir wa tammim bil khair.\n\nMeaning: My Lord, make things easy for me and do not make them difficult, and complete them with goodness.",
    "Allahumma inni as'aluka al-afiyah.\n\nMeaning: O Allah, I ask You for well-being in this world and the next.",
    "Rabbana atina fid dunya hasanah wa fil akhirati hasanah.\n\nMeaning: Our Lord, give us in this world that which is good and in the Hereafter that which is good.",
    "Allahumma mutahhir al-qulub.\n\nMeaning: O Allah, Purifier of hearts, make our hearts firm on Your religion."
];

// 1. Live Date & Time Counter
function updateClock() {
    const now = new Date();
    
    // Format Tarikh
    const options = { weekday: 'long', year: 'numeric', month: 'long', day: 'numeric' };
    document.getElementById("live-date").innerText = now.toLocaleDateString('en-US', options);
    
    // Format Masa (Live)
    document.getElementById("live-time").innerText = now.toLocaleTimeString('en-US');
}
setInterval(updateClock, 1000);
updateClock();

// 2. Fungsi Tukar Halaman (Tab Navigation)
function switchPage(pageId) {
    // Sembunyikan semua page
    const pages = document.querySelectorAll('.page');
    pages.forEach(page => page.classList.remove('active'));
    
    // Paparkan page yang dipilih
    document.getElementById(pageId).classList.add('active');
    
    // Tukar status button active di navbar
    const buttons = document.querySelectorAll('.nav-btn');
    buttons.forEach(btn => btn.classList.remove('active'));
    
    // Cari button mana yang ditekan dan set jadi active
    event.currentTarget.classList.add('active');
}

// 3. Papar Doa & Simpan History Beserta Tarikh & Masa
function showDua() {
    const emotion = document.getElementById("emotion").value;
    
    if (emotion == "") {
        alert("Please choose an emotion first!");
        return;
    }
    
    // Papar doa
    document.getElementById("doa").innerText = duas[emotion];
    
    // Ambil masa & tarikh semasa butang ditekan
    const now = new Date();
    const dateStr = now.toLocaleDateString('en-GB'); // Contoh: 03/07/2026
    const timeStr = now.toLocaleTimeString('en-US', { hour: '2-digit', minute: '2-digit' }); // Contoh: 09:30 PM
    const exactTimestamp = `${dateStr} @ ${timeStr}`;
    
    saveHistory(emotion, exactTimestamp);
}

// 4. Pengurusan Local Storage untuk History
function saveHistory(emotion, timestamp) {
    let history = JSON.parse(localStorage.getItem("duamate_history")) || [];
    
    // Simpan objek yang mengandungi nama emosi dan masa
    history.unshift({ emotion: emotion, time: timestamp });
    
    localStorage.setItem("duamate_history", JSON.stringify(history));
    displayHistory();
}

function displayHistory() {
    let history = JSON.parse(localStorage.getItem("duamate_history")) || [];
    let list = document.getElementById("historyList");
    
    list.innerHTML = "";
    
    if (history.length === 0) {
        list.innerHTML = `<li style='color:#999; text-align:center; padding: 20px;'>No history found. Try selecting an emotion!</li>`;
        return;
    }
    
    history.forEach(item => {
        let li = document.createElement("li");
        li.className = "history-item";
        li.innerHTML = `
            <span class="history-emotion">${item.emotion}</span>
            <span class="history-time">📅 ${item.time}</span>
        `;
        list.appendChild(li);
    });
}

function clearHistory() {
    if (confirm("Are you sure you want to clear your emotion history?")) {
        localStorage.removeItem("duamate_history");
        displayHistory();
    }
}

// 5. Dua of the Day (Berubah mengikut hari bulan)
function setupDailyDua() {
    let today = new Date();
    let index = today.getDate() % dailyDuas.length;
    document.getElementById("dailyDua").innerText = dailyDuas[index];
}

// Run functions on load
displayHistory();
setupDailyDua();
</script>

</body>
</html>
