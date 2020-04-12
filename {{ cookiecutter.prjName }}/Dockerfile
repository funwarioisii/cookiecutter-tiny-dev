FROM python:3.8

COPY ./requirements.txt /requirementx.txt
RUN pip install -r /requirements.txt

WORKDIR /work
CMD ["make", "jupyter"]
