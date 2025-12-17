# Gift.html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Golden Ribbon Journey</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
 
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 20px;
        }
 
        .container {
            max-width: 600px;
            width: 100%;
            background: white;
            border-radius: 20px;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
            padding: 40px;
            text-align: center;
            animation: fadeIn 0.5s ease-in;
        }
 
        @keyframes fadeIn {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
 
        @keyframes slideIn {
            from {
                opacity: 0;
                transform: scale(0.9);
            }
            to {
                opacity: 1;
                transform: scale(1);
            }
        }
 
        .screen {
            display: none;
        }
 
        .screen.active {
            display: block;
            animation: slideIn 0.5s ease-out;
        }
 
        h1 {
            color: #667eea;
            font-size: 2.5em;
            margin-bottom: 20px;
        }
 
        p {
            color: #555;
            font-size: 1.2em;
            margin-bottom: 30px;
            line-height: 1.6;
        }
 
        .image-container {
            margin: 30px 0;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
            background: #f8f9fa;
            min-height: 300px;
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
        }
 
        .image-container img {
            width: 100%;
            height: auto;
            display: block;
            max-height: 500px;
            object-fit: cover;
        }
 
        .button-group {
            display: flex;
            gap: 15px;
            justify-content: center;
            flex-wrap: wrap;
            margin-top: 20px;
        }
 
        button {
            padding: 15px 40px;
            font-size: 1.1em;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            transition: all 0.3s ease;
            font-weight: bold;
            text-transform: uppercase;
            letter-spacing: 1px;
        }
 
        .btn-primary {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            box-shadow: 0 5px 15px rgba(102, 126, 234, 0.4);
        }
 
        .btn-primary:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 25px rgba(102, 126, 234, 0.6);
        }
 
        .btn-secondary {
            background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
            color: white;
            box-shadow: 0 5px 15px rgba(245, 87, 108, 0.4);
        }
 
        .btn-secondary:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 25px rgba(245, 87, 108, 0.6);
        }
 
        .btn-exit {
            background: #6c757d;
            color: white;
        }
 
        .btn-exit:hover {
            background: #5a6268;
            transform: translateY(-3px);
        }
 
        .emoji {
            font-size: 3em;
            margin-bottom: 20px;
            animation: bounce 2s infinite;
        }
 
        @keyframes bounce {
            0%, 100% {
                transform: translateY(0);
            }
            50% {
                transform: translateY(-10px);
            }
        }
 
        .final-message {
            background: linear-gradient(135deg, #ffecd2 0%, #fcb69f 100%);
            padding: 20px;
            border-radius: 15px;
            margin-top: 20px;
        }
 
        @media (max-width: 768px) {
            .container {
                padding: 20px;
            }
 
            h1 {
                font-size: 2em;
            }
 
            button {
                padding: 12px 30px;
                font-size: 1em;
            }
 
            .image-container {
                min-height: 250px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <div id="screen1" class="screen active">
            <div class="emoji">🎀</div>
            <h1>Are you ready?</h1>
            <p>Click "Next" to proceed or "Exit" if you're not ready</p>
            <div class="button-group">
                <button class="btn-primary" onclick="showScreen(2)">Next</button>
                <button class="btn-exit" onclick="exitPage()">Exit</button>
            </div>
        </div>
 
        <div id="screen2" class="screen">
            <h1>Golden Connection</h1>
            <div class="image-container">
                <img id="image1" src="" alt="First golden ribbon image">
            </div>
            <p><strong>Continue or not?</strong></p>
            <div class="button-group">
                <button class="btn-primary" onclick="showScreen(3)">Continue</button>
                <button class="btn-exit" onclick="exitPage()">Exit</button>
            </div>
        </div>
 
        <div id="screen3" class="screen">
            <h1>Together as One</h1>
            <div class="image-container">
                <img id="image2" src="" alt="Second golden ribbon image">
            </div>
            <div class="final-message">
                <p><strong>✨ Thank you for joining this journey! ✨</strong></p>
                <p>These golden ribbons symbolize the bonds that connect us all.</p>
            </div>
            <div class="button-group">
                <button class="btn-secondary" onclick="showScreen(1)">Start Over</button>
            </div>
        </div>
    </div>
 
    <script>
        function svgToDataUriBase64(svg) {
            // btoa expects Latin1; this keeps it safe for any Unicode.
            const utf8 = encodeURIComponent(svg).replace(/%([0-9A-F]{2})/g, (_, hex) => String.fromCharCode(parseInt(hex, 16)));
            return 'data:image/svg+xml;base64,' + btoa(utf8);
        }
 
        const image1SVG = svgToDataUriBase64(`
            <svg xmlns="http://www.w3.org/2000/svg" width="800" height="600" viewBox="0 0 800 600">
                <defs>
                    <linearGradient id="gold" x1="0%" y1="0%" x2="100%" y2="100%">
                        <stop offset="0%" style="stop-color:#FFD700;stop-opacity:1"/>
                        <stop offset="100%" style="stop-color:#FFA500;stop-opacity:1"/>
                    </linearGradient>
                </defs>
                <rect width="800" height="600" fill="#f8f9fa"/>
                <path d="M200,300 Q400,150 600,300 Q600,450 400,350 Q200,400 200,300Z"
                      fill="url(#gold)" stroke="#DAA520" stroke-width="3"/>
                <ellipse cx="250" cy="280" rx="40" ry="60" fill="#FFE4B5" stroke="#D2B48C" stroke-width="2"/>
                <ellipse cx="550" cy="280" rx="40" ry="60" fill="#FFE4B5" stroke="#D2B48C" stroke-width="2"/>
                <text x="400" y="100" font-family="Arial" font-size="32" fill="#667eea" text-anchor="middle">
                    Golden Ribbon Connection
                </text>
                <text x="400" y="550" font-family="Arial" font-size="18" fill="#666" text-anchor="middle">
                    Your Photo: IMG_20251217_154707_808.jpg
                </text>
            </svg>
        `);
 
        const image2SVG = svgToDataUriBase64(`
            <svg xmlns="http://www.w3.org/2000/svg" width="800" height="600" viewBox="0 0 800 600">
                <defs>
                    <linearGradient id="gold2" x1="0%" y1="0%" x2="100%" y2="100%">
                        <stop offset="0%" style="stop-color:#FFD700;stop-opacity:1"/>
                        <stop offset="100%" style="stop-color:#FFA500;stop-opacity:1"/>
                    </linearGradient>
                </defs>
                <rect width="800" height="600" fill="#f8f9fa"/>
                <path d="M150,250 Q300,150 450,250" stroke="url(#gold2)" stroke-width="15" fill="none"/>
                <path d="M250,350 Q400,250 550,350" stroke="url(#gold2)" stroke-width="15" fill="none"/>
                <path d="M200,450 Q400,350 600,450" stroke="url(#gold2)" stroke-width="15" fill="none"/>
                <ellipse cx="150" cy="250" rx="30" ry="50" fill="#FFE4B5" stroke="#D2B48C" stroke-width="2"/>
                <ellipse cx="450" cy="250" rx="30" ry="50" fill="#FFE4B5" stroke="#D2B48C" stroke-width="2"/>
                <ellipse cx="250" cy="350" rx="30" ry="50" fill="#FFE4B5" stroke="#D2B48C" stroke-width="2"/>
                <ellipse cx="550" cy="350" rx="30" ry="50" fill="#FFE4B5" stroke="#D2B48C" stroke-width="2"/>
                <ellipse cx="200" cy="450" rx="30" ry="50" fill="#FFE4B5" stroke="#D2B48C" stroke-width="2"/>
                <ellipse cx="600" cy="450" rx="30" ry="50" fill="#FFE4B5" stroke="#D2B48C" stroke-width="2"/>
                <text x="400" y="100" font-family="Arial" font-size="32" fill="#667eea" text-anchor="middle">
                    Together as One
                </text>
                <text x="400" y="550" font-family="Arial" font-size="18" fill="#666" text-anchor="middle">
                    Your Photo: IMG_20251217_154700_663.jpg
                </text>
            </svg>
        `);
 
        // Replace this with your own image URL/path for Screen 2.
        const image1Src = "https://scontent.fdvo1-2.fna.fbcdn.net/v/t1.15752-9/597886154_4405123299807526_4314329531120645535_n.jpg?_nc_cat=101&ccb=1-7&_nc_sid=9f807c&_nc_eui2=AeHf0jt6ZLcPj0eQE3R57TcI02fjj6vHFO_TZ-OPq8cU75NDo4Q3E7P9NDuv2rGff28eXwrgaTiYCi8WG4prvOCl&_nc_ohc=WlHMtuvzypQQ7kNvwG7ityj&_nc_oc=Adkw8Ua64tbJzOgIiJBcF3Sk3ikWyRUx5BQiUIZjt_4KbKioAsStnfau1xhnXLAszPM&_nc_zt=23&_nc_ht=scontent.fdvo1-2.fna&oh=03_Q7cD4AEN66VO4U5wha0_vpomk1ZNYgeo1ImifOekasqbFaktYw&oe=696A1FD2";
 
        // Replace this with your own image URL/path for Screen 3.
        // Example (local): "images/photo2.jpg"
        // Example (web): "https://example.com/photo2.jpg"
        // Leave empty ("") to keep using the built-in SVG placeholder.
        const image2Src = "https://scontent.fdvo1-2.fna.fbcdn.net/v/t1.15752-9/597865760_1489696343163751_1049266288994909989_n.jpg?_nc_cat=100&ccb=1-7&_nc_sid=9f807c&_nc_eui2=AeHLTr_w1iAgrz57T2iCsRs48stfwBs8Tiryy1_AGzxOKimTXW9949TXJqEcmhhzhnXbvqxTuEQfW7Pyt0YL6HNq&_nc_ohc=9e_WVAb-QegQ7kNvwGMYFsc&_nc_oc=AdnegrfRGVt3yS3aSWHNSQ8waL_SV1hjR4bFmhaTQuZKO0HBA6_rR8bhogDHhJ8fMmg&_nc_zt=23&_nc_ht=scontent.fdvo1-2.fna&oh=03_Q7cD4AHZrpV2Lvt7Kim7mekdSzlPWkY_HBwAmYFwRbLdcEI7lA&oe=696A079D";
 
        function showScreen(screenNumber) {
            document.querySelectorAll('.screen').forEach(screen => {
                screen.classList.remove('active');
            });
 
            document.getElementById('screen' + screenNumber).classList.add('active');
 
            if (screenNumber === 2) {
                document.getElementById('image1').src = image1Src;
            } else if (screenNumber === 3) {
                document.getElementById('image2').src = image2Src || image2SVG;
            }
        }
 
        function exitPage() {
            if (confirm('Are you sure you want to exit?')) {
                document.body.innerHTML = `
                    <div style="
                        display: flex;
                        align-items: center;
                        justify-content: center;
                        min-height: 100vh;
                        background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
                        color: white;
                        font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
                        text-align: center;
                        padding: 20px;
                    ">
                        <div>
                            <h1 style="font-size: 3em; margin-bottom: 20px;">👋</h1>
                            <h2 style="font-size: 2em; margin-bottom: 10px;">Goodbye!</h2>
                            <p style="font-size: 1.2em;">Come back when you're ready.</p>
                        </div>
                    </div>
                `;
            }
        }
 
        window.addEventListener('DOMContentLoaded', function() {
            const img1 = new Image();
            img1.src = image1Src;
 
            const img2 = new Image();
            img2.src = image2Src || image2SVG;
        });
    </script>
</body>
</html>
