# MiniMarket Online — Backend

## 1. Descripción del proyecto

API básica para administrar los productos y registrar las compras realizadas desde la aplicación web MiniMarket Online. Este proyecto representa el trabajo del equipo backend.

## 2. Objetivo

Desarrollar una API REST que permita:

- Consultar los productos disponibles.
- Registrar una compra con sus productos y cantidades.
- Calcular el total de la compra en el servidor.

## 3. Tecnologías

- C# y .NET 8 Web API.
- Entity Framework Core.
- SQL Server.

Para simplificar el ejercicio, el docente puede permitir inicialmente una lista en memoria y agregar la base de datos en una segunda etapa.

## 4. Arquitectura base: 3 capas

El Backend se organizará en tres capas independientes:

1. **Presentación:** recibe las solicitudes HTTP y devuelve las respuestas. Contiene los Controllers.
2. **Lógica de negocio:** aplica las reglas del sistema, valida compras y calcula totales. Contiene los Services.
3. **Acceso a datos:** consulta y guarda información en la base de datos. Contiene el DbContext y los Repositories.

Flujo general:

`Cliente → Controllers → Services → Repositories → SQL Server`

## 5. Estructura de carpetas

```text
MiniMarket.Backend/
├── Controllers/
│   ├── ProductsController.cs
│   └── OrdersController.cs
├── Services/
│   ├── Interfaces/
│   │   ├── IProductService.cs
│   │   └── IOrderService.cs
│   └── Implementations/
│       ├── ProductService.cs
│       └── OrderService.cs
├── Data/
│   ├── MiniMarketDbContext.cs
│   └── Repositories/
│       ├── ProductRepository.cs
│       └── OrderRepository.cs
├── Models/
│   ├── Product.cs
│   ├── Order.cs
│   └── OrderItem.cs
├── DTOs/
│   └── CreateOrderDto.cs
├── Program.cs
└── README.md
```

### Responsabilidad de las carpetas

- `Controllers/`: define los endpoints de la API.
- `Services/`: implementa las reglas y operaciones del negocio.
- `Data/`: administra la conexión y el acceso a SQL Server.
- `Models/`: representa las entidades principales.
- `DTOs/`: define los datos que se reciben o envían por la API.

## 6. Modelo básico de datos

### Product

- `Id`: identificador.
- `Name`: nombre del producto.
- `Description`: descripción corta.
- `Price`: precio.
- `Stock`: unidades disponibles.

### Order

- `Id`: identificador.
- `CreatedAt`: fecha de creación.
- `Total`: valor total de la compra.

### OrderItem

- `Id`: identificador.
- `OrderId`: compra relacionada.
- `ProductId`: producto comprado.
- `Quantity`: cantidad.
- `UnitPrice`: precio al momento de la compra.

## 7. Endpoints requeridos

| Método | Endpoint | Descripción |
|---|---|---|
| GET | `/api/products` | Lista los productos disponibles |
| GET | `/api/products/{id}` | Consulta un producto |
| POST | `/api/orders` | Registra una compra simulada |

### Ejemplo de solicitud para registrar una compra

```json
{
  "items": [
    { "productId": 1, "quantity": 2 },
    { "productId": 3, "quantity": 1 }
  ]
}
```

El backend valida que los productos existan y que las cantidades sean válidas.

El total debe calcularse en el servidor, no confiarse al valor enviado por el frontend.

## 8. Tareas del equipo Backend

- Crear el proyecto Web API.
- Definir los modelos básicos.
- Crear los endpoints indicados.
- Agregar datos iniciales de prueba.
- Validar los datos recibidos.
- Probar los endpoints con Swagger.

## 9. Criterios de aceptación

- La API devuelve una lista de productos.
- Se puede consultar un producto por su identificador.
- Se puede registrar una compra válida.
- La API calcula y devuelve el total de la compra.
- Las solicitudes inválidas reciben una respuesta de error comprensible.

## 10. Entrega

El equipo debe entregar el repositorio Git con el código fuente y este README. Documentar los avances mediante commits claros.

> **Alcance académico:** no se implementan pagos reales, autenticación, facturación ni integración con servicios externos.