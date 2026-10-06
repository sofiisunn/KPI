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
