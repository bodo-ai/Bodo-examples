FROM condaforge/mambaforge as build

RUN conda install -y python=3.12 bodo -c bodo.ai -c conda-forge

FROM mpioperator/mpich:0.6.0

COPY --from=build /opt/conda /opt/conda

RUN chown -R mpiuser /opt/conda
ENV PATH /opt/conda/bin:${PATH}
USER mpiuser

ADD pi.py pi.py
