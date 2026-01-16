# Restaurant Management System

Sistema de gestión para restaurantes desarrollado con **Spring Boot (Backend)** y **Java Swing (Cliente)**, siguiendo una **arquitectura limpia / hexagonal** para mantener separación clara de responsabilidades.

---

## Arquitectura General

El proyecto está dividido en **dos módulos principales**:

1. **Backend – API REST (Spring Boot)**
2. **Cliente de Escritorio – Java Swing**

Cada módulo es independiente y se comunica mediante HTTP/JSON.

---

##  Backend – Spring Boot

Ruta del proyecto:

```
restaurant-management/
```

###  Estructura del Proyecto

```
restaurant-management/
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── com/restaurant/management/
│   │   │
│   │   │       ├── RestaurantManagementApplication.java
│   │   │
│   │   │       ├── config/                    # Configuración global
│   │   │       │   ├── SecurityConfig.java
│   │   │       │   ├── JwtConfig.java
│   │   │       │   ├── SwaggerConfig.java
│   │   │       │   ├── CorsConfig.java
│   │   │       │   └── ModelMapperConfig.java
│   │   │
│   │   │       ├── common/                    # Elementos compartidos
│   │   │       │   ├── constants/
│   │   │       │   │   └── ApiConstants.java
│   │   │       │   ├── exceptions/
│   │   │       │   │   ├── BusinessException.java
│   │   │       │   │   ├── NotFoundException.java
│   │   │       │   │   └── UnauthorizedException.java
│   │   │       │   └── response/
│   │   │       │       ├── ApiResponse.java
│   │   │       │       └── ErrorResponse.java
│   │   │
│   │   │       ├── domain/                    #  CORE DEL NEGOCIO
│   │   │       │   ├── model/
│   │   │       │   │   ├── Usuario.java
│   │   │       │   │   ├── Rol.java
│   │   │       │   │   ├── Mesa.java
│   │   │       │   │   ├── Producto.java
│   │   │       │   │   ├── Pedido.java
│   │   │       │   │   ├── PedidoDetalle.java
│   │   │       │   │   ├── Venta.java
│   │   │       │   │   └── Inventario.java
│   │   │       │   ├── repository/
│   │   │       │   │   ├── UsuarioRepository.java
│   │   │       │   │   ├── PedidoRepository.java
│   │   │       │   │   ├── ProductoRepository.java
│   │   │       │   │   └── MesaRepository.java
│   │   │       │   └── service/
│   │   │       │       ├── PedidoDomainService.java
│   │   │       │       ├── VentaDomainService.java
│   │   │       │       └── InventarioDomainService.java
│   │   │
│   │   │       ├── application/               #  CASOS DE USO
│   │   │       │   ├── usecase/
│   │   │       │   │   ├── pedido/
│   │   │       │   │   │   ├── CrearPedidoUseCase.java
│   │   │       │   │   │   ├── AgregarProductoUseCase.java
│   │   │       │   │   │   └── CerrarPedidoUseCase.java
│   │   │       │   │   ├── venta/
│   │   │       │   │   │   └── CobrarPedidoUseCase.java
│   │   │       │   │   └── auth/
│   │   │       │   │       └── LoginUseCase.java
│   │   │       │   ├── dto/
│   │   │       │   │   ├── request/
│   │   │       │   │   │   ├── PedidoRequestDTO.java
│   │   │       │   │   │   └── LoginRequestDTO.java
│   │   │       │   │   └── response/
│   │   │       │   │       ├── PedidoResponseDTO.java
│   │   │       │   │       └── LoginResponseDTO.java
│   │   │       │   └── mapper/
│   │   │       │       ├── PedidoMapper.java
│   │   │       │       └── UsuarioMapper.java
│   │   │
│   │   │       ├── infrastructure/            #  IMPLEMENTACIONES
│   │   │       │   ├── persistence/
│   │   │       │   │   ├── entity/
│   │   │       │   │   │   ├── PedidoEntity.java
│   │   │       │   │   │   ├── ProductoEntity.java
│   │   │       │   │   │   └── UsuarioEntity.java
│   │   │       │   │   └── repository/
│   │   │       │   │       ├── JpaPedidoRepository.java
│   │   │       │   │       ├── JpaProductoRepository.java
│   │   │       │   │       └── JpaUsuarioRepository.java
│   │   │       │   ├── security/
│   │   │       │   │   ├── JwtFilter.java
│   │   │       │   │   └── JwtProvider.java
│   │   │       │   └── external/
│   │   │       │       └── PaymentServiceClient.java
│   │   │
│   │   │       ├── presentation/              #  API REST
│   │   │       │   ├── controller/
│   │   │       │   │   ├── PedidoController.java
│   │   │       │   │   ├── VentaController.java
│   │   │       │   │   └── AuthController.java
│   │   │       │   └── advice/
│   │   │       │       └── GlobalExceptionHandler.java
│   │   │
│   │   └── resources/
│   │       ├── application.yml
│   │       ├── data.sql
│   │       └── schema.sql
│   │
│   └── test/
│       └── java/com/restaurant/management/
│           ├── domain/
│           ├── application/
│           └── presentation/
│
├── pom.xml
└── README.md
```

---

## Cliente – Java Swing

Ruta del proyecto:

```
restaurant-swing-client/
```

###  Estructura del Cliente

```
restaurant-swing-client/
├── src/
│   ├── main/
│   │   ├── java/com/restaurant/client/
│   │   │   ├── Main.java
│   │   │   ├── config/
│   │   │   │   └── ApiConfig.java
│   │   │   ├── view/
│   │   │   │   ├── login/LoginFrame.java
│   │   │   │   ├── dashboard/DashboardFrame.java
│   │   │   │   ├── pedido/PedidoPanel.java
│   │   │   │   └── cocina/CocinaPanel.java
│   │   │   ├── controller/
│   │   │   │   ├── LoginController.java
│   │   │   │   └── PedidoController.java
│   │   │   ├── service/
│   │   │   │   ├── AuthService.java
│   │   │   │   └── PedidoService.java
│   │   │   ├── dto/
│   │   │   │   ├── PedidoDTO.java
│   │   │   │   └── UsuarioDTO.java
│   │   │   └── util/
│   │   │       ├── HttpClientUtil.java
│   │   │       └── SessionManager.java
│   │   └── resources/icons/
│   └── test/
│
└── pom.xml
```

---

##  Objetivo del Proyecto

* Gestión de pedidos
* Control de mesas
* Autenticación con roles
* Ventas e inventario
* Cliente de escritorio para operación del restaurante

---

## Estado Actual

**Sprint 0 – Estructura base y arquitectura**
