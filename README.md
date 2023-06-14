

1- city tablosu ile country tablosunda bulunan şehir (city) ve ülke (country) isimlerini birlikte görebileceğimiz LEFT JOIN sorgusunu yazınız.
```sh
SELECT city, country FROM city
LEFT JOIN country ON city.country_id=country.country_id;
```
2- customer tablosu ile payment tablosunda bulunan payment_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz RIGHT JOIN sorgusunu yazınız.
```sh
SELECT payment_id, first_name last_name FROM customer
RIGHT JOIN payment ON payment.customer_id=customer.customer_id;
```
3- customer tablosu ile rental tablosunda bulunan rental_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz FULL JOIN sorgusunu yazınız.
```sh
SELECT rental_id, first_name, last_name FROM customer
FULL JOIN rental ON rental.customer_id=customer.customer_id;
```


1- actor ve customer tablolarında bulunan first_name sütunları için tüm verileri sıralayalım.
```sh
(
	SELECT first_name FROM actor
)
UNION
(
	SELECT first_name FROM customer
);

```
2- actor ve customer tablolarında bulunan first_name sütunları için kesişen verileri sıralayalım.
```sh
(
	SELECT first_name FROM actor
)
INTERSECT
(
	SELECT first_name FROM customer
);
```
3- actor ve customer tablolarında bulunan first_name sütunları için ilk tabloda bulunan ancak ikinci tabloda bulunmayan verileri sıralayalım.
```sh
(
	SELECT first_name FROM actor
)
EXCEPT
(
	SELECT first_name FROM customer
);
```
4- İlk 3 sorguyu tekrar eden veriler için de yapalım.
```sh
(
	SELECT first_name FROM actor
)
UNION ALL
(
	SELECT first_name FROM customer
);

(
	SELECT first_name FROM actor
)
INTERSECT ALL
(
	SELECT first_name FROM customer
);

(
	SELECT first_name FROM actor
)
EXCEPT ALL
(
	SELECT first_name FROM customer
);
```
