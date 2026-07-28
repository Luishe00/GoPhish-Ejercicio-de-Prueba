🎣 Campaña de Phishing con GoPhish — Caso Crunchyroll

Simulación de una campaña de phishing dirigida, realizada con GoPhish sobre Kali Linux, con fines exclusivamente formativos. El proyecto reproduce el ciclo completo de una campaña de concienciación en seguridad: desde la instalación de la herramienta hasta la recolección y análisis de los resultados.

📌 Objetivo

Demostrar de forma práctica cómo se diseña, ejecuta y mide una campaña de phishing controlada, entendiendo tanto la perspectiva del atacante (credibilidad del pretexto, clonado de páginas, plantillas de correo) como la utilidad de este tipo de simulaciones para entrenar a los usuarios frente a ataques reales.

🧠 Pretexto elegido

Se seleccionó Crunchyroll (plataforma de streaming de anime) como marca a suplantar, aprovechando que la campaña coincidía con su 9º aniversario para justificar de forma creíble un correo de "descuento por aniversario" y aumentar la tasa de éxito del engaño.

🛠️ Herramienta

GoPhish — framework open source de simulación de phishing, preinstalado en Kali Linux (gophish-start / gophish-stop), con panel de administración en localhost:3333.

🔍 Fases de la campaña
1. Perfil de envío (Sending Profile)

Configuración del servidor SMTP (Gmail) desde el que se enviarían los correos, incluyendo autenticación en dos pasos y contraseña de aplicación, con envío de prueba para validar la configuración.

2. Grupos de destinatarios (Users & Groups)

Creación manual del grupo de objetivos (crunchy-test) con nombre, correo y datos adicionales de cada destinatario.

3. Página de aterrizaje (Landing Page)

Clonado de la página de login real de Crunchyroll, con captura de credenciales introducidas y redirección posterior a la web oficial para reducir sospechas. Para aumentar la credibilidad del enlace se editó /etc/hosts y se utilizó un dominio similar (typosquatting) en lugar de exponer una IP interna.

4. Plantilla de correo (Email Template)

Reutilización del código fuente de un correo real de Crunchyroll para maximizar el parecido visual con las comunicaciones legítimas de la marca.

5. Lanzamiento de la campaña

Configuración final combinando plantilla, landing page, perfil de envío y grupo de destinatarios, con la URL del servidor alojando la página falsa.

6. Recolección de datos

Análisis de resultados desde el panel de GoPhish: correos enviados, abiertos, clics en el enlace, credenciales introducidas (en texto plano), sistema operativo y navegador de las víctimas.

⚠️ Aviso legal y ético

Esta campaña se ejecutó en un entorno controlado y con fines exclusivamente educativos. No se registró ningún dominio real ni se dirigió el ataque contra usuarios ajenos al ejercicio. Ninguna técnica de este repositorio debe emplearse contra terceros sin autorización explícita: la suplantación de identidad y el phishing no autorizado son delito.

👥 Autores

Luis Hernando Esteban, Álvaro Salvador Castro, Pablo Valderas Cid
