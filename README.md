# Control de Ingreso y Gasto

Este es un sistema web para la gestión de ingresos y gastos, desarrollado con ASP.NET Core y Bootstrap.

## Características
- Gestión de categorías de ingresos y gastos.
- Registro y visualización de ingresos y gastos.
- Interfaz responsiva con Bootstrap.

## Tecnologías Utilizadas
- ASP.NET Core MVC
- Entity Framework Core
- Bootstrap 4
- SQL Server

## Configuración del Proyecto
1. Clona este repositorio:
   ```sh
[  git clone https://github.com/tuusuario/control-ingreso-gasto.git](https://github.com/NestorAndres1215/Control-de-Ingreso-y-Gasto.git](https://github.com/NestorAndres1215/Control-de-Ingreso-y-Gasto.git)
   ```
2. Abre el proyecto en Visual Studio 2019.
3. Configura la cadena de conexión en `appsettings.json`.
4. Aplica las migraciones de la base de datos:
   ```sh
   dotnet ef database update
   ```
5. Ejecuta la aplicación desde Visual Studio.

## Base de Datos
### Estructura SQL
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


