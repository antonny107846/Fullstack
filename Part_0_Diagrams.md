sequenceDiagram
    participant Navegador Web
    participant Servidor

    Navegador Web->>Servidor: GET https://studies.cs.helsinki.fi/exampleapp/notes
    activate Servidor
    Servidor-->>Navegador Web: Documento HTML
    deactivate Servidor

    Navegador Web->>Servidor: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate Servidor
    Servidor-->>Navegador Web: Archivo CSS
    deactivate Servidor

    Navegador Web->>Servidor: GET https://studies.cs.helsinki.fi/exampleapp/main.js
    activate Servidor 
    Servidor-->>Navegador Web: Archivo JavaScript
    deactivate Servidor

    Note right of Navegador Web: La aplicación web comienza a ejecutar el código JavaScript que obtiene el JSON del servidor

    Navegador Web->>Servidor: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate Servidor
    Servidor-->>Navegador Web: [{ "content": "HTML es fácil", "date": "2023-1-1" }, ... ]
    deactivate Servidor

    Note right of Navegador Web: La aplicación web ejecuta la función de devolución de llamada que renderiza las notas

