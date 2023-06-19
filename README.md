# Conocimiento personalizado para usar con OpenAI

(Escrito en Junio de 2023)

Es publicamente conocido que el LLM que utiliza OpenAI para ChatGPT fue entrenado con conocimiento hasta septiembre de 2021.

Por ejemplo podemos preguntar sobre el apple event del 2023 y obtendremos la siguiente respuesta:

![alt text](https://i.imgur.com/fw2SkzX.png "ChatGPT no knowledge after sep2021")

Inclusive podriamos no decir nada acerca de la fecha en nuestro promt, sino preguntar por un objeto que es dado a conocer despues de septiembre de 2021 y obtendriamos un resultado similar.

![alt text](https://i.imgur.com/RDXv6P9.png "ChatGPT no knowledge for objects after sep2021")

---

## ¿Que podemos hacer si queremos preguntar sobre eventos despues de dicha fecha?

Podemos usar LLamma y LangChain para crear indices con conocimiento personalizado

Para este ejempplo con notebooks de Python, convertí manualmente a texto las siguiente noticias del apple event de 2023

- [(Apple Event 2023: esto fue TODO lo que se presentó en el evento de tecnología](https://www.heraldobinario.com.mx/tendencias/2023/6/5/apple-event-2023-esto-fue-todo-lo-que-se-presento-en-el-evento-de-tecnologia-35716.html)

- [Apple Event 2023: todos los detalles de WWDC 2023 en vivo minuto a minuto
](https://expansion.mx/tecnologia/2023/06/05/apple-evento-2023-en-vivo#uuid00000188-8cf1-d409-a399-eef522330000)

- [Apple Event 2023: conoce todas las novedades del WWDC
](https://eldiario.com/2023/06/05/apple-event-2023-noedades-wwdc/)

Los archivos de texto los podras encontrar en .\context_data\data\apple_event

### Requisitos

- VScode
- Python 3
- Instalar las extensiones de python de VScode
- Crear una carpeta para el proyecto con un entorno virtual de python

```bash
mkdir terminalGPT

cd terminalGPT

py -m venv .\venv
```

- Tener un clave privada de OpenAI
    - Tener usuario de OpenAI
    - Crear la api key en [(https://platform.openai.com/](https://platform.openai.com/)
    - Es posible que les sea solicitada información de facturación, pueden proporcionar una tarjeta de crédito o debito, no se preocupen por que los costos de uso de la api de ChatGPT son bastante bajos. [https://openai.com/pricing](https://openai.com/pricing)

---

### Como utilizar este notebook

- En VScode abre el archivo gptWithAppleEventInfo.ipynb.
- Click en Run All.
- Seleccionas el entorno virtual creado anteriormente.
- Te sera presentando repetidamente un promt donde podras realizar preguntas sobre el apple event hasta que escribas "exit"