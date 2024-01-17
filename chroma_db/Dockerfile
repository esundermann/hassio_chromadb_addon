ARG BUILD_FROM
FROM $BUILD_FROM

SHELL ["/bin/bash", "-o", "pipefail", "-c"]


# Install requirements for add-on
RUN apt update && apt install -y \
  apk add --no-cache \
    python3 \
    python3-pip

RUN pip install uvicorn
RUN pip install chromadb 
RUN pip install --force-reinstall fastapi==0.85.1
WORKDIR /chroma_data


COPY server.py .
CMD ["uvicorn", "server:app","--host", "0.0.0.0", "--port", "8000"]
