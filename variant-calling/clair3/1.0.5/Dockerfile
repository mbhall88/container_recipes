FROM hkubal/clair3:v1.0.5

ENV CLAIR3_SUP="https://cdn.oxfordnanoportal.com/software/analysis/models/clair3/r1041_e82_400bps_sup_v430.tar.gz"
ENV CLAIR3_HAC="https://cdn.oxfordnanoportal.com/software/analysis/models/clair3/r1041_e82_400bps_hac_v430.tar.gz"

RUN (wget $CLAIR3_SUP -O - | tar xvz -C /opt/models) && \
    (wget $CLAIR3_HAC -O - | tar xvz -C /opt/models)