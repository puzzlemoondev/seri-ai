# seri-ai

Diff-SVC voice model for Seri.

For base image I use [rocm-gfx803-docker](https://github.com/puzzlemoondev/rocm-gfx803-docker). You should change it to something else if you're not using the gfx803 gpu.

## Requirements

- docker
- docker-compose
- ffmpeg
- demucs

## Usage

Put data in place first. See [`compose.yml`](./compose.yml) for volumes that'll be mounted.

### Prepare raw data

`./prepare_raw [FILE OR DIRECTORY]`

Input files should have corresponding `.cue` file with format `hh:mm:ss-hh:mm:ss` and newline separated.

### Preprocess

`docker-compose run preprocess`

### Train

`docker-compose run train`

### Infer

`docker-compose run infer`

Input file should be inside `raw` folder with name `vocals.wav`
