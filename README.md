# Patika_SQL_Odevler
Bu repo Patika SQL Dersi kapsamında hazırlanan ödevleri içermektedir.
## SQL Ödev 1 

1. **film** tablosunda bulunan **title** ve **description** sütunlarındaki verileri sıralayınız.
   
   ```
   SELECT title, description FROM film;
   ```
   
3. **film** tablosunda bulunan tüm sütunlardaki verileri film uzunluğu (length) 60 dan büyük **VE** 75 ten küçük olma koşullarıyla sıralayınız.
   ```
   SELECT * FROM film
   WHERE length > 60 AND length < 75;
   
   ```
4. **film** tablosunda bulunan tüm sütunlardaki verileri rental_rate 0.99 __VE__ replacement_cost 12.99 __VEYA__ 28.99 olma koşullarıyla sıralayınız.
   ```
   SELECT * FROM film
   WHERE rental_rate = 0.99 AND (replacement_cost = 12.99 OR replacement_cost= 28.99);
   
   ```
5. **customer** tablosunda bulunan first_name sütunundaki değeri 'Mary' olan müşterinin last_name sütunundaki değeri nedir?
   ```
   SELECT last_name FROM customer
   WHERE first_name = 'Mary';

   ```
6. **film**  tablosundaki uzunluğu(length) 50 ten büyük **OLMAYIP** aynı zamanda rental_rate değeri 2.99 **veya** 4.99 OLMAYAN verileri sıralayınız.
   ```
    SELECT * FROM film
    WHERE NOT (length > 50) AND NOT (rental_rate = 2.99 OR rental_rate = 4.99 );

   ```

## SQL ÖDEV 2

1. **film** tablosunda bulunan tüm sütunlardaki verileri replacement cost değeri 12.99 dan büyük eşit ve 16.99 küçük olma koşuluyla sıralayınız ( BETWEEN - AND 
   yapısını kullanınız.)
    
   ```
   SELECT * FROM film
   WHERE replacement_cost BETWEEN 12.99 AND 16.99 ;

   ```
2. **actor** tablosunda bulunan first_name ve last_name sütunlardaki verileri first_name 'Penelope' veya 'Nick' veya 'Ed' değerleri olması koşuluyla sıralayınız.
    ( IN operatörünü kullanınız)
   
   ```
   SELECT first_name, last_name FROM actor
   WHERE first_name IN ('Penelope', 'Nick', 'Ed') ;

   ```
3. **film** tablosunda bulunan tüm sütunlardaki verileri rental_rate 0.99, 2.99, 4.99 VE replacement_cost 12.99, 15.99, 28.99 olma koşullarıyla sıralayınız. ( IN 
     operatörünü kullanınız.)
   
   ```
   SELECT * FROM film
   WHERE rental_rate IN (0.99,2.99,4.99) AND replacement_cost IN (12.99, 15.99, 28.99) ;

   ```
## SQL ÖDEV 3

1. **country** tablosunda bulunan **country** sütunundaki ülke isimlerinden 'A' karakteri ile başlayıp 'a' karakteri ile sonlananları sıralayınız.

    ```
    SELECT * FROM country
    WHERE country LIKE 'A%a';

    ```
2.  **country** tablosunda bulunan **country** sütunundaki ülke isimlerinden en az 6 karakterden oluşan ve sonu 'n' karakteri ile sonlananları sıralayınız.

     ```
     SELECT * FROM country
     WHERE country LIKE '____%_n';

     ```
3. **film** tablosunda bulunan **title** sütunundaki film isimlerinden en az 4 adet büyük ya da küçük harf farketmesizin 'T' karakteri içeren film isimlerini 
   sıralayınız.

    ```
    SELECT * FROM film
    WHERE title ILIKE '%t%T%t%T%';

    ```
4. **film** tablosunda bulunan tüm sütunlardaki verilerden **title** 'C' karakteri ile başlayan ve uzunluğu (length) 90 dan büyük olan ve rental_rate 2.99 olan
    verileri sıralayınız.

    ```
    SELECT * FROM film
    WHERE title LIKE 'C%'
    AND length > 90 AND rental_rate = 2.99;

    ```
   
## SQL Ödev 4

1. **film** tablosunda bulunan replacement_cost sütununda bulunan birbirinden farklı değerleri sıralayınız.

    ```
    SELECT DISTINCT replacement_cost FROM film;
    
    ```
2. **film** tablosunda bulunan replacement_cost sütununda birbirinden farklı kaç tane veri vardır?
   
    ```
    SELECT COUNT (DISTINCT replacement_cost) FROM film;
    
    ```
3. **film** tablosunda bulunan film isimlerinde (title) kaç tanesini T karakteri ile başlar ve aynı zamanda rating 'G' ye eşittir?
   
    ```
    SELECT COUNT(*) FROM film
    WHERE title LIKE ('T%') AND rating = 'G';
    
    ```
4. **country** tablosunda bulunan ülke isimlerinden (country) kaç tanesi 5 karakterden oluşmaktadır?

   ```
    SELECT COUNT(*) FROM country
    WHERE country LIKE '_____';
    
    ```
5. **city** tablosundaki şehir isimlerinin kaç tanesi 'R' veya r karakteri ile biter?

    ```
    SELECT COUNT(*) FROM city
    WHERE city ILIKE '%r';
    
    ```
## SQL ÖDEV 5

1. **film** tablosunda bulunan ve film ismi (title) 'n' karakteri ile biten en uzun (length) 5 filmi sıralayınız.
   
    ```
    SELECT  * FROM film
    WHERE title LIKE '%n'
    ORDER BY length DESC
    LIMIT 5;
    
    ```
2. **film** tablosunda bulunan ve film ismi (title) 'n' karakteri ile biten en kısa (length) ikinci(6,7,8,9,10) 5 filmi(6,7,8,9,10) sıralayınız.
   
    ```
    SELECT  * FROM film
    WHERE title LIKE '%n'
    ORDER BY length
    OFFSET 5
    LIMIT 5;
    
    ```
3. **customer** tablosunda bulunan last_name sütununa göre azalan yapılan sıralamada store_id 1 olmak koşuluyla ilk 4 veriyi sıralayınız.
   
    ```
    SELECT  * FROM customer
    WHERE store_id = 1 
    ORDER BY last_name DESC
    LIMIT 4;
    
    ```
    
## SQL ÖDEV 6

1. **film** tablosunda bulunan rental_rate sütunundaki değerlerin ortalaması nedir?

   ```
    SELECT AVG(rental_rate)  FROM film;
    
    ```
2. **film** tablosunda bulunan filmlerden kaç tanesi 'C' karakteri ile başlar?
   
    ```
    SELECT  COUNT(*) FROM film
    WHERE title LINK 'C%';
    
    ```
3. **film** tablosunda bulunan filmlerden rental_rate değeri 0.99 a eşit olan en uzun (length) film kaç dakikadır?

   ```
    SELECT MAX(length) FROM film
    WHERE rental_rate = 0.99;
    
    ```
4. **film** tablosunda bulunan filmlerin uzunluğu 150 dakikadan büyük olanlarına ait kaç farklı replacement_cost değeri vardır?
 
   ```
    SELECT DISTINCT (replacement_cost) FROM film
    WHERE length > 150;
    
    ```

## SQL ÖDEV 7

1. **film** tablosunda bulunan filmleri rating değerlerine göre gruplayınız.

   ```
    SELECT rating, COUNT(*) FROM film
    GROUP BY raiting;
    
    ```
2. **film** tablosunda bulunan filmleri replacement_cost sütununa göre grupladığımızda film sayısı 50 den fazla olan replacement_cost değerini ve karşılık gelen 
     film sayısını sıralayınız.

    ```
    SELECT replacement_cost, COUNT(*) FROM film
    GROUP BY replacement_cost
    HAVING replacement_cost > 50;
    
    ```
3. **customer** tablosunda bulunan store_id değerlerine karşılık gelen müşteri sayılarını nelerdir?
   
    ```
    SELECT store_id COUNT(*) FROM customer
    GROUP BY store_id;
    
    ```
4. **city** tablosunda bulunan şehir verilerini country_id sütununa göre gruplandırdıktan sonra en fazla şehir sayısı barındıran country_id bilgisini ve şehir 
   sayısını paylaşınız.

   ```
    SELECT  country_id COUNT(*) FROM city
    GROUP BY country_id
    ORDER BY COUNT(*) DESC
    LIMIT 1;
    
    ```
   
## SQL Ödev 4

1. **test** veritabanınızda **employee** isimli sütun bilgileri id(INTEGER), name VARCHAR(50), birthday DATE, email VARCHAR(100) olan bir tablo oluşturalım.

    ```
     CREATE TABLE employee (
     id INTEGER PRIMARY KEY,
     name VARCHAR(50),
     birthday DATE,
     email VARCHAR(100)	
      );
    
    ```
2. Oluşturduğumuz **employee** tablosuna 'Mockaroo' servisini kullanarak 50 adet veri ekleyelim.

    ```
      insert into employee (id , name, birthday, email) values (1, 'Cathleen Spalton', '1994-03-24', 'cspalton0@dedecms.com');
      insert into employee (id , name, birthday, email) values (2, 'Zelig Coggill', '1965-07-26', 'zcoggill1@ucsd.edu');
      insert into employee (id , name, birthday, email) values (3, 'Lanny Fairhead', '1929-05-14', 'lfairhead2@techcrunch.com');
      insert into employee (id , name, birthday, email) values (4, 'Idette Kilius', '1940-05-13', 'ikilius3@sun.com');
      insert into employee (id , name, birthday, email) values (5, 'Ann-marie Yedall', '1957-04-17', 'ayedall4@google.cn');
      insert into employee (id , name, birthday, email) values (6, 'Bronnie Kenneford', '1966-03-14', 'bkenneford5@netlog.com');
      insert into employee (id , name, birthday, email) values (7, 'Osborn Batty', '1926-12-26', 'obatty6@i2i.jp');
      insert into employee (id , name, birthday, email) values (8, 'Orly Lealle', '1922-07-27', 'olealle7@themeforest.net');
      insert into employee (id , name, birthday, email) values (9, 'Stefa Vernham', '1914-05-02', 'svernham8@spiegel.de');
      insert into employee (id , name, birthday, email) values (10, 'Hyacinth Yearron', '1933-05-02', 'hyearron9@deliciousdays.com');
      insert into employee (id , name, birthday, email) values (11, 'Kirby Ellington', '1996-05-20', 'kellingtona@biglobe.ne.jp');
      insert into employee (id , name, birthday, email) values (12, 'Trenton Fishbourn', '1927-06-01', 'tfishbournb@livejournal.com');
      insert into employee (id , name, birthday, email) values (13, 'Hermon Sollett', '1952-12-11', 'hsollettc@huffingtonpost.com');
      insert into employee (id , name, birthday, email) values (14, 'Brewer Cockley', '1952-11-21', 'bcockleyd@barnesandnoble.com');
      insert into employee (id , name, birthday, email) values (15, 'Clemence Bollon', '1923-12-06', 'cbollone@intel.com');
      insert into employee (id , name, birthday, email) values (16, 'Loralyn Jost', '1961-07-29', 'ljostf@statcounter.com');
      insert into employee (id , name, birthday, email) values (17, 'Miner MacCallam', '1913-09-26', 'mmaccallamg@yahoo.co.jp');
      insert into employee (id , name, birthday, email) values (18, 'Mamie Buten', '1920-08-04', 'mbutenh@desdev.cn');
      insert into employee (id , name, birthday, email) values (19, 'Crystie Lumb', '1932-02-25', 'clumbi@de.vu');
      insert into employee (id , name, birthday, email) values (20, 'Glenden Argabrite', '1953-07-17', 'gargabritej@purevolume.com');
      insert into employee (id , name, birthday, email) values (21, 'Garvy Vittori', '1981-09-17', 'gvittorik@go.com');
      insert into employee (id , name, birthday, email) values (22, 'Rubin Rickeard', '1966-01-23', 'rrickeardl@ftc.gov');
      insert into employee (id , name, birthday, email) values (23, 'Ruggiero Rising', '1988-02-28', 'rrisingm@tuttocitta.it');
      insert into employee (id , name, birthday, email) values (24, 'Garfield Sarney', '1910-06-10', 'gsarneyn@craigslist.org');
      insert into employee (id , name, birthday, email) values (25, 'Kitti Fillimore', '1992-04-19', 'kfillimoreo@godaddy.com');
      insert into employee (id , name, birthday, email) values (26, 'Tobie Nickerson', '1995-10-01', 'tnickersonp@zimbio.com');
      insert into employee (id , name, birthday, email) values (27, 'Concordia McMurty', '1987-11-22', 'cmcmurtyq@sogou.com');
      insert into employee (id , name, birthday, email) values (28, 'Cacilie Cussins', '1901-04-26', 'ccussinsr@answers.com');
      insert into employee (id , name, birthday, email) values (29, 'Lusa De la Yglesia', '1987-12-13', 'ldes@multiply.com');
      insert into employee (id , name, birthday, email) values (30, 'Nerta Woodhead', '1984-08-11', 'nwoodheadt@dedecms.com');
      insert into employee (id , name, birthday, email) values (31, 'Eduard Sircomb', '1963-11-22', 'esircombu@blogspot.com');
      insert into employee (id , name, birthday, email) values (32, 'Joanne Charity', '1914-09-24', 'jcharityv@utexas.edu');
      insert into employee (id , name, birthday, email) values (33, 'Ysabel Patriskson', '1985-05-30', 'ypatrisksonw@squarespace.com');
      insert into employee (id , name, birthday, email) values (34, 'Dory MacInnes', '1953-06-16', 'dmacinnesx@go.com');
      insert into employee (id , name, birthday, email) values (35, 'Jan Filppetti', '1922-04-19', 'jfilppettiy@indiegogo.com');
      insert into employee (id , name, birthday, email) values (36, 'Lemmie Piwell', '1936-02-15', 'lpiwellz@ezinearticles.com');
      insert into employee (id , name, birthday, email) values (37, 'Laney Axtens', '1956-09-30', 'laxtens10@fema.gov');
      insert into employee (id , name, birthday, email) values (38, 'Susette Wisedale', '1907-05-10', 'swisedale11@ow.ly');
      insert into employee (id , name, birthday, email) values (39, 'Corbie Greguol', '1924-08-02', 'cgreguol12@imgur.com');
      insert into employee (id , name, birthday, email) values (40, 'Cosette Ranfield', '1936-10-28', 'cranfield13@theglobeandmail.com');
      insert into employee (id , name, birthday, email) values (41, 'Adan Lyles', '1960-12-07', 'alyles14@netvibes.com');
      insert into employee (id , name, birthday, email) values (42, 'Oneida Bartali', '1946-07-12', 'obartali15@joomla.org');
      insert into employee (id , name, birthday, email) values (43, 'Dun Battany', '1965-06-22', 'dbattany16@eventbrite.com');
      insert into employee (id , name, birthday, email) values (44, 'Ferdy Izhakov', '1946-04-27', 'fizhakov17@github.io');
      insert into employee (id , name, birthday, email) values (45, 'Drusilla Alstead', '1962-01-16', 'dalstead18@hostgator.com');
      insert into employee (id , name, birthday, email) values (46, 'Wendy Jacquet', '1976-08-15', 'wjacquet19@foxnews.com');
      insert into employee (id , name, birthday, email) values (47, 'Constantia Nelson', '1999-06-17', 'cnelson1a@netlog.com');
      insert into employee (id , name, birthday, email) values (48, 'Riordan Berlin', '1911-06-24', 'rberlin1b@yellowbook.com');
      insert into employee (id , name, birthday, email) values (49, 'Fina Shieber', '1971-06-24', 'fshieber1c@census.gov');
      insert into employee (id , name, birthday, email) values (50, 'Melisande Sollars', '1921-04-17', 'msollars1d@miibeian.gov.cn');
    ```
3. Sütunların her birine göre diğer sütunları güncelleyecek 5 adet UPDATE işlemi yapalım.

   ```
    UPDATE employee
	 SET name = 'Mevlüt'
	 WHERE id = '2';
    
    ```
    ```
     UPDATE employee
	  SET name = 'İzmirli'
	  WHERE id = '3';
    
    ```
    ```
     UPDATE employee
	  SET name = 'Patika'
	  WHERE id = '21';
    
    ```
    ```
     UPDATE employee
	  SET name = 'SQL'
	  WHERE id = '34';
    
    ```
    ```
     UPDATE employee
	  SET name = 'MMM'
	  WHERE name LIKE  = 'R%';
    
     ```

4. Sütunların her birine göre ilgili satırı silecek 5 adet DELETE işlemi yapalım.

    ```
     DELETE FROM employee
     WHERE id = 2;
    
    ```
    ```
     DELETE FROM employee
     WHERE id = 22;
    
    ```
    ```
     DELETE FROM employee
     WHERE id = 32;
    
    ```
    ```
     DELETE FROM employee
     WHERE id = 42;
    
    ```
    ```
     DELETE FROM employee
     WHERE id = 29;
    
    ```


   



   



   




   

   
 








   

   
