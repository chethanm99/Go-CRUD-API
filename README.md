# Go Movie CRUD API

A simple, lightweight RESTful API for performing CRUD (Create, Read, Update, Delete) operations on a movie collection. This project is built in Go and uses the `gorilla/mux` router for handling HTTP requests.

The application runs a local web server and manages a list of movies in-memory.

## Getting Started

Follow these instructions to get the project running on your local machine.

### Prerequisites

*   [Go](https://golang.org/dl/) (version 1.18 or newer)
*   An API client like `curl` or [Postman](https://www.postman.com/)

### Installation & Usage

1.  **Clone the repository** (or save the code as `main.go` in a new directory).

2.  **Navigate to the project directory** and install the required dependency:
    ```sh
    go mod tidy
    ```

3.  **Run the server:**
    ```sh
    go run main.go
    ```
    The server will start on `http://localhost:8000`.

## API Endpoints

The base URL for all endpoints is `http://localhost:8000`.

| Action            | Method   | Endpoint          | Description                                                    |
| ----------------- | -------- | ----------------- | -------------------------------------------------------------- |
| **Get All Movies**  | `GET`    | `/movies`         | Retrieves a list of all movies in the collection.              |
| **Get Single Movie**| `GET`    | `/movies/{id}`    | Retrieves a single movie by its unique ID.                     |
| **Create Movie**    | `POST`   | `/movies`         | Adds a new movie to the collection. The ID is auto-generated.  |
| **Update Movie**    | `PUT`    | `/movies/{id}`    | Updates the details of an existing movie by its ID.            |
| **Delete Movie**    | `DELETE` | `/movies/{id}`    | Removes a movie from the collection by its ID.                 |

---

### Request Examples

#### Get All Movies
```sh
curl -X GET http://localhost:8000/movies
```

#### Get a Movie by ID
```sh
curl -X GET http://localhost:8000/movies/1
```

#### Create a New Movie
```sh
curl -X POST -H "Content-Type: application/json" -d '{
    "isbn": "987654",
    "title": "Movie Three",
    "director": {
        "firstname": "Jane",
        "lastename": "Roe"
    }
}' http://localhost:8000/movies
```

#### Update a Movie by ID
```sh
curl -X PUT -H "Content-Type: application/json" -d '{
    "isbn": "45455-2",
    "title": "Movie Two (Updated)",
    "director": {
        "firstname": "Steven",
        "lastename": "Smith"
    }
}' http://localhost:8000/movies/2
```

#### Delete a Movie by ID
```sh
curl -X DELETE http://localhost:8000/movies/1
```

---

*Thank you for exploring this project*
