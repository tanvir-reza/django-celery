FROM python:3.11.4-alpine

WORKDIR /usr/src/app

ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

COPY ./requirements.txt /usr/src/app/requirements.txt

COPY ./endpoint.sh /usr/src/app/endpoint.sh

RUN pip install -r requirements.txt

COPY . /usr/src/app

ENTRYPOINT [ "/usr/src/app/endpoint.sh" ]

CMD ["python3", "manage.py", "runserver" ,"0.0.0.0:8000"]
