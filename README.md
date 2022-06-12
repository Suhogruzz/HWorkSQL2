 ##Схема БД
 ![](https://github.com/Suhogruzz/HWorkSQL2/blob/main/SQL_HWork1.png)
 ##HWork SQL2
 ```sql
 CREATE TABLE IF NOT EXISTS performer (
	id SERIAL PRIMARY KEY,
	name VARCHAR(100) NOT NULL,
	id_genre INTEGER REFERENCES genre(id)
);

CREATE TABLE IF NOT EXISTS album (
	id SERIAL PRIMARY KEY,
	album_name VARCHAR(100) NOT NULL,
	album_year NUMERIC(4) NOT NULL,
	id_performer INTEGER REFERENCES performer(id)
);

CREATE TABLE IF NOT EXISTS track (
	id SERIAL PRIMARY KEY,
	track_name VARCHAR(100) NOT NULL,
	track_length REAL NOT NULL,
	id_album INTEGER REFERENCES album(id)
);

CREATE TABLE IF NOT EXISTS genre (
	id SERIAL PRIMARY KEY,
	genre_name VARCHAR(100) NOT NULL
);
