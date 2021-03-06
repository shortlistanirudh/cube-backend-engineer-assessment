# cube-backend-engineer-assessment

To get things started

# Requirements
a. Python (2.7, 3.4, 3.5, 3.6, 3.7)
b. Django (1.9, 1.10, 1.11, 2.0.7)
c. pip
d. Docker
e. Redis

# Init
1. Clone the repository
2. cd assessment

# DB + Redis (in new terminals) 
3a. 
docker run --rm -P -p 127.0.0.1:5432:5432 -e POSTGRES_PASSWORD="postgres" --name pg postgres:alpine

3b.
``` bash 
wget http://download.redis.io/releases/redis-5.0.5.tar.gz
tar xzf redis-5.0.5.tar.gz
cd redis-5.0.5
make
sudo src/redis-server
```
# Redis Worker + Redis Scheduler (in new terminals)
```bash
cd assessment
```
3c. 
```bash
rqworker
```

3d.
``` bash 
rqscheduler
```

# Server
4. pip install -r requirements.txt
5. ./manage.py makemigrations cube django_business_rules
6. ./manage.py migrate
7. ./manage.py dbr
8. ./manage.py runserver

# Output
9. Open localhost:8000/assessment/business-rule on the browser

Setup rules as per the requirement.

# Demo
http://8df2a8389742.ngrok.io/assessment/business-rule/

# Events POST URL
http://8df2a8389742.ngrok.io/cube-server/events

# Sample Event
```json
{
	"ts_source": "2020-12-22T18:30",
	"noun": "bill",
	"verb": "pay",
	"user":2,
	"properties": {"noun": "bill", "value":2000},
	"time_spent": 0
}
```

