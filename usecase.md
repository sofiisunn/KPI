```mermaid
graph TD

    Client((Клієнт))
    PaymentService((Платіжна система))
    DeliveryService((Служба доставки))

    Client --> UC1[Додати товар у кошик]
    Client --> UC2[Оформити замовлення]
    Client --> UC3[Переглянути каталог косметики]
    Client --> UC4[Ввести дані акаунта]
    Client --> UC5[Авторизуватися]

    PaymentService --> UC6[Фіксувати транзакцію]
    PaymentService --> UC10[Обробити статус оплати]

    DeliveryService --> UC11[Згенерувати трек-номер]

    UC1 --> UC7[Попередження про ліміт кошика]

    UC2 --> UC11
    UC2 --> UC8[Авторизація користувача]
    UC2 --> UC9[Перевірка адреси доставки]
