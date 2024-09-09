FROM hkubal/clair3:v1.0.10

# Define the base URL
ENV CLAIR3_BASE_URL="https://cdn.oxfordnanoportal.com/software/analysis/models/clair3/"

# Define build arguments for the file names (space-separated)
ARG CLAIR3_FILES="r1041_e82_400bps_sup_v430.tar.gz r1041_e82_400bps_hac_v430.tar.gz r1041_e82_400bps_sup_v500.tar.gz r1041_e82_400bps_hac_v500.tar.gz"

# Set environment variables based on build arguments
ENV CLAIR3_FILES="$CLAIR3_FILES"

# Download and extract each file by appending it to the base URL
RUN for FILE in $(echo $CLAIR3_FILES); do \
        wget ${CLAIR3_BASE_URL}${FILE} -O - | tar xvz -C /opt/models; \
    done
