# Deploying a Flask API

This project is a requirement of Udacity Full Stack Development Nanodegree.

In this project I containerized and deployed a Flask API to a Kubernetes cluster using Docker, AWS EKS, CodePipeline, and CodeBuild.

The Flask app that will be used for this project consists of a simple API with three endpoints:

- `GET '/'`: This is a simple health check, which returns the response 'Healthy'. 
- `POST '/auth'`: This takes a email and password as json arguments and returns a JWT based on a custom secret.
- `GET '/contents'`: This requires a valid JWT, and returns the un-encrpyted contents of that token. 

The app relies on a secret set as the environment variable `JWT_SECRET` to produce a JWT. The built-in Flask server is adequate for local development, but not production, so I will be using the production-ready [Gunicorn](https://gunicorn.org/) server when deploying the app.

## Dependencies

- Docker Engine
- AWS Account