# 📊 Control de Ingreso y Gasto

Este es un sistema web para la gestión de ingresos y gastos, desarrollado con ASP.NET Core y Bootstrap.

## ✨ Características
- 📂 Gestión de categorías de ingresos y gastos.
- 💰 Registro y visualización de ingresos y gastos.
- 📱 Interfaz responsiva con Bootstrap y animaciones en CSS.

## 🛠️ Tecnologías Utilizadas

| Tecnología                | Descripción |
|--------------------------|-------------|
| ![ASP.NET Core](https://upload.wikimedia.org/wikipedia/commons/e/ee/.NET_Core_Logo.svg) | **ASP.NET Core MVC** - Framework para aplicaciones web. |
| ![Entity Framework](https://upload.wikimedia.org/wikipedia/commons/thumb/6/6f/Entity_Framework_Logo.png/220px-Entity_Framework_Logo.png) | **Entity Framework Core** - ORM para el acceso a datos. |
| ![Bootstrap](https://upload.wikimedia.org/wikipedia/commons/b/b2/Bootstrap_logo.svg) | **Bootstrap 4** - Framework de diseño responsivo. |
| ![SQL Server](https://upload.wikimedia.org/wikipedia/en/8/8c/Microsoft_SQL_Server_Logo.svg) | **SQL Server** - Sistema de gestión de bases de datos. |
| 🎨 **CSS Animado** | Estilos personalizados y animaciones CSS |

## 🚀 Configuración del Proyecto

1. Clona este repositorio:
   ```sh
   git clone https://github.com/NestorAndres1215/Control-de-Ingreso-y-Gasto.git
   ```
2. Abre el proyecto en **Visual Studio 2019 o superior**.
3. Configura la cadena de conexión en `appsettings.json`.
4. Aplica las migraciones de la base de datos:
   ```sh
   dotnet ef database update
   ```
5. Ejecuta la aplicación desde Visual Studio.

## 🗄️ Base de Datos

### 📌 Estructura SQL
```sql
CREATE TABLE Categorias (
    Id INT IDENTITY(1,1) PRIMARY KEY,
    NombreCategoria NVARCHAR(255) NOT NULL,
    Tipo NVARCHAR(50) NOT NULL,
    Estado BIT NOT NULL
);

CREATE TABLE IngresoGasto (
    Id INT IDENTITY(1,1) PRIMARY KEY,
    CategoriaId INT NOT NULL,
    Fecha DATETIME NOT NULL,
    Valor FLOAT NOT NULL CHECK (Valor >= 1 AND Valor <= 100000),
    CONSTRAINT FK_IngresoGasto_Categoria FOREIGN KEY (CategoriaId) REFERENCES Categorias(Id) ON DELETE CASCADE
);
```

