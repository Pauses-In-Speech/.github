# Pauses in Speech

# Demo

[![This is a demo screenshot of the App](https://github-production-user-asset-6210df.s3.amazonaws.com/51822945/274918796-826260e3-645d-4194-a694-6ed38e7803f5.png)](https://www.youtube.com/watch?v=E5KyIt7sALw)

Click on this picture to open the [Youtube](https://www.youtube.com/watch?v=E5KyIt7sALw) demo video. 

# How to run

## Backend transcribing service
Navigate to /transcribing_service and run:

`docker build . -t transcribing_service`

### On GPU:
`docker run --rm --gpus all -p 8000:8000 -t transcribing_service`

### On CPU:
`docker run -p 8000:8000 -t transcribing_service`

## Webapp
Navigate to /pis_webapp and run:

`docker build . -t transcribing_service`

`docker run -it --rm -p 3000:3000 -v ${PWD}/src/:/app/src --name pis-web pis_webapp:latest`

Afterwards you can connect to localhost:3000 and run use the app!
