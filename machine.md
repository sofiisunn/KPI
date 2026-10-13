```mermaid
stateDiagram-v2
    [*] --> Draft : Клієнт натиснув кнопку "Оформити замовлення"

    Draft --> Validated : validateAddress()
    Draft --> Paying : processPayment()
```
