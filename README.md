# Jokes API

A simple RESTful API for managing jokes. This API supports CRUD operations for jokes and includes endpoints for adding, updating, deleting, and filtering jokes.

## Features

- **Add** a new joke.
- **Retrieve** jokes by ID or filter by type.
- **Update** existing jokes.
- **Delete** specific or all jokes with API key authorization.

---

## Technologies Used

- Node.js
- Express.js
- Body-parser
- Postman (for testing)

---

## Prerequisites

- [Node.js](https://nodejs.org/) installed
- [Postman](https://www.postman.com/) or any API testing tool

---

## Installation

1. Clone the repository:

```bash
git clone https://github.com/yourusername/jokes-api.git
```

2. Navigate into the project directory:

```bash
cd jokes-api
```

3. Install the dependencies:

```bash
npm install
```

4. Create a `.env` file in the root directory to store your `MASTER_KEY`:

```env
MASTER_KEY=your-master-key
```

5. Start the server:

```bash
node index.js
```

The server will run on `http://localhost:3000`.

---

## API Endpoints

### 1. **Get All Jokes**

- **URL**: `/jokes`
- **Method**: `GET`
- **Response**:

```json
[
  {
    "id": 1,
    "jokeText": "Why don't scientists trust atoms? Because they make up everything.",
    "jokeType": "Science"
  }
]
```

---

### 2. **Get a Random Joke**

- **URL**: `/random`
- **Method**: `GET`
- **Response**:

```json
{
  "id": 2,
  "jokeText": "Why did the scarecrow win an award? Because he was outstanding in his field.",
  "jokeType": "Puns"
}
```

---

### 3. **Get Joke by ID**

- **URL**: `/jokes/:id`
- **Method**: `GET`
- **Parameters**:
  - `id`: The ID of the joke to retrieve
- **Response**:

```json
{
  "id": 1,
  "jokeText": "Why don't scientists trust atoms? Because they make up everything.",
  "jokeType": "Science"
}
```

---

### 4. **Add a New Joke**

- **URL**: `/jokes`
- **Method**: `POST`
- **Body**:

```json
{
  "text": "Why don't programmers like nature? It has too many bugs.",
  "type": "Programming"
}
```

- **Response**:

```json
{
  "id": 3,
  "jokeText": "Why don't programmers like nature? It has too many bugs.",
  "jokeType": "Programming"
}
```

---

### 5. **Update a Joke**

- **URL**: `/jokes/:id`
- **Method**: `PUT`
- **Body**:

```json
{
  "text": "Why did the chicken join a band? Because it had the drumsticks.",
  "type": "Puns"
}
```

- **Response**:

```json
{
  "id": 2,
  "jokeText": "Why did the chicken join a band? Because it had the drumsticks.",
  "jokeType": "Puns"
}
```

---

### 6. **Partially Update a Joke**

- **URL**: `/jokes/:id`
- **Method**: `PATCH`
- **Body**:

```json
{
  "text": "Why do we never tell secrets on a farm? Because the potatoes have eyes."
}
```

- **Response**:

```json
{
  "id": 2,
  "jokeText": "Why do we never tell secrets on a farm? Because the potatoes have eyes.",
  "jokeType": "Puns"
}
```

---

### 7. **Delete a Specific Joke**

- **URL**: `/jokes/:id`
- **Method**: `DELETE`
- **Response**:

```json
{
  "message": "Joke deleted successfully"
}
```

---

### 8. **Delete All Jokes**

- **URL**: `/all`
- **Method**: `DELETE`
- **Headers**:

```json
{
  "api_key": "your-master-key"
}
```

- **Response**:

```json
{
  "message": "Deleted All"
}
```
