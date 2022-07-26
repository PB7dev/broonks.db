## Broonks Database
Um simples banco de dados em JSON com o foco em performance e simplicidade.

Inspirado no [quick.db](https://www.npmjs.com/package/quick.db) e no [Enmap](https://www.npmjs.com/package/enmap).

---

## Instalação
Instale a database com `npm install broonks.db`

---

## Exemplo básico
```javascript
const DatabaseManager = require('broonks.db')

//Essa será a varíavel que você usará para manipular a Database.
const Database = new DatabaseManager()

//Define a chave 'pessoas bonitas' para uma lista com pb7 e broonks
Database.set('pessoas bonitas', ['pb7', 'broonks'])

//Adiciona o valor Toledo a chave 'pessoas bonitas' (apenas arrays/listas)
Database.push('pessoas bonitas', 'Toledo')

//Define a chave 'pessoas bonitas' para google.com
Database.set('website', 'google.com')

//Retorna o valor contido na chave website
Database.get('website')

//Excluí a chave website
Database.delete('website')
```

---

## Documentação
> Interrogação (?) signfica que uma opção é opcional e já possui um valor atribuído por padrão.

> Opções sem interrogação retornarão um erro dizendo que uma opção está faltando em tal metódo.

- `Database#set(chave, valor)` **|** Cria ou altera uma chave com o valor específico
  ```js
  Database.set('melhor bot', 'broonks')
  ```
  - Tipos:
    - Chave: string, number
    - Valor: any (\*)
    - Resultado: undefined

- `Database#get(chave)` **|** Retorna o valor da chave
  ```js
  Database.get('melhor bot')
  ```
  - Tipos:
    - Chave: string | number
    - Resultado: undefined **|** any (\*)

- `Database#delete(chave)` **|** Exclui uma chave
  ```js
  Database.delete('moedas')
  ```
  - Tipos:
    - Chave: string | number
    - Resultado: undefined

    
- `Database#exists(chave)` **|** Verifica se uma chave existe
  ```js
  Database.exists('moedas')
  ```
  - Tipos:
    - Chave: string | number
    - Resultado: boolean

- `Database#add(chave, quantia)` **|** Adiciona um número para a chave (adição)
  ```js
  Database.add('dinheiro', 1200)
  ```
  - Tipos:
    - Chave: string | number
    - Quantia: number
    - Resultado: undefined

- `Database#remove(chave, quantia)` **|** Remove um número para a chave (subtração)
  ```js
  Database.remove('dinheiro', 1200)
  ```
  - Tipos:
    - Chave: string | number
    - Quantia: number
    - Resultado: undefined


- `Database#push(chave, item)` **|** Adiciona um item a uma array
  ```js
  Database.push('amigos', 'Jookie')
  ```
  - Tipos:
    - Chave: string | number
    - Item: any
    - Resultado: undefined

    
- `Database#pull(chave, item)` **|** Remove um item de uma array
  ```js
  Database.pull('amigos', 'Darkness')
  ```
  - Tipos:
    - Chave: string | number
    - Item: any
    - Resultado: undefined


- `Database#includes(chave, item)` **|** Verifica se uma array possui um item específico
  ```js
  Database.includes('amigos', 'MrPowerGamerBR')
  ```
  - Tipos:
    - Chave: string | number
    - Item: any
    - Resultado: boolean

- `Database#ping` **|** Informa o tempo em miliseggundos para escrever e remover um item
  ```js
  Database.ping
  ```
  - Tipos:
    - Resultado: number


- `Database#deleteAll()` **|** Apaga todos os itens do banco de dados
  ```js
  Database.deleteAll()
  ```
  - Tipos:
    - Resultado: undefined


- `Database#storage` **|** Retorna o objeto da database
  ```js
  Database.storage
  ```
  - Tipos:
    - Resultado: object


- `Database#all(tipo?)` **|** Retorna todos os itens da database
  ```js
  Database.all('all') //Retorna todas as entradas da database
  Database.all('keys') //Retorna todas as chaves da database
  Database.all('values') //Retorna todas os valores da database
  ```
  - Tipos:
    - Resultado: object
