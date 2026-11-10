const http = require('http');
const port = process.env.PORT || 3000; 

const server = http.createServer((req, res) => {
  console.log(`Petición recibida en: ${req.url}`);
  
  // Cabeceras CORS obligatorias para evitar bloqueos en Android
  res.setHeader('Access-Control-Allow-Origin', '*');
  res.setHeader('Access-Control-Allow-Methods', 'GET, POST, OPTIONS');
  res.setHeader('Content-Type', 'application/json');
  
  // Respuesta exitosa al juego
  res.statusCode = 200;
  res.end(JSON.stringify({ status: "success", message: "Conectado al FC Mobile 24 Reborn" }));
});

server.listen(port, '0.0.0.0', () => {
  console.log(`Servidor de Reborn activo en el puerto ${port}`);
});
