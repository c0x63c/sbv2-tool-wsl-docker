FROM nvidia/cuda:12.1.0-base-ubuntu22.04

ENV PYTHONUNBUFFERED=1 

# system
# python3
RUN apt update -y -q && DEBIAN_FRONTEND=noninteractive apt install -y -q --no-install-recommends \
    software-properties-common apt-utils build-essential cmake \
    curl git git-lfs vim \
    python3.10 python3.10-dev pip libgl1-mesa-dev ffmpeg \
    && rm -rf /var/lib/apt/lists/*

# git
RUN git clone https://github.com/litagin02/laughter-collector.git /sbv2-tool
WORKDIR /sbv2-tool
# typo fix
RUN sed -i s/splice.py/slice.py/ collect_laughter.py
# fix music len check
RUN sed -i -e "41,42s:^:#:" slice.py

# requirements pytorch
RUN pip install --upgrade pip 
RUN pip install -r requirements.txt
RUN pip install torch==2.2.2+cu121 torchaudio==2.2.2+cu121 torchvision==0.17.2+cu121 --index-url https://download.pytorch.org/whl/cu121
RUN pip install transformers==4.40.0 soundfile==0.12.1 tokenizers==0.19.1

# shell
CMD ["/bin/bash"]
