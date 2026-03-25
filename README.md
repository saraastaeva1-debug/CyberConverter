[my-site (9).html](https://github.com/user-attachments/files/26244885/my-site.9.html)
<html lang="ru"><head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Web2APK CyberConverter</title>
    <link href="https://fonts.googleapis.com/css2?family=Roboto+Mono:wght@400;700&amp;family=Orbitron:wght@400;700&amp;display=swap" rel="stylesheet">
    <style>
        /* Neon Cyberpunk Theme */
        :root {
            --bg-dark: #0a0a0f;
            --neon-blue: #00e5ff;
            --neon-pink: #ff0099;
            --neon-green: #39ff14;
            --text-light: #e0e0e0;
            --border-glow: rgba(0, 229, 255, 0.7);
            --gradient-primary: linear-gradient(45deg, var(--neon-blue), var(--neon-pink));
            --gradient-secondary: linear-gradient(135deg, var(--neon-green), var(--neon-blue));
            --font-primary: 'Roboto Mono', monospace;
            --font-heading: 'Orbitron', sans-serif;
            --shadow-glow: 0 0 10px var(--neon-blue), 0 0 20px var(--neon-blue), 0 0 30px var(--neon-pink);
        }

        body {
            font-family: var(--font-primary);
            background-color: var(--bg-dark);
            color: var(--text-light);
            margin: 0;
            padding: 0;
            display: flex;
            flex-direction: column;
            min-height: 100vh;
            justify-content: center;
            align-items: center;
            overflow-x: hidden;
            position: relative;
            background-image: url('data:image/svg+xml;utf8,<svg width="100%" height="100%" xmlns="http://www.w3.org/2000/svg"><defs><pattern id="grid" width="20" height="20" patternUnits="userSpaceOnUse"><path d="M 20 0 L 0 0 0 20" fill="none" stroke="%231a1a2a" stroke-width="1"/></pattern></defs><rect width="100%" height="100%" fill="url(%23grid)" /></svg>');
        }

        body::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle at center, rgba(0, 229, 255, 0.1) 0%, rgba(0, 229, 255, 0) 70%),
                        radial-gradient(circle at top right, rgba(255, 0, 153, 0.08) 0%, rgba(255, 0, 153, 0) 60%),
                        radial-gradient(circle at bottom left, rgba(57, 255, 20, 0.06) 0%, rgba(57, 255, 20, 0) 50%);
            pointer-events: none;
            z-index: -1;
        }

        .container {
            background-color: #1a1a2a;
            border: 2px solid var(--neon-blue);
            box-shadow: var(--shadow-glow);
            border-radius: 10px;
            padding: 40px;
            margin: 20px;
            width: clamp(300px, 90%, 800px);
            box-sizing: border-box;
            position: relative;
            overflow: hidden;
            z-index: 1;
        }

        .container::before {
            content: '';
            position: absolute;
            top: -2px;
            left: -2px;
            right: -2px;
            bottom: -2px;
            background: linear-gradient(45deg, var(--neon-blue), var(--neon-pink), var(--neon-green), var(--neon-blue));
            z-index: -1;
            filter: blur(8px);
            opacity: 0.6;
            animation: borderGlow 6s linear infinite alternate;
        }

        @keyframes borderGlow {
            0% { transform: scale(1.02) rotate(0deg); opacity: 0.6; }
            50% { transform: scale(1.02) rotate(180deg); opacity: 0.8; }
            100% { transform: scale(1.02) rotate(360deg); opacity: 0.6; }
        }

        header {
            text-align: center;
            margin-bottom: 40px;
        }

        header h1 {
            font-family: var(--font-heading);
            color: var(--neon-green);
            text-shadow: 0 0 15px var(--neon-green), 0 0 25px rgba(57, 255, 20, 0.6);
            margin-bottom: 10px;
            font-size: 2.8em;
            letter-spacing: 2px;
            animation: pulseText 2s infinite alternate;
        }

        @keyframes pulseText {
            0% { transform: scale(1); opacity: 0.9; }
            100% { transform: scale(1.02); opacity: 1; }
        }

        header p {
            color: var(--neon-blue);
            font-style: italic;
            text-shadow: 0 0 5px var(--neon-blue);
            font-size: 1.1em;
        }

        .form-section {
            display: grid;
            gap: 25px;
            margin-bottom: 30px;
        }

        .form-group {
            position: relative;
        }

        label {
            display: block;
            margin-bottom: 8px;
            color: var(--neon-pink);
            font-weight: bold;
            text-shadow: 0 0 3px var(--neon-pink);
        }

        input[type="text"],
        input[type="url"],
        textarea {
            width: 100%;
            padding: 12px 15px;
            background-color: #0c0c12;
            border: 1px solid var(--neon-blue);
            border-radius: 5px;
            color: var(--text-light);
            font-family: var(--font-primary);
            font-size: 1em;
            box-shadow: inset 0 0 5px rgba(0, 229, 255, 0.3);
            transition: all 0.3s ease;
        }

        input[type="text"]:focus,
        input[type="url"]:focus,
        textarea:focus {
            outline: none;
            border-color: var(--neon-pink);
            box-shadow: 0 0 8px var(--neon-pink);
            background-color: #15151f;
        }

        input[type="file"] {
            display: none;
        }

        .file-upload-label {
            display: inline-block;
            background: var(--gradient-primary);
            color: var(--bg-dark);
            padding: 10px 20px;
            border-radius: 5px;
            cursor: pointer;
            transition: all 0.3s ease;
            font-weight: bold;
            text-shadow: none;
            box-shadow: 0 0 10px rgba(0, 229, 255, 0.5);
        }

        .file-upload-label:hover {
            box-shadow: 0 0 15px var(--neon-pink), 0 0 25px var(--neon-blue);
            transform: translateY(-2px);
        }

        .ai-image-wrapper {
            display: flex;
            flex-direction: column;
            align-items: center;
            text-align: center;
        }

        .ai-image {
            width: 150px;
            height: 150px;
            background-color: #333; /* Placeholder background */
            border: 2px dashed var(--neon-green);
            border-radius: 10px;
            margin-top: 10px;
            display: flex;
            justify-content: center;
            align-items: center;
            color: var(--neon-green);
            font-size: 0.9em;
            text-shadow: 0 0 5px var(--neon-green);
            overflow: hidden;
            word-break: break-word; /* Allow long prompts to wrap */
            padding: 10px; /* Padding for prompt text */
            background-size: cover; /* For uploaded image */
            background-position: center; /* For uploaded image */
            box-sizing: border-box; /* Include padding in dimensions */
        }
        .ai-image:empty:before { /* Only show prompt if src is empty */
            content: attr(data-prompt);
        }
        .ai-image:not([src=""]):before { /* Hide prompt if src is set */
            content: none;
        }


        .options-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin-top: 20px;
        }

        .checkbox-group {
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .checkbox-group input[type="checkbox"] {
            appearance: none;
            width: 20px;
            height: 20px;
            border: 2px solid var(--neon-blue);
            border-radius: 3px;
            background-color: #0c0c12;
            cursor: pointer;
            position: relative;
            flex-shrink: 0;
            transition: all 0.2s ease;
        }

        .checkbox-group input[type="checkbox"]:checked {
            background-color: var(--neon-green);
            border-color: var(--neon-green);
            box-shadow: 0 0 8px var(--neon-green);
        }

        .checkbox-group input[type="checkbox"]:checked::after {
            content: '✓';
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            color: var(--bg-dark);
            font-size: 1.2em;
            font-weight: bold;
        }
        .checkbox-group label {
             margin-bottom: 0;
             cursor: pointer;
             color: var(--text-light);
             text-shadow: none;
        }

        button {
            display: block;
            width: 100%;
            padding: 15px 25px;
            margin-top: 30px;
            background: var(--gradient-secondary);
            color: var(--bg-dark);
            border: none;
            border-radius: 8px;
            font-family: var(--font-heading);
            font-size: 1.3em;
            font-weight: bold;
            cursor: pointer;
            text-transform: uppercase;
            letter-spacing: 1px;
            box-shadow: 0 0 15px var(--neon-green), 0 0 25px var(--neon-blue);
            transition: all 0.3s ease;
        }

        button:hover {
            transform: translateY(-3px);
            box-shadow: 0 0 20px var(--neon-green), 0 0 35px var(--neon-blue), 0 0 50px var(--neon-pink);
            filter: brightness(1.1);
        }

        .status-area {
            margin-top: 30px;
            padding: 20px;
            background-color: #1a1a2a;
            border: 1px dashed var(--neon-pink);
            border-radius: 8px;
            min-height: 80px;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: flex-start;
            color: var(--neon-pink);
            font-size: 0.95em;
            box-shadow: inset 0 0 8px rgba(255, 0, 153, 0.4);
        }

        .status-area p {
            margin: 5px 0;
            line-height: 1.4;
        }

        .status-area .progress-bar {
            width: 0%;
            height: 8px;
            background: var(--gradient-primary);
            border-radius: 4px;
            margin-top: 10px;
            transition: width 0.5s ease-in-out;
            box-shadow: 0 0 10px var(--neon-blue);
        }

        .download-link {
            display: block;
            text-align: center;
            margin-top: 20px;
        }

        .download-link a {
            color: var(--neon-green);
            text-decoration: none;
            font-weight: bold;
            text-shadow: 0 0 5px var(--neon-green);
            transition: all 0.2s ease;
            font-size: 1.1em;
        }

        .download-link a:hover {
            color: var(--neon-pink);
            text-shadow: 0 0 8px var(--neon-pink);
            transform: translateY(-1px);
        }

        footer {
            margin-top: 40px;
            text-align: center;
            color: #777;
            font-size: 0.85em;
            padding-bottom: 20px;
        }
        footer p {
            color: var(--text-light);
        }
        footer a {
            color: var(--neon-blue);
            text-decoration: none;
            text-shadow: 0 0 3px var(--neon-blue);
        }
        footer a:hover {
            text-decoration: underline;
            color: var(--neon-pink);
            text-shadow: 0 0 5px var(--neon-pink);
        }

        /* Glitch effect for hover elements */
        .glitch-text:hover {
            animation: glitch 0.5s cubic-bezier(0.25, 0.46, 0.45, 0.94) both infinite;
        }

        @keyframes glitch {
            0% {
                transform: translate(0);
            }
            20% {
                transform: translate(-2px, 2px);
            }
            40% {
                transform: translate(-2px, -2px);
            }
            60% {
                transform: translate(2px, 2px);
            }
            80% {
                transform: translate(2px, -2px);
            }
            100% {
                transform: translate(0);
            }
        }

        /* Responsive adjustments */
        @media (max-width: 768px) {
            header h1 {
                font-size: 2em;
            }
            .container {
                padding: 25px;
            }
            .options-grid {
                grid-template-columns: 1fr;
            }
            .ai-image {
                width: 120px;
                height: 120px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <h1 class="glitch-text">Web2APK CyberConverter</h1>
            <p>Ваш портал в мобильное будущее: Превратите любую веб-страницу в полноценное Android приложение!</p>
        </header>

        <main>
            <section class="form-section">
                <div class="form-group">
                    <label for="website-url">URL веб-сайта для конвертации:</label>
                    <input type="url" id="website-url" placeholder="https://example.com" required="">
                </div>

                <div class="form-group">
                    <label for="app-name">Название APK-файла (имя приложения):</label>
                    <input type="text" id="app-name" placeholder="Мое Веб-Приложение" required="">
                </div>

                <div class="options-grid">
                    <div class="form-group">
                        <label for="app-icon">Иконка приложения:</label>
                        <div class="ai-image-wrapper">
                            <input type="file" id="app-icon" accept="image/*">
                            <label for="app-icon" class="file-upload-label">Выбрать иконку</label>
                            <img src="" alt="App Icon Preview" class="ai-image" data-prompt="futuristic neon app icon, abstract, cybernetic, glowing blue and pink, 1:1 aspect ratio">
                            <small>Рекомендуемый размер: 512x512px</small>
                        </div>
                    </div>

                    <div class="form-group">
                        <label for="splash-screen">Заставка (Splash Screen):</label>
                        <div class="ai-image-wrapper">
                            <input type="file" id="splash-screen" accept="image/*">
                            <label for="splash-screen" class="file-upload-label">Выбрать заставку</label>
                            <img src="" alt="Splash Screen Preview" class="ai-image" data-prompt="cyberpunk city landscape, neon lights, dark background, futuristic, high-tech, wide aspect ratio">
                            <small>Появится при запуске приложения</small>
                        </div>
                    </div>
                </div>

                <div class="options-grid">
                    <div class="checkbox-group">
                        <input type="checkbox" id="enable-js">
                        <label for="enable-js">Включить JavaScript</label>
                    </div>
                    <div class="checkbox-group">
                        <input type="checkbox" id="offline-mode">
                        <label for="offline-mode">Оффлайн-режим (кэширование)</label>
                    </div>
                    <div class="checkbox-group">
                        <input type="checkbox" id="fullscreen" checked="">
                        <label for="fullscreen">Полноэкранный режим</label>
                    </div>
                    <div class="checkbox-group">
                        <input type="checkbox" id="orientation-lock">
                        <label for="orientation-lock">Блокировка ориентации (Портретная)</label>
                    </div>
                </div>
            </section>

            <button id="generate-apk-btn" class="glitch-text">СГЕНЕРИРОВАТЬ APK-ФАЙЛ</button>

            <section class="status-area">
                <p><strong>Статус:</strong> Ожидание URL...</p>
                <div class="progress-bar" style="width: 0%;"></div>
            </section>

            <section class="download-link" style="display: none;">
                <p>Ваш APK готов! <a href="#" id="download-apk">СКАЧАТЬ WebApp.apk</a></p>
            </section>
        </main>

        <footer>
            <p>© 2077 CyberConverter. Все права защищены. <a href="#">Политика конфиденциальности</a></p>
        </footer>
    </div>

    <script>
        // JavaScript for interactivity and simulated APK generation
        document.addEventListener('DOMContentLoaded', () => {
            const generateBtn = document.getElementById('generate-apk-btn');
            const websiteUrlInput = document.getElementById('website-url');
            const appNameInput = document.getElementById('app-name');
            const statusArea = document.querySelector('.status-area');
            const progressBar = statusArea.querySelector('.progress-bar');
            const downloadLinkSection = document.querySelector('.download-link');
            const downloadApkLink = document.getElementById('download-apk');
            const appIconInput = document.getElementById('app-icon');
            const appIconImg = document.querySelector('.ai-image[data-prompt*="app icon"]');
            const splashScreenInput = document.getElementById('splash-screen');
            const splashScreenImg = document.querySelector('.ai-image[data-prompt*="splash screen"]');

            function updateStatus(message, progress = 0, isError = false) {
                statusArea.innerHTML = `<p><strong>Статус:</strong> ${message}</p><div class="progress-bar" style="width: ${progress}%;"></div>`;
                if (isError) {
                    statusArea.style.borderColor = '#ff3333'; /* Error red */
                    statusArea.style.boxShadow = 'inset 0 0 8px rgba(255, 51, 51, 0.4)';
                    statusArea.style.color = '#ff3333';
                } else {
                    statusArea.style.borderColor = 'var(--neon-pink)';
                    statusArea.style.boxShadow = 'inset 0 0 8px rgba(255, 0, 153, 0.4)';
                    statusArea.style.color = 'var(--neon-pink)';
                }
                progressBar.style.width = `${progress}%`;
                downloadLinkSection.style.display = 'none';
            }

            function handleFileUpload(inputElement, imgElement) {
                inputElement.addEventListener('change', (event) => {
                    const file = event.target.files[0];
                    if (file) {
                        const reader = new FileReader();
                        reader.onload = (e) => {
                            imgElement.src = e.target.result;
                            imgElement.style.backgroundImage = `url(${e.target.result})`;
                            imgElement.style.backgroundSize = 'cover';
                            imgElement.style.backgroundPosition = 'center';
                            imgElement.textContent = ''; // Clear prompt text
                        };
                        reader.readAsDataURL(file);
                    } else {
                        imgElement.src = '';
                        imgElement.style.backgroundImage = 'none'; // Clear uploaded image
                        // CSS will automatically re-add the content: attr(data-prompt) if src is empty
                    }
                });
            }

            // Initialize image previews to show data-prompt text if src is empty
            document.querySelectorAll('.ai-image').forEach(img => {
                if (!img.src) {
                    // The CSS pseudo-element handles showing the prompt text
                    // We just need to make sure the img element itself is empty
                    img.src = ""; // Ensure src is explicitly empty if it's not set
                }
            });

            handleFileUpload(appIconInput, appIconImg);
            handleFileUpload(splashScreenInput, splashScreenImg);

            generateBtn.addEventListener('click', () => {
                const websiteUrl = websiteUrlInput.value.trim();
                const appName = appNameInput.value.trim();

                if (!websiteUrl) {
                    updateStatus('Ошибка: Пожалуйста, введите URL веб-сайта.', 0, true);
                    return;
                }
                if (!appName) {
                    updateStatus('Ошибка: Пожалуйста, введите название приложения.', 0, true);
                    return;
                }

                updateStatus('Начало конвертации...', 10);

                // Simulate async process
                let progress = 10;
                const interval = setInterval(() => {
                    progress += 10;
                    if (progress <= 90) {
                        updateStatus(`Прогресс: ${progress}% - ${getStatusMessage(progress)}`, progress);
                    } else if (progress > 100) {
                        clearInterval(interval);
                        updateStatus('Конвертация завершена! Готов к загрузке.', 100);
                        downloadLinkSection.style.display = 'block';
                        downloadApkLink.href = '#'; // In a real app, this would be the actual download URL
                        downloadApkLink.download = `${appName.replace(/[^a-zA-Z0-9]/g, '') || 'WebApp'}.apk`;
                    }
                }, 700);
            });

            function getStatusMessage(progress) {
                if (progress <= 20) return 'Анализ веб-страницы...';
                if (progress <= 40) return 'Создание Android-проекта...';
                if (progress <= 60) return 'Интеграция веб-контента...';
                if (progress <= 80) return 'Компиляция и подписание APK...';
                if (progress <= 90) return 'Финальная оптимизация...';
                return 'Почти готово...';
            }
        });
    </script>

</body></html>
