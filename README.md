# HTTP-API-LAMBDA

A framework for building typesafe Python HTTP APIs on top of AWS Lambda & API Gateway. It based on concepts of the most popular Python API framework, FastAPI, and extends these to the AWS context.

## Features
* Full editor support with syntax highlighting and auto completion with [Pydantic](https://github.com/pydantic/pydantic)
* JSON schema checking on incoming and outgoing entities
* 30% Faster than FastAPI + Mangum

## Usage

    from http_api_lambda import App

    app = App()

    @app.get("/")
    def root():
        return {"message": "Hello World!"}


    def handler(event, context):
        return app.handle_request(event, context)


