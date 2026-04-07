# Insta THRIFT Creator Store — Database Design

A relational database for managing an Instagram-based thrift/handmade product store.

Eraser Link -> https://app.eraser.io/workspace/CmmcIY5dr1LXlZrnRO0E?origin=share

## Tables

| Table | Description |
|---|---|
| `customer` | Stores buyer info including Instagram handle, contact, and address |
| `products` | Catalog of thrifted/handmade items with type, category, size, condition, and media |
| `inventory` | Tracks available quantity per product |
| `orders` | Customer orders with total amount and optional rating |
| `order_items` | Line items linking products to orders with quantity and unit price |
| `payments` | Payment records per order (UPI, Card, COD) with status tracking |
| `shipping` | Shipping address and delivery status per order |

## Relationships

- A **customer** places many **orders**
- An **order** has many **order_items**
- A **product** appears in many **order_items**
- A **product** has one **inventory** record
- An **order** can have multiple **payments** (e.g. on retry after failure)
- An **order** has one **shipping** record

## Enums

- `product_type`: `thrifted`, `handmade`
- `category`: `Tops`, `Bottoms`, `Accessories`, `Home`, `Jewelry`
- `size`: `XS`, `S`, `M`, `L`, `XL`, `Free_Size`
- `condition`: `new_with_tags`, `excellent`, `good`, `fair`
- `payment_method`: `UPI`, `Card`, `COD`
- `payment_status`: `Pending`, `Paid`, `Failed`
- `shipping_status`: `confirmed`, `out_for_delivery`, `delivered`
