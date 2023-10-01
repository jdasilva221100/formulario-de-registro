document.getElementById("registroForm").addEventListener("submit", function(event) {
          event.preventDefault();
  
          const nombre = document.getElementById("nombre").value;
          const apellido = document.getElementById("apellido").value;
          const fechaNacimiento = document.getElementById("fechaNacimiento").value;
  
      
          const data = {
              nombre: nombre,
              apellido: apellido,
              fechaNacimiento: fechaNacimiento
          };
  
          fetch("https://jsonplaceholder.typicode.com/users", {
              method: "POST",
              headers: {
                  "Content-Type": "application/json"
              },
              body: JSON.stringify(data)
          })
          .then(response => response.json())
          .then(data => {
              console.log("Respuesta del servidor:", data);
            
          })
          .catch(error => {
              console.error("Error al enviar los datos:", error);
          });
      });

      <!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Formulario de Registro</title>
</head>
<body>
    <h2>Formulario de Registro</h2>
    <form id="registroForm">
        <div>
            <label for="nombre">Nombre:</label>
            <input type="text" id="nombre" name="nombre" required>
        </div>
        <div>
            <label for="apellido">Apellido:</label>
            <input type="text" id="apellido" name="apellido" required>
        </div>
        <div>
            <label for="fechaNacimiento">Fecha de Nacimiento:</label>
            <input type="date" id="fechaNacimiento" name="fechaNacimiento" required>
        </div>
        <div>
            <button type="submit">Registrarse</button>
        </div>
    </form>
</body>
</html>
