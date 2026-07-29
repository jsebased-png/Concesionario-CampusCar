# Vehicle Sales & Maintenance Database

## 📌 Descripción
Este proyecto define el diseño de una base de datos para gestionar la **venta de vehículos**, el **registro de clientes y vendedores**, y el **mantenimiento de los automóviles**.  
El modelo está basado en un **diagrama entidad-relación (ERD)** que incluye entidades principales como `SELLER`, `CUSTOMER`, `SALE`, `SALEDETAIL`, `VEHICLE`, `MODEL`, `BRAND`, `CATALOG` y `MAINTENANCE`.

---

## 🗂️ Entidades y Atributos

### SELLER
- `seller_id` (PK)  
- `employee_number`  
- `name`  
- `hire_date`  
- `created_at`

### CUSTOMER
- `customer_id` (PK)  
- `name`  
- `phone`  
- `email`  
- `address`  
- `created_at`

### SALE
- `sale_id` (PK)  
- `customer_id` (FK)  
- `seller_id` (FK)  
- `sale_date`  
- `total`  
- `comments`  
- `created_at`

### SALEDETAIL
- `detail_id` (PK)  
- `sale_id` (FK)  
- `vehicle_id` (FK)  
- `sold_price`  
- `taxes`  
- `discount`  
- `quantity`

### VEHICLE
- `vehicle_id` (PK)  
- `vin`  
- `brand_id` (FK)  
- `model_id` (FK)  
- `year`  
- `list_price`  
- `color`  
- `status`  
- `availability`  
- `created_at`  
- `updated_at`

### MODEL
- `model_id` (PK)  
- `model_name`  
- `brand_id` (FK)

### BRAND
- `brand_id` (PK)  
- `brand_name`

### MAINTENANCE
- `maintenance_id` (PK)  
- `vehicle_id` (FK)  
- `customer_id` (FK)  
- `cost`  
- `service_date`  
- `notes`  
- `created_at`

### CATALOG
- `catalog_id` (PK)  
- `catalog_type`  
- `catalog_value`

---

## 🔗 Relaciones
- **SELLER** vende **SALE**  
- **CUSTOMER** realiza **SALE**  
- **SALE** contiene **SALEDETAIL**  
- **SALEDETAIL** incluye **VEHICLE**  
- **VEHICLE** pertenece a **MODEL**  
- **MODEL** pertenece a **BRAND**  
- **VEHICLE** tiene **MAINTENANCE**  
- **VEHICLE** usa **CATALOG**

---

## 🎯 Objetivo del Diseño
Este esquema permite:
- Gestionar clientes y vendedores.  
- Registrar ventas y detalles de cada transacción.  
- Controlar inventario de vehículos y sus características.  
- Llevar historial de mantenimientos asociados a cada vehículo.  
- Organizar catálogos de atributos (color, transmisión, combustible, etc.).  

---

## 🚀 Próximos pasos
- Implementar el modelo en PostgreSQL/MySQL.  
- Crear scripts de migración y carga inicial de datos.  
- Añadir índices y restricciones para optimizar consultas.  
- Documentar ejemplos de queries frecuentes (ventas por cliente, historial de mantenimiento, etc.).  
