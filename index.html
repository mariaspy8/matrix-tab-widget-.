# matrix-tab-widget-.

<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tabulador #ru:unredacted.org</title>
    <style>
        /* Diseño inspirado en Matrix/Element Dark */
        body { 
            background: #15191e; 
            color: #f3f4f5; 
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; 
            margin: 0; 
            padding: 15px;
            display: flex;
            flex-direction: column;
            height: 100vh;
            box-sizing: border-box;
        }
        
        #header {
            font-size: 0.9em;
            color: #a9b2bc;
            margin-bottom: 10px;
            border-bottom: 1px solid #394352;
            padding-bottom: 5px;
        }

        #display { 
            flex-grow: 1; 
            background: #181d23; 
            border: 1px solid #2e3641;
            padding: 15px; 
            overflow-y: auto; 
            margin-bottom: 15px; 
            border-radius: 8px;
            font-size: 0.95em;
            line-height: 1.5;
        }

        .input-wrapper {
            position: relative;
            display: flex;
            align-items: center;
        }

        input { 
            width: 100%;
            background: #21262c; 
            border: 1px solid #394352; 
            color: #ffffff; 
            padding: 12px 15px; 
            border-radius: 8px; 
            outline: none;
            font-size: 1em;
            transition: border-color 0.2s;
        }

        input:focus { 
            border-color: #0dbd8b; 
        }

        .hint {
            font-size: 0.75em;
            color: #61708b;
            margin-top: 8px;
        }

        .user-msg { color: #0dbd8b; font-weight: bold; }
        .system-msg { color: #e64b7b; font-style: italic; }
    </style>
</head>
<body>

    <div id="header">Matrix Widget: #ru:unredacted.org</div>
    
    <div id="display">
        <div class="system-msg">Система готова. Pulsa @ seguido de letras y luego TAB.</div>
    </div>
    
    <div class="input-wrapper">
        <input type="text" id="chatInput" placeholder="Escribe @usuario y pulsa Tabulador..." autocomplete="off">
    </div>
    
    <div class="hint">Usa <b>Tab ↹</b> para autocompletar nombres de usuarios.</div>

    <script src="https://unpkg.com/matrix-widget-api@0.1.0/dist/api.js"></script>
    <script>
        const widgetApi = new matrixWidgetApi.WidgetApi();
        const chatInput = document.getElementById('chatInput');
        const display = document.getElementById('display');

        // Base de datos de usuarios para el canal #ru
        const usuariosRu = [
            "@admin:unredacted.org", 
            "@mariaspy8:unredacted.org",
            "@ivan:unredacted.org", 
            "@sergei:unredacted.org", 
            "@vladimir:unredacted.org",
            "@boris:unredacted.org",
            "@unredacted_bot:unredacted.org"
        ];

        // Inicializar Widget
        widgetApi.requestCapabilities(['org.matrix.msc2762.receive.event', 'm.room.message']);
        widgetApi.start();

        chatInput.addEventListener('keydown', (e) => {
            // Lógica del Tabulador
            if (e.key === 'Tab') {
                e.preventDefault(); 
                
                const currentVal = chatInput.value;
                const words = currentVal.split(" ");
                const lastWord = words[words.length - 1];

                if (lastWord.startsWith('@')) {
                    const match = usuariosRu.find(u => 
                        u.toLowerCase().startsWith(lastWord.toLowerCase())
                    );

                    if (match) {
                        words[words.length - 1] = match;
                        chatInput.value = words.join(" ") + " ";
                    }
                }
            }

            // Enviar mensaje ficticio al presionar Enter
            if (e.key === 'Enter' && chatInput.value.trim() !== "") {
                const text = chatInput.value;
                display.innerHTML += `<div><span class="user-msg">Вы:</span> ${text}</div>`;
                chatInput.value = "";
                display.scrollTop = display.scrollHeight;
            }
        });
    </script>
</body>
</html>
