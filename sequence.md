```mermaid
sequenceDiagram
    actor Customer as Клієнт
    participant CheckoutPage as Сторінка замовлення
    participant OrderController as Сервер
    participant Database as База Даних
    actor PaymentService as Платіжна система
    actor DeliveryService as Служба доставки 

    Customer->>CheckoutPage: Відкриває сторінку оформлення замовлення
    CheckoutPage->>OrderController: getCustomerProfile(customer_id)
    OrderController->>Database: Зчитування особистих даних клієнта
    Database-->>OrderController: Повернення (ім'я, прізвище, дата народження, телефон, електронна пошта)
    OrderController-->>CheckoutPage: Заповнені дані профілю клієнта

    Customer->>CheckoutPage: Вносить адресу доставки та підтверджує замовлення
    CheckoutPage->>OrderController: submitOrder(customer_id, delivery_address)
    
    OrderController->>PaymentService: processPayment(order_id, order_price)
    OrderController->>OrderController: validateAddress()
    
    OrderController->>Database: createOrderRecord()
    Database-->>OrderController: Замовлення успішно створено (order_id)
    OrderController->>Database: recordItemsPrice()
```
