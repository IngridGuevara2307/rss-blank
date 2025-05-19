<div id="info">Aquí aparecerá información adicional</div>

<script>
const xmlString = `
<rss>
  <channel>
    <title>Mi canal de pruebas</title>
    <description>Esta es una descripción de ejemplo.</description>
  </channel>
</rss>
`;

const parser = new DOMParser();
const xml = parser.parseFromString(xmlString, "application/xml");

const title = xml.querySelector("title").textContent;
document.getElementById("info").textContent = title;
</script>
