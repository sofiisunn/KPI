```mermaid
graph TD
    Client((Клієнт)) --> UC1[Додати товар у кошик]
    Client --> UC2[Оформити замовлення]

    PaymentService((Платіжна система)) --> UC3[Фіксація транзакції]
