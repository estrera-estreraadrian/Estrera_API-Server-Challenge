# Estrera_API-Server-Challenge
# Video Games REST API

This project is a simple REST API for managing video game information. Its built using Python, Flask, and SQLite.

The API allows users to:

* View all games
* View a specific game
* Add a new game
* Update an existing game
* Delete a game

## The methods

There are four API Methods used in the project;

* **GET** - Retrieves all games or just one specific game at a time.
* **POST** - Adds a new game to the database.
* **PUT** - Updates an existing game.
* **DELETE** - Removes a game from the database.


Each game contains information such as its title, genre, platform, and release year.

The API also includes basic validation to make sure required information is provided when adding or updating games.

## How to run it

First, install the required dependencies:

pip install -r requirements.txt

Then, run the server:

python app.py

The API will run at:

http://127.0.0.1:5000

## Sample Requests and Responses

### GET /games

Retrieves all games from the database.

**Request:**

GET http://127.0.0.1:5000/games

**Response:**

[
  {
    "id": 1,
    "title": "Warframe",
    "genre": "Action RPG",
    "platform": "PC",
    "release_year": 2013
  }
]

**Status Code:** 200 OK

### GET /games/<id>

Retrieves one specific game using its ID.

**Request:**

GET http://127.0.0.1:5000/games/1

**Response:**

{
  "id": 1,
  "title": "Warframe",
  "genre": "Action RPG",
  "platform": "PC",
  "release_year": 2013
}

**Status Code:** 200 OK

### POST /games

Adds a new game to the database.

**Request:**

POST http://127.0.0.1:5000/games

**Request Body:**

{
  "title": "Minecraft",
  "genre": "Sandbox",
  "platform": "PC",
  "release_year": 2011
}

**Response:**

{
  "id": 16,
  "title": "Minecraft",
  "genre": "Sandbox",
  "platform": "PC",
  "release_year": 2011
}

**Status Code:** 201 Created

### PUT /games/<id>

Updates an existing game in the database.

**Request:**

PUT http://127.0.0.1:5000/games/16

**Request Body:**

{
  "title": "Minecraft Java Edition",
  "genre": "Sandbox",
  "platform": "PC",
  "release_year": 2011
}

**Response:**

{
  "id": 16,
  "title": "Minecraft Java Edition",
  "genre": "Sandbox",
  "platform": "PC",
  "release_year": 2011
}

**Status Code:** 200 OK

### DELETE /games/<id>

Removes a game from the database.

**Request:**

DELETE http://127.0.0.1:5000/games/16

**Response:**

{
  "message": "Game deleted successfully"
}

**Status Code:** 200 OK

## Status Codes - Summary

- 200 OK - Successful GET, PUT, or DELETE request.
- 201 Created - Successfully created a new game.
- 400 Bad Request - Required information is missing.
- 404 Not Found - The requested game does not exist.

## Validation

POST and PUT requests require the following fields:

- title
- genre
- platform
- release_year

If any required field is missing the API returns a 400 Bad Request response with an error message.  

## The Live API

The API is deployed on Render and can be accessed here:

https://estrera-api-server-challenge.onrender.com

Example endpoint:

https://estrera-api-server-challenge.onrender.com/games