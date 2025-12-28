# matrix-tab-widget-.
<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <style>
        body { background: #1a1a1a; color: #e0e0e0; font-family: sans-serif; margin: 0; padding: 10px; overflow: hidden; }
        #container { display: flex; flex-direction: column; height: 95vh; }
        #display { flex-grow: 1; border: 1px solid #333; background: #222; padding: 10px; overflow-y: auto; margin-bottom: 10px; border-radius: 4px; font-size: 14px; }
        #input-area { display: flex; gap: 5px; }
        input { flex-grow: 1; background: #333; border: 1px solid #444; color: white; padding: 10px; border-radius: 4px; outline: none; }
        input:focus { border-color: #0dbd8b; }
        .user-tag { color: #0dbd8b; font-weight: bold; }
    </style>
</head>
<body>

<div id="container">
    <div id="display">Добро пожаловать в #ru:unredacted.org<br>Escribe @ y pulsa TAB para completar...</div>
    <div id="input-area">
        <input type="text" id="chatInput" placeholder="Escribe aquí..." autocomplete="off">
    </div>
</div>

<script src="https://unpkg.com/matrix-widget-api@0.1.0/dist/api.js"></script>
<script>
    const widgetApi = new matrixWidgetApi.WidgetApi();
    const chatInput = document.getElementById('chatInput');
    const display = document.getElementById('display');

    // Lista de usuarios simulada (puedes cargarla dinámicamente luego)
    const usuariosRu = ["@admin:unredacted.org", "@ivan:unredacted.org", "@boris:matrix.org", "@sergei_ru", "@unredacted_bot"];

    // Configuración del Widget
    widgetApi.requestCapabilities(['org.matrix.msc2762.receive.event', 'm.room.message']);
    widgetApi.start();

    chatInput.addEventListener('keydown', (e) => {
        if (e.key === 'Tab') {
            e.preventDefault();
            const words = chatInput.value.split(" ");
            const lastWord = words[words.length - 1];

            if (lastWord.startsWith('@')) {
                const match = usuariosRu.find(u => u.toLowerCase().startsWith(lastWord.toLowerCase()));
                if (match) {
                    words[words.length - 1] = match;
                    chatInput.value = words.join(" ") + " ";
                }
            }
        }

        if (e.key === 'Enter' && chatInput.value.trim() !== "") {
            display.innerHTML += `<div><span class="user-tag">Usted:</span> ${chatInput.value}</div>`;
            chatInput.value = "";
            display.scrollTop = display.scrollHeight;
        }
    });
</script>
</body>
</html>
