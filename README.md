# Lab 3

## Завдання 1
> Напишіть SQL команду, за допомогою якої можна:
> - вибрати всі стовпчики (За допомогою wildcard “*”) з таблиці `products`;
  
```sql
select * from products;
```
> - вибрати тільки стовпчики name, phone з таблиці shippers
   
```sql
select name, phone from shippers;
```
## Завдання 2
>Напишіть SQL команду, за допомогою якої можна знайти середнє, максимальне та мінімальне значення стовпчика `price`
>таблички `products`
```sql
select min(price) as minimalPrice,
       avg(price) as averagePrice,
       max(price) as maximalPrice
from products;
```

## Завдання 3
>Напишіть SQL команду, за допомогою якої можна обрати унікальні значення колонок `category_id` та `price` таблиці `products`.
>Оберіть порядок виведення на екран за спаданням значення price та виберіть тільки 10 рядків

```sql
select distinct category_id, price
from products
order by price desc
limit 10;
```
## Завдання 4
>Напишіть SQL команду, за допомогою якої можна знайти кількість продуктів (рядків), які знаходиться в цінових межах від
>20 до 100.

```sql
select count(id) as productAmount
from products
where price >= 20 and price <= 100;
```

## Завдання 5
>Напишіть SQL команду, за допомогою якої можна знайти кількість продуктів (рядків) та середню ціну (price) у кожного
>постачальника `supplier_id`.
```sql
select supplier_id,
       count(id) as productAmount,
       avg(price) as avaragePrice
from products
group by supplier_id;
```
