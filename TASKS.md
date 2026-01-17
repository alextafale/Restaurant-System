# Tasks – Fin de Semana (Sprint 0)

Proyecto: **Restaurant Management System**
Duración: **Fin de semana (Sprint de arranque)**

Objetivo del sprint:

> Tener **la estructura base del proyecto**, backend (Spring Boot) y cliente (Swing), compilando correctamente y con responsabilidades claras por integrante.

---

##  Backend – Spring Boot

###  Configuración Base

* [ ] Crear proyecto Spring Boot (`restaurant-management`) con Maven
* [ ] Configurar `application.yml` (puertos, datasource en H2/MySQL)
* [ ] Verificar que la aplicación levante correctamente

---

###  Seguridad y Configuración Global

* [ ] Crear paquete `config`
* [ ] Implementar `SecurityConfig` (estructura básica, sin reglas complejas aún)
* [ ] Crear `JwtConfig` (claves, expiración, estructura)
* [ ] Agregar `CorsConfig`
* [ ] Agregar `SwaggerConfig`
* [ ] Configurar `ModelMapperConfig`

---

###  Capa Common

* [ ] Crear `ApiConstants`
* [ ] Implementar excepciones base:

    * `BusinessException`
    * `NotFoundException`
    * `UnauthorizedException`
* [ ] Crear `ApiResponse` y `ErrorResponse`

---

###  Dominio (CORE)

* [ ] Crear modelos de dominio:

    * `Usuario`
    * `Rol`
    * `Mesa`
    * `Producto`
    * `Pedido`
    * `PedidoDetalle`
    * `Venta`
    * `Inventario`
* [ ] Definir relaciones a nivel dominio (sin JPA todavía)
* [ ] Crear interfaces de repositorio:

    * `UsuarioRepository`
    * `PedidoRepository`
    * `ProductoRepository`
    * `MesaRepository`
* [ ] Crear servicios de dominio:

    * `PedidoDomainService`
    * `VentaDomainService`
    * `InventarioDomainService`

---

###  Application (Casos de Uso)

* [ ] Crear DTOs:

    * `PedidoRequestDTO`
    * `PedidoResponseDTO`
    * `LoginRequestDTO`
    * `LoginResponseDTO`
* [ ] Crear Mappers:

    * `PedidoMapper`
    * `UsuarioMapper`
* [ ] Implementar casos de uso:

    * `CrearPedidoUseCase`
    * `AgregarProductoUseCase`
    * `CerrarPedidoUseCase`
    * `CobrarPedidoUseCase`
    * `LoginUseCase`

---

###  Infrastructure

* [ ] Crear entidades JPA:

    * `PedidoEntity`
    * `ProductoEntity`
    * `UsuarioEntity`
* [ ] Implementar repositorios JPA:

    * `JpaPedidoRepository`
    * `JpaProductoRepository`
    * `JpaUsuarioRepository`
* [ ] Crear seguridad JWT:

    * `JwtProvider`
    * `JwtFilter`
* [ ] Crear cliente externo:

    * `PaymentServiceClient` (mock)

---

###  Presentation (API REST)

* [ ] Crear controladores:

    * `AuthController`
    * `PedidoController`
    * `VentaController`
* [ ] Implementar `GlobalExceptionHandler`

---

##  Cliente – Swing

###  Estructura Base

* [ ] Crear proyecto `restaurant-swing-client`
* [ ] Configurar `Main.java`
* [ ] Crear `ApiConfig`

---

###  Vistas

* [ ] `LoginFrame`
* [ ] `DashboardFrame`
* [ ] `PedidoPanel`
* [ ] `CocinaPanel`

---

###  Controladores y Servicios

* [ ] `LoginController`
* [ ] `PedidoController`
* [ ] `AuthService`
* [ ] `PedidoService`

---

###  Utilidades

* [ ] `HttpClientUtil`
* [ ] `SessionManager`

---

##  Entregable del fin de semana

* Proyecto compila sin errores
* Estructura completa creada
* README con instrucciones básicas
