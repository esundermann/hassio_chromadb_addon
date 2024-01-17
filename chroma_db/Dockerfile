ARG BUILD_FROM
FROM $BUILD_FROM

# Install requirements for add-on
RUN \
  apk add --no-cache \
    python3
RUN pip install uvicorn
RUN pip install chromadb 
RUN pip install --force-reinstall fastapi==0.85.1
WORKDIR /chroma_data


COPY server.py .
CMD ["uvicorn", "server:app", "--port", "8000"]
