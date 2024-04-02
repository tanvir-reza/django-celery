pip freeze > requirements.txt
chmod +x ./endpoint.sh
docker-composer up -d --build
docker exec -it django /bin/sh

<!-- Celery Group -->

from celery import group
from newapp.tasks import tp1,tp2,tp3,tp4
task_group = group(tp1.s()......)
task_group.apply_async()

<!-- celery Task Chaining -->
from celery import chain
from newapp.tasks import tp1,tp2,tp3,tp4
task_chain = chain(tp1.s(),tp2.s(),tp3.s(),tp4.s())
task_chain.apply_async()
