# Специфікація вимог (spec.md)

## 1. Список сутностей та атрибутів
Сутності:
  Товар, бренд, категорія, клієнт, замовлення, елемент замовлення
Атрибути сутностей:
  Product (товар):
•	product_id – унікальний ідентифікатор товару (primary key)
•	brand_id – бренд до якого належить товар (foreign key)
•	category_id – категорія до якої належить товар (foreign key)
•	product_title – назва продукту
•	product_price – ціна продукту
•	product_pao_months – термін придатності після відкриття у місяцях
•	product_application_method – спосіб застосування
•	product_volume – об’єм продукту
  Brand (бренд):
•	brand_id – унікальний ідентифікатор бренду (primary key)
•	brand_title – назва бренду
  Category (категорія):
•	category_id – унікальний ідентифікатор категорії (primary key)
•	category_title – назва категорії
  Customer (клієнт):
•	customer_id – унікальний ідентифікатор клієнта (primary key)
•	customer_first_name – ім’я клієнта
•	customer_last_name – прізвище клієнта
•	customer_birth_date – дата народження
•	customer_phone_number – номер телефону
•	customer_email – електронна пошта
  Order (замовлення):
•	order_id – унікальний ідентифікатор замовлення (primary key)
•	customer_id – клієнт, який зробив замовлення (foreign key)
•	order_date – дата, коли було оформлене замовлення
•	order_status – статус замовлення
•	order_delivery_address – адреса для доставки
•	order_price – загальна вартість замовлення
  Order Item (елемент замовлення): 
•	order_item_id – унікальний ідентифікатор елемента замовлення (primary key)
•	product_id – який це саме продукт (foreign key)
•	order_id – до якого замовлення належить елемент (foreign key)
•	order_item_quantity – кількість продуктів в замовленні
•	order_item_price – ціна на момент оформлення замовлення
