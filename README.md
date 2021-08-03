# Patika.dev SQL Ödevleri

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
