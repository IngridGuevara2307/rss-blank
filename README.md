<div id="info">Aquí aparecerá información adicional</div>

<script>
fetch('blank.xml')
  .then(response => {
    if (!response.ok) throw new Error("No se pudo cargar el XML");
    return response.text();
  })
  .then(str => {
    const parser = new DOMParser();
    const xml = parser.parseFromString(str, "application/xml");
    const title = xml.querySelector("title");
    document.getElementById("info").textContent = title ? title.textContent : ".";
  })
  .catch(error => {
    // Si ocurre un error (como CORS), al menos se muestra un punto
    document.getElementById("info").textContent = ".";
    console.error("Error al cargar el XML:", error);
  });
</script>
