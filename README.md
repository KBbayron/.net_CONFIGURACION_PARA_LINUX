<h1 align="center">CONFIGURACIÓN DE .NET CORE WEB API</h1>

Esta documentación cubre la configuración y uso de **.NET Core** y **.NET 8+** en sistemas **Debian**. Incluye comandos para instalación básico para la creación de proyectos y ejecución.

## 📚 Recursos Oficiales
- **[Documentación Microsoft Learn](https://learn.microsoft.com/es-es/aspnet/core/web-api/?view=aspnetcore-10.0)**

## 📧 Contacto
Si encuentras errores o necesitas ayuda, contáctame:

- [Correo](mailto:bayronlr@outlook.com)
- [LinkedIn](https://www.linkedin.com/in/bayronleiva-dev/)


# Linux

## Instalar dependencias necesarias en Linux
```bash
sudo apt install -y wget curl gnupg ca-certificates
```

## Agregar el repositorio de Microsoft
```bash
wget https://packages.microsoft.com/config/debian/[version]/packages-microsoft-prod.deb -O packages-microsoft-prod.deb

sudo dpkg -i packages-microsoft-prod.deb

rm packages-microsoft-prod.deb
```
## Instalar .NET SDK (incluye runtime y herramientas)
```bash
sudo apt update
sudo apt install -y dotnet-sdk
```
## Crear proyecto de consola
```bash
dotnet new console -n MiPrimerProyecto
```
## Verificar la instalación
```bash
dotnet --version
dotnet --info
```
## Crear proyecto API web (REST)
```bash
dotnet new webapi -n [nombre-del-poyecto]
```
Te creará un proyecto con el archivo 'Program.cs' con un código similar:
```csharp
var builder = WebApplication.CreateBuilder(args);

builder.Services.AddControllers();
builder.Services.AddEndpointsApiExplorer();
builder.Services.AddSwaggerGen();

var app = builder.Build();

if (app.Environment.IsDevelopment())
{
    app.UseSwagger();
    app.UseSwaggerUI();
}

app.UseHttpsRedirection();
app.UseAuthorization();
app.MapControllers();

app.Run();
```
# Algunos otros proyectos de .Net que no son web API

## Crear proyecto web MVC
```bash
dotnet new mvc -n [nombre-del-poyecto]
```
## Crear proyecto Blazor
```bash
dotnet new blazorserver -n [nombre-del-poyecto]
```
# Compilar
```bash
dotnet build
```
# Compilar y ejecutar
```bash
dotnet run
```

# Compilar test
```bash
dotnet test
```