# Work-3
const http = require('http');

// Беремо порт з першого аргументу командного рядка
const port = process.argv[2];

// Створюємо HTTP-сервер
const server = http.createServer((req, res) => {
  // Перевіряємо, що запит саме GET /
  if (req.method === 'GET' && req.url === '/') {
    res.statusCode = 200;
    res.setHeader('Content-Type', 'text/plain');
    res.end('Welcome to Manual HTTP Router');
  }
});

// Запускаємо сервер на вказаному порту
server.listen(port);
