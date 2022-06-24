# escape=`

ARG BASE_IMAGE
ARG SPE_IMAGE
ARG HEADLESS_SERVICES_IMAGE

FROM ${SPE_IMAGE} as spe
FROM ${HEADLESS_SERVICES_IMAGE} as headless_services_image
FROM ${BASE_IMAGE}

COPY --from=headless_services_image C:\module\db C:\jss_data
COPY --from=spe C:\module\db C:\resources\spe