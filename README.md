# 🎵 Prueba Técnica: FullStack Playlist Manager

Este repositorio es el **punto central** de la solución integral para la gestión de listas de reproducción musicales. Aquí se encuentra la documentación maestra y el acceso a los diferentes módulos del sistema.

---

## 🔗 Enlaces a los Repositorios
* **Frontend (Angular 19):** [https://github.com/CarlosEstrad/music-playlist-app.git](https://github.com/CarlosEstrad/music-playlist-app.git)
* **Backend (.NET 8):** [https://github.com/CarlosEstrad/API-IUDAntioquia.git](https://github.com/CarlosEstrad/API-IUDAntioquia.git)

---

## 🛠️ Tecnologías Utilizadas
* **Frontend:** Angular 19, Tailwind CSS (Diseño responsive), Jasmine/Karma (Testing).
* **Backend:** .NET 8 (C#), Entity Framework Core.
* **Base de Datos:** SQL Server (Relacional).
* **Autenticación:** JWT (JSON Web Tokens).

---

## 🏗️ Arquitectura y Decisiones Técnicas
* **Separación de Concernimientos:** Arquitectura desacoplada. El Frontend consume una API RESTful, permitiendo escalabilidad independiente.
* **Seguridad:** Implementación de un `AuthInterceptor` en Angular para inyección automática de JWT y middleware de autorización en .NET.
* **Base de Datos:** Motor relacional (SQL Server) para garantizar integridad referencial (Usuarios -> Playlists -> Canciones).

---

## 📊 Modelo de Base de Datos y Análisis
> **Nota:** El script de creación se encuentra en la carpeta `/database` de este repositorio (o en el repositorio Backend).

### Índices Justificados:
1.  **`IX_Users_Email`**: Optimización de velocidad en el inicio de sesión.
2.  **`IX_Playlists_UserId`**: Agilidad en la carga de listas por usuario específico.

### Estructuras de Análisis (Vistas/Consultas):
* **TotalUsuarios:** Conteo total de registros.
* **TopPlaylists:** Playlists con mayor número de canciones.
* **PromedioCanciones:** Media de temas por lista de reproducción.

---

## 🧪 Pruebas Unitarias
Se implementaron pruebas robustas en el Frontend utilizando Jasmine y Karma.

* **Componente Home:** Pruebas de inicialización de formularios, apertura de modales y cierre de sesión.
* **AuthInterceptor:** Validación de inyección de tokens de seguridad.
* **Cobertura:** **91.35%** (Enfocada en el Core de la aplicación).

**Para ejecutar las pruebas:**
```bash
ng test --code-coverage --no-watch