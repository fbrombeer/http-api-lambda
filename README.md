# HTTP-API-LAMBDA

A framework for building typesafe Python HTTP APIs on top of AWS Lambda & API Gateway. It based on concepts of the most popular Python API framework, FastAPI, and extends these to the AWS context.

## Features
* Full editor support with syntax highlighting and auto completion with [Pydantic](https://github.com/pydantic/pydantic)
* JSON schema checking on incoming and outgoing entities
* 50% Faster than FastAPI + Mangum (see Performance)

## Usage

    from http_api_lambda import App

    app = App()

    @app.get("/")
    def root():
        return {"message": "Hello World!"}


    def handler(event, context):
        return app.handle_request(event, context)


## Performance
Compared to FastAPI with Mangum, http-api-lambda reduces the execution duration by more than 50%. Tested with a [basic example](https://github.com/fbrombeer/http-api-lambda-speed-comparison), I achieved an average execution duration of 4.5ms for http-api-lambda vs 12.1ms for FastAPI with Mangum over a sample set of 100 invokations.