# 4B Owls Speech Recognition Trial

## Description
This project demonstrates speech recognition capabilities using the ESPnet 4B Owls model. The notebook showcases:
- Speech-to-text inference
- Language-specific recognition

## Prerequisites
### Hardware Requirements
- CUDA-capable GPU
- Recommended GPU Specifications:
  - 4B Model: 40 GB vRAM recommended (tested on L40)
  - 9B Model: 55-60 GB vRAM recommended

### Software Requirements
- Docker
- NVIDIA Container Toolkit

## Installation

### Pull the docker image
This docker image is based on [NVIDIA NeMo Framework](https://catalog.ngc.nvidia.com/orgs/nvidia/containers/nemo) `nvcr.io/nvidia/nemo:24.01.speech`
```bash
docker pull warrents/espnet:202503
```

## Usage

### Starting Jupyter Lab
Run the Docker container with GPU support:
```bash
docker run -it --rm --gpus all \
  -p 8888:8888 \
  -v /YOUR/HOST/MOUNT/POINT:/workspace/ws \
  --shm-size=2g \
  -w /workspace/ws \
  warrents/espnet:202503 \
  jupyter lab --ip 0.0.0.0 --allow-root --NotebookApp.token=''
```

### Preparing Audio Files
- Prepare audio files for transcription
- Example files in notebook: 
  - `zh.wav` for Chinese transcription
  - `en.wav` for English transcription

### Notebook Functionality
The script will:
- Load the pretrained 4B Owls ASR model
- Perform language-specific transcription

## Model Reference
- **Pretrained Model**: [`espnet/owls_4B_180K`](https://huggingface.co/espnet/owls_4B_180K)
