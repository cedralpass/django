# Getting Familiar with Django

# Install Django

[install instructions](https://docs.djangoproject.com/en/5.1/intro/install/)
simply adding django to the requirements.txt.

Check version of django:
```python -m django --version```

# First tutorial
[writing first app](https://docs.djangoproject.com/en/5.1/intro/tutorial01/)

# create db

- Change your models (in models.py).
- Run python manage.py makemigrations to create migrations for those changes
- Run python manage.py migrate to apply those changes to the database.


create migraitons from metadata in models.py
```python manage.py makemigrations polls```

test migrations by looking at the SQL genereated from migrations in ```migrartions``` folder

```python manage.py sqlmigrate polls 0001```


apply migrations to database
```python manage.py migrate```

## Test with the interactive Shell

``` python manage.py shell```

import the models
```from polls.models import Choice, Question```

import timezone
```from django.utils import timezone```

create a question
```
q = Question(question_text="What's new?", pub_date=timezone.now())
q.save()
q.id
Question.objects.all()

```

