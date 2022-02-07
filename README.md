# Exmeals API

## Introduction
This project was build to fulfill a challenge on the Elixir track, from Rocketseat Ignite Course

Techs used:
- Elixir
- Ecto
- Phoenix
- ExMachina
- PostgreSQL

## Challenge objective
The objective of this challenge was to build a simple CRUD API to monitor and create a meal log.

## API Documentation

As said, this API is a simple CRUD, which contains the following endpoints:

- POST `/api/meals` to register new meals on the database
    - The body passed contains the following parameters:
        - `description`: A string containing the meal description
        - `calories`: An integer containing the meal calories
        - `date`: A date in the format `YYYY-MM-DD` when the meal was consumed
        ```json
        {
            "description": "Burguer with fries",
            "calories": 378,
            "date": "2022-02-04"
        }
        ```
- GET `/api/meals/{id}` to list the data of a specific meal
    - The body of the response contains the following data:
        ```json
        {
            "meal": {
                "meal": {
                    "id": "734ab366-16fe-4c53-a659-c8f6d723fdec",
                    "description": "Burguer with fries",
                    "calories": 378,
                    "date": "2022-02-04"
                }
            },
            "message": "Meal created!"
        }
        ```
- DELETE `/api/meals/{id}` to delete a specific meal
- PUT `/api/meals/{id}` to update a specific meal
    - The bodu of the request can contain the `description`, `calories` or/and `date`

## Get it running

Pre-requisites:
- Elixir installed
- Phoenix Framework installed
- PostgreSQL database running

After cloning the repository, please run the following command to install all the project dependencies:

```
$ mix deps.get
```

After that, run the following command to set up the database and run the migration

```
$ mix ecto.setup
```

And finally run the following command to start the server locally (by default on port `4000`)

```
$ mix phx.server
```

If everything went well, you can now start sending requests to the endpoints!

You can run the unit tests with the following command:

```
$ mix test
```