# Pauses in Speech
This App will analyze pauses in speech and create automatic subtitles for uploaded audio. It is intended to be used for audiobooks.
You can also upload a manually created text transcript which the app uses to correct its automatically generated subtitles. Via audio to text alignment, it displays only the part of the transcript, which is currently being said.

You can access the interactive backend API documentation via http://localhost:8000/docs


# Demo

[![This is a demo screenshot of the App](https://github-production-user-asset-6210df.s3.amazonaws.com/51822945/274918796-826260e3-645d-4194-a694-6ed38e7803f5.png)](https://www.youtube.com/watch?v=E5KyIt7sALw)

Click on this picture to open the [Youtube](https://www.youtube.com/watch?v=E5KyIt7sALw) demo video. 

# How to run
Clone both repositories into a directory you want to use:

`git clone git@github.com:Pauses-In-Speech/transcribing_service.git`

`git clone git@github.com:Pauses-In-Speech/pis_webapp.git`

Running the backend and frontend requires [docker](https://docs.docker.com/engine/install/). To use GPU acceleration inside docker [install the Nvidia Container Toolkit](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/latest/install-guide.html).

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

Afterwards you can connect to http://localhost:3000 and run use the app!

# License

Both repositories are licensed with the MIT license
