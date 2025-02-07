<!DOCTYPE html>
<html lang="hu">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Wall of Boredom</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="container">
        <header>
            <h1>Wall of Boredom</h1>
            <button class="upload-btn">Kép Feltöltése</button>
        </header>
        <main>
            <div class="wall">
                <!-- Itt jelennek meg a képek -->
            </div>
        </main>
        <footer>
            <p>© 2025 Wall of Boredom</p>
        </footer>
    </div>
    <script src="script.js"></script>
</body>
</html>
CSS (style.css)
css
Másolás
Szerkesztés
body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
    background-color: #f1f1f1;
}

.container {
    width: 100%;
    max-width: 1200px;
    margin: 0 auto;
    padding: 20px;
}

header {
    background-color: #fff;
    padding: 20px;
    text-align: center;
}

header h1 {
    color: #0080ff;
}

.upload-btn {
    background-color: #0080ff;
    color: white;
    padding: 10px 20px;
    border: none;
    cursor: pointer;
    font-size: 16px;
}

.upload-btn:hover {
    background-color: #005f99;
}

.wall {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
    margin-top: 20px;
    background-color: white;
    padding: 20px;
    border-radius: 10px;
}

.wall img {
    width: 200px;
    height: 200px;
    object-fit: cover;
    border-radius: 10px;
    cursor: pointer;
}

footer {
    text-align: center;
    margin-top: 40px;
}
JavaScript (script.js)
javascript
Másolás
Szerkesztés
const wall = document.querySelector('.wall');
const uploadBtn = document.querySelector('.upload-btn');

// Példa képek (ezeket később lehet dinamikusan feltölteni)
let images = [
    'image1.jpg',
    'image2.jpg',
    'image3.jpg'
];

// Képek megjelenítése a falon
function renderWall() {
    wall.innerHTML = ''; // Kiürítjük a falat
    images.forEach(image => {
        const imgElement = document.createElement('img');
        imgElement.src = image;
        imgElement.alt = "Random Image";
        imgElement.onclick = () => alert("Tetszik ez a kép!");
        wall.appendChild(imgElement);
    });
}

// Kép feltöltésének alap logikája
uploadBtn.onclick = () => {
    const imageUrl = prompt("Add meg a kép URL-jét:");
    if (imageUrl) {
        images.push(imageUrl); // Hozzáadjuk a képet a listához
        renderWall(); // Újra rendereljük a falat
    }
};

// Inicializáljuk a falat
renderWall();
