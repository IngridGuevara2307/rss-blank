<div id="info">Aquí aparecerá información adicional</div>

<script>
// XML embebido como cadena de texto
const xmlString = `
<rss version="2.0">
  <channel>
    <title>Ejemplo de RSS</title>
    <description>Descripción de prueba</description>
    <link>https://ejemplo.com</link>
  </channel>
</rss>
`;

// Parsear el XML y mostrar el título
const parser = new DOMParser();
const xml = parser.parseFromString(xmlString, "application/xml");
const title = xml.querySelector("title")?.textContent || ".";

document.getElementById("info").textContent = title;
</script>
