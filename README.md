- main.py: description of Get, post, update, delete 
- models.py: It is found in the row and column of tables.
- database.py: There is information about databases.
- response model: Show limited information.
- router: Use this file to make more modelers.
- auth: There is fundamental information for access.

### 1. Pip İnstall
```
pip install -r requirements.txt
```

### 2. Create Database
```
docker run --rm -d --name postgresql -e POSTGRES_USER=postgres -e POSTGRES_PASSWORD=Ankara06 -e PGDATA=/var/lib/postgresql/data/pgdata -p 5433:5432 -v postgresql13_v:/var/lib/postgresql/data postgres:13
```

### 3. Connect database and create user and give privileges

- Open psql  
```
docker exec -it postgresql psql -U postgres 
```

- List users
```
postgres=# \du
```

- Create and grant
```
create database traindb;
create user train with encrypted password 'Ankara06';
grant all privileges on database traindb to train;
```

### 4. Run uvicorn
```
uvicorn mall.main:app --host 0.0.0.0 --port 8002 --reload
```

### Use information of project data

Samsung,64.0,4.0,6.5,5000.0,8.0,48.0,2.0,2.0,2.0,2.999
```
{
  "memory": 64.0,
  "ram": 4.0,
  "screen_size": 6.5,
  "power": 5000,
  "front_camera": 8.0,
  "rc1": 48.0,
  "rc3": 2.0,
  "rc5": 2.0,
  "rc7": 2.0
}
```

Samsung,128.0,6.0,6.5,4500.0,32.0,12.0,12.0,8.0,0.0,6.849

```
{
  "memory": 128.0,
  "ram": 6.0,
  "screen_size": 6.5,
  "power": 4500,
  "front_camera": 32.0,
  "rc1": 12.0,
  "rc3": 12.0,
  "rc5": 8.0,
  "rc7": 0.0
}
```

Oppo,64.0,4.0,6.52,4230.0,8.0,13.0,2.0,2.0,0.0,2.749
```
{
  "memory": 64.0,
  "ram": 4.0,
  "screen_size": 6.52,
  "power": 4230,
  "front_camera": 8.0,
  "rc1": 13.0,
  "rc3": 2.0,
  "rc5": 2.0,
  "rc7": 0.0
}
```

Xiaomi,64.0,3.0,6.53,5000.0,5.0,13.0,0.0,0.0,0.0,2.692
```
{
  "memory": 64.0,
  "ram": 3.0,
  "screen_size": 6.53,
  "power": 5000,
  "front_camera": 5.0,
  "rc1": 13.0,
  "rc3": 0.0,
  "rc5": 0.0,
  "rc7": 0.0
}
```

iPhone,64.0,4.0,6.1,3110.0,12.0,12.0,12.0,0.0,0.0,11.199
```
{
  "memory": 64.0,
  "ram": 4.0,
  "screen_size": 6.1,
  "power": 3110,
  "front_camera": 12.0,
  "rc1": 12.0,
  "rc3": 12.0,
  "rc5": 0.0,
  "rc7": 0.0
}
```


### 5. See the table is created.
```
docker exec -it postgresql psql -U train -d traindb
```

### 6. See databeses

```
traindb=> \dt
```


### 7. Show Table 

```
postgres=# \l
```

```
select * from create_data;
```

```
select * from "user";
```