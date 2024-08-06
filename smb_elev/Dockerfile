
FROM firedrakeproject/firedrake-vanilla:2024-05

RUN sudo apt-get update && \
    sudo apt-get install -yq gmsh patchelf ffmpeg

RUN . firedrake/bin/activate && \
    pip install git+https://github.com/icepack/trilinos.git && \
    pip install git+https://github.com/icepack/pyrol.git && \
    git clone https://github.com/icepack/icepack.git && \
    pip install ./icepack

RUN . firedrake/bin/activate && \
    pip install ipykernel && \
    python -m ipykernel install --user --name=firedrake

RUN . firedrake/bin/activate && \
    pip install git+https://github.com/firedrakeproject/irksome.git@05e122041a2487b3c5b8946847397e2b81c81c1a && \
    git clone https://github.com/icepack/icepack2.git && \
    pip install ./icepack2

ENV PATH=/home/firedrake/firedrake/bin:$PATH
