# Mock

O termo mock é utilizado quando estamos querendo nos referir a algum modelo, exemplo.

Exemplo:
Uma API qualquer retorna os seguintes dados:
```js
data: {
  id: '1',
  name: 'John Doe',
  state: active
}
```

Eu quero fazer um teste com a minha função/método que recebe os dado dessa API, porém não quero fazer a request a todo momento.

Então para isso eu posso utilizar um "Mock" que seria uma cópia local do que a API entregaria.

Exemplo fazendo a request:

```js
async function fetchData() {
  try {
    const response = await fetch('https://api.example.com/data');
    // Verifica se a resposta da solicitação é bem-sucedida
    if (!response.ok) {
      throw new Error('Ocorreu um erro ao obter os dados');
    }
    // Converte a resposta para JSON e a retorna
    return await response.json();
  } catch (error) {
    // Captura e trata erros
    console.error('Ocorreu um erro:', error);
    throw error;
  }
}

const dataToAPI = await fetchData();

handleData(dadosDaAPI);
```

Exemplo com Mock
```js
const dataToAPI = {
  id: '1',
  name: 'John Doe',
  state: active
};

handleData(dadosDaAPI);
```