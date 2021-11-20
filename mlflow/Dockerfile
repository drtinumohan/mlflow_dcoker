FROM continuumio/miniconda3:latest

WORKDIR /app

COPY wait-for-it.sh wait-for-it.sh 
COPY requirements.txt requirements.txt
RUN chmod +x wait-for-it.sh
RUN pip install -r requirements.txt
CMD ["bash", "-c"  ,"mlflow server --backend-store-uri sqlite:///mydb.sqlite --default-artifact-root s3://${AWS_BUCKET_NAME}/  -h 0.0.0.0" ]

