FROM python:3.9-slim-buster

ENV PYTHONUNBUFFERED 1
# ENV DJANGO_SETTINGS_MODULE project.settings  # Replace with your project's settings module

WORKDIR /app
COPY ./requirements.txt ./

RUN pip install --upgrade pip --no-cache-dir
RUN pip install -r requirements.txt --no-cache-dir
COPY . .

EXPOSE 8000

#CMD ["python", "manage.py", "migrate"]
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]
