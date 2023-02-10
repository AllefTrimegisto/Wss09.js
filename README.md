# Wss09.js
#Crie um web service usando o Node.js e o framework Express.

Nele, desenvolva duas rotas HTTP com comunicação via JSON.
const express = require('express');
const app = express();
const port = 3000;

app.use(express.json());

app.get('/api/products', (req, res) => {
  const products = [
    {id: 1, name: 'Product 1'},
    {id: 2, name: 'Product 2'},
    {id: 3, name: 'Product 3'}
  ];
  res.status(200).json(products);
});

app.post('/api/products', (req, res) => {
  const product = req.body;
  console.log(product);
  res.status(201).json({message: 'Product created successfully'});
});

app.listen(port, () => {
  console.log(`Server running on port ${port}`);
});
