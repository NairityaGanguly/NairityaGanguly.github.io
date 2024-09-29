erDiagram
    PRODUCT {
        string product_id PK
        string name
        string brand
        float price
        string category
    }
    CUSTOMER {
        string customer_id PK
        string name
        string email
        string phone
    }
    SALE {
        string sale_id PK
        string product_id FK
        string customer_id FK
        date sale_date
        int quantity
        float total_price
    }
    INVENTORY {
        string inventory_id PK
        string product_id FK
        int stock_quantity
        date last_updated
    }

    PRODUCT ||--o{ SALE : "is purchased in"
    CUSTOMER ||--o{ SALE : "makes"
    PRODUCT ||--|| INVENTORY : "has"
	
