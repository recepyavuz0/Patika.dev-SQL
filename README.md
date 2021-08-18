# Patika.dev SQL Ödevleri

## ÖDEV 1

1. film tablosunda bulunan title ve description sütunlarındaki verileri sıralayınız.

```sql
SELECT title,description FROM film
```

2. film tablosunda bulunan tüm sütunlardaki verileri film uzunluğu (length) 60 dan büyük VE 75 ten küçük olma koşullarıyla sıralayınız.

```SQL
SELECT * FROM film where length > 60 and length < 75
ya da
SELECT * FROM film where length between 61 and 74
```

3. film tablosunda bulunan tüm sütunlardaki verileri rental_rate 0.99 VE replacement_cost 12.99 VEYA 28.99 olma koşullarıyla sıralayınız.

```sql
SELECT * FROM film where rental_rate = 0.99 and replacement_cost = 12.99 or rental_rate = 0.99 and replacement_cost = 28.99
```

4. customer tablosunda bulunan first_name sütunundaki değeri 'Mary' olan müşterinin last_name sütunundaki değeri nedir?

```sql
SELECT * FROM customer WHERE first_name='Mary'
```

5. film tablosundaki uzunluğu(length) 50 ten büyük OLMAYIP aynı zamanda rental_rate değeri 2.99 veya 4.99 OLMAYAN verileri sıralayınız.

```sql
SELECT * FROM film WHERE length < 50 and rental_rate <> 2.99 and rental_rate <> 4.99 
```
---

## ÖDEV 2

1. film tablosunda bulunan tüm sütunlardaki verileri replacement cost değeri 12.99 dan büyük eşit ve 16.99 küçük olma koşuluyla sıralayınız ( BETWEEN - AND yapısını kullanınız.)

```sql
SELECT * FROM film 
WHERE replacement_cost BETWEEN 12.99 AND 16.99
```

2. actor tablosunda bulunan first_name ve last_name sütunlardaki verileri first_name 'Penelope' veya 'Nick' veya 'Ed' değerleri olması koşuluyla sıralayınız. ( IN operatörünü kullanınız.)

```SQL
SELECT * FROM actor 
WHERE first_name IN('Penelope','Nick','Ed')
```

3. film tablosunda bulunan tüm sütunlardaki verileri rental_rate 0.99, 2.99, 4.99 VE replacement_cost 12.99, 15.99, 28.99 olma koşullarıyla sıralayınız. ( IN operatörünü kullanınız.)

```sql
SELECT * FROM film 
WHERE rental_rate IN(0.99,2.99,4.99) AND replacement_cost IN(12.99,15.99,28.99)
```
---

## ÖDEV 3

1. country tablosunda bulunan country sütunundaki ülke isimlerinden 'A' karakteri ile başlayıp 'a' karakteri ile sonlananları sıralayınız.

```sql
SELECT * FROM country 
WHERE country LIKE 'A%a' 
```

2. country tablosunda bulunan country sütunundaki ülke isimlerinden en az 6 karakterden oluşan ve sonu 'n' karakteri ile sonlananları sıralayınız.

```SQL
SELECT * FROM country 
WHERE country LIKE '_____%n' 
```

3. film tablosunda bulunan title sütunundaki film isimlerinden en az 4 adet büyük ya da küçük harf farketmesizin 'T' karakteri içeren film isimlerini sıralayınız.

```sql
SELECT * FROM film 
WHERE title ILIKE '%t%t%t%t%' 
```

4. film tablosunda bulunan tüm sütunlardaki verilerden title 'C' karakteri ile başlayan ve uzunluğu (length) 90 dan büyük olan ve rental_rate 2.99 olan verileri sıralayınız.

```sql
SELECT * FROM film 
WHERE title LIKE 'C%' AND length > 90 and rental_rate = 2.99 
```
---

## ÖDEV 4

1. film tablosunda bulunan replacement_cost sütununda bulunan birbirinden farklı değerleri sıralayınız.

```sql
SELECT DISTINCT replacement_cost FROM film 
```

2. film tablosunda bulunan replacement_cost sütununda birbirinden farklı kaç tane veri vardır?

```SQL
SELECT COUNT(DISTINCT replacement_cost) FROM film 
```

3. film tablosunda bulunan film isimlerinde (title) kaç tanesini T karakteri ile başlar ve aynı zamanda rating 'G' ye eşittir?

```sql
SELECT COUNT(*) FROM film
WHERE title LIKE 'T%' AND rating IN('G')
```

4. country tablosunda bulunan ülke isimlerinden (country) kaç tanesi 5 karakterden oluşmaktadır?

```sql
SELECT COUNT(*) FROM country 
WHERE country LIKE '_____'
```

5. city tablosundaki şehir isimlerinin kaçtanesi 'R' veya r karakteri ile biter?

```sql
SELECT COUNT(*) FROM city
WHERE city ILIKE '%R'

```
---

## ÖDEV 5

1. film tablosunda bulunan ve film ismi (title) 'n' karakteri ile biten en uzun (length) 5 filmi sıralayınız.

```sql
SELECT * FROM film
WHERE title LIKE '%n'
ORDER BY length DESC
LIMIT 5
```

2. film tablosunda bulunan ve film ismi (title) 'n' karakteri ile biten en kısa (length) ikinci 5 filmi sıralayınız.

```SQL
SELECT * FROM film
WHERE title LIKE '%n'
ORDER BY length
OFFSET 5
LIMIT 5
```

3. customer tablosunda bulunan last_name sütununa göre azalan yapılan sıralamada store_id 1 olmak koşuluyla ilk 4 veriyi sıralayınız.

```sql
SELECT * FROM customer
WHERE store_id = 1
ORDER BY last_name DESC
LIMIT 4
```
---



