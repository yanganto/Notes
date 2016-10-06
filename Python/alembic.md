## install and init

```
pip install alembic

alembic init db
```

## edit alembic.ini

```
sqlalchemy.url = postgresql+psycopg2://Username:Password@dblocation/dbname
```

## edit db/env.py

```
from __future__ import with_statement
from alembic import context
from sqlalchemy import engine_from_config, pool
from logging.config import fileConfig
import os
import sys

# add bellow two lines
sys.path.insert(0, os.path.realpath("."))
from twilio_service import models

target_metadata = models.DeclarativeBase.metadata

```

## upgrade database

### restore files with different envirnment
1. copy back the file in /db/versions from /db/versions/env/
2. copy back the alembic.ini from alembic.env.ini

### excuting migration
```
alembic revision --autogenerate
alembic upgrade head
```

