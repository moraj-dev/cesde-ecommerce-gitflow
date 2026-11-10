# MiniMarket Online — Frontend

## 1. Descripción del proyecto

Aplicación web básica para consultar productos y simular compras en línea. Este proyecto se desarrolla como ejercicio académico y representa el trabajo del equipo frontend.

## 2. Objetivo

Construir una interfaz sencilla donde el usuario pueda:

- Ver el listado de productos.
- Consultar el nombre, precio y descripción de cada producto.
- Agregar productos a un carrito.
- Registrar una compra simulada.

## 3. Tecnologías

- HTML5
- CSS3
- JavaScript
- Fetch API para consumir el backend.

## 4. Arquitectura base: 3 capas

El frontend se organizará en tres capas para separar responsabilidades:

1. **Presentación:** muestra las pantallas y recibe las acciones del usuario.
2. **Lógica de aplicación:** coordina las acciones, administra el carrito y calcula los totales.
3. **Acceso a datos:** se comunica con el Backend mediante solicitudes HTTP.

## 5. Estructura de carpetas

```text
minimarket-frontend/
├── index.html
├── README.md
├── assets/
│   └── images/
├── css/
│   └── styles.css
└── js/
    ├── presentation/
    │   ├── productsView.js
    │   └── cartView.js
    ├── application/
    │   └── cartManager.js
    └── services/
        └── apiService.js
```

### Responsabilidad de las carpetas

- `presentation/`: renderiza productos y carrito en la interfaz.
- `application/`: contiene la lógica del carrito y las operaciones de compra.
- `services/`: realiza las peticiones HTTP a la API.
- `assets/` y `css/`: almacenan imágenes y estilos visuales.

## 6. Pantallas principales

1. **Inicio:** listado de productos.
2. **Carrito:** productos seleccionados y total.
3. **Confirmación:** mensaje con el resultado de la compra.

## 7. Integración con Backend

La aplicación consumirá una API REST.

Dirección local de ejemplo:

`https://localhost:7001/api`

Endpoints necesarios:

- `GET /products` — consultar productos.
- `POST /orders` — registrar una compra.

El frontend debe mostrar un mensaje sencillo cuando ocurra un error al consultar o registrar información.

## 8. Tareas del equipo Frontend

- Crear la estructura de archivos del proyecto.
- Diseñar las pantallas con estilos básicos.
- Mostrar los productos recibidos desde la API.
- Implementar el carrito y el cálculo del total.
- Enviar la compra al backend.
- Probar el flujo completo.

## 9. Criterios de aceptación

- Se visualizan los productos disponibles.
- El usuario puede agregar y quitar productos del carrito.
- El total se actualiza correctamente.
- Se puede enviar una compra simulada.
- La interfaz funciona en un navegador de escritorio.

## 10. Entrega

El equipo debe entregar el repositorio Git con el código fuente y este README. Incluir commits pequeños que describan los avances realizados.

> **Alcance académico:** no se implementan pagos reales, inicio de sesión ni gestión avanzada de inventario.