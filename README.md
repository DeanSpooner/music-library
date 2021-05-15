# Project: Music Library

This project aims to create an app for managing a music library, implementing SQL, databases and express.js.

## Purpose

To design and implement an API which can perform CRUD operations on a database. This will take JSON GET, POST, PATCH, PUT and DELETE requests to add, read, update or delete artists from a music database.

## Getting Started

This project requires [NPM](https://www.npmjs.com/get-npm), [Node.js](https://nodejs.org/en/download/), [MySQL](https://www.mysql.com/) and [Docker](https://www.docker.com/).

## Pull this repo and install NPM

    $ git clone https://github.com/DeanSpooner/music-library.git
    $ cd music-library
    $ npm install

## Configure app

Add the following into `.env` and `.env.test` files in the root folder of the project:

```properties
DB_PASSWORD=password
DB_NAME=music_library
DB_USER=root
DB_HOST=localhost
DB_PORT=3307
PORT=3000
```

## Start the app

    $ npm start

# API Endpoints

| URI                                         | Request Method | CRUD     | What does it do?                                                                         |
| ------------------------------------------- | -------------- | -------- | ---------------------------------------------------------------------------------------- |
| [/artist](#list-all-artists)                | `GET`          | `READ`   | Generate a list of all artists in the database's `Artists` table.                        |
| [/artist](#create-new-artist)               | `POST`         | `CREATE` | Adds an artist to the table in the database.                                             |
| [/artist/\*](#get-artist-by-id)             | `GET`          | `READ`   | Fetches the artist from the database's `Artists` table with the same \* ID (an integer). |
| [/artist/\*](#update-existing-artist-by-id) | `PATCH`        | `UPDATE` | Updates the artist with the matching \* ID.                                              |
| [/artist/\*](#delete-artist-by-id)          | `DELETE`       | `DELETE` | Deletes the artist with the matching \* ID.                                              |

---

### List All Artists

`GET` `/artist`

#### Response Body

```json
[
  {
    "id": 1,
    "name": "Tina Turner",
    "genre": "Rock",
    "createdAt": "2021-05-08T21:01:24.000Z",
    "updatedAt": "2021-05-08T21:01:24.000Z"
  },
  {
    "id": 2,
    "name": "Lady Gaga",
    "genre": "Pop",
    "createdAt": "2021-05-08T21:09:56.000Z",
    "updatedAt": "2021-05-08T21:09:56.000Z"
  },
  {
    "id": 3,
    "name": "Kim Petras",
    "genre": "Pop",
    "createdAt": "2021-05-08T21:14:00.000Z",
    "updatedAt": "2021-05-08T21:14:58.000Z"
  }
]
```

---

### Create new Artist

`POST` `/artist`

#### Request Body

```json
{
  "name": "Utada Hikaru",
  "genre": "J-Pop"
}
```

#### Response Body

```json
{
  "id": 4,
  "name": "Utada Hikaru",
  "genre": "J-Pop",
  "updatedAt": "2021-05-08T21:21:08.000Z",
  "createdAt": "2021-05-08T21:21:08.000Z"
}
```

---

### Get Artist by ID

`GET` `/artist/{ artist id }`

#### Response Body

```json
{
  "id": 1,
  "name": "Tina Turner",
  "genre": "Rock",
  "createdAt": "2021-05-08T21:01:24.000Z",
  "updatedAt": "2021-05-08T21:01:24.000Z"
}
```

---

### Update existing Artist by ID

`PATCH` `/artist/{ artist id }`

#### Request Body

```json
{
  "genre": "Japanese Pop"
}
```

#### Response Body

```json
{
  "id": 4,
  "name": "Utada Hikaru",
  "genre": "Japanese Pop",
  "createdAt": "2021-05-08T21:21:08.000Z",
  "updatedAt": "2021-05-08T21:22:02.000Z"
}
```

---

### Delete Artist by ID

`DELETE` `/artist/{ artist id }`

#### Response Body

```json
{
  "id": 4,
  "name": "Utada Hikaru",
  "genre": "Japanese Pop",
  "createdAt": "2021-05-08T21:21:08.000Z",
  "updatedAt": "2021-05-08T21:22:02.000Z"
}
```

## By Dean Spooner and Manchester Codes

[Dean Spooner](https://github.com/DeanSpooner)\
[Manchester Codes](https://github.com/MCRCodes)

## Version History

- 1.0
  - Initial release
  - Update README.md
  - Tested all artist CRUD methods work correctly
