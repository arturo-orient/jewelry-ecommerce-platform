# 💍 Nora Joyeros | Full-Stack E-commerce Platform

> **Nota:** Este repositorio funciona como un escaparate técnico (Showcase). El código fuente completo se mantiene en un repositorio privado por acuerdos de confidencialidad y propiedad del cliente.

## 📖 Descripción del Proyecto
Plataforma de comercio electrónico integral diseñada para una joyería de lujo, centrada en la automatización de procesos administrativos y una experiencia de usuario de alto nivel. El proyecto aborda desafíos complejos de ingeniería, como la sincronización masiva de inventarios y la optimización de métricas de rendimiento web.

---

## 🛠️ Stack Tecnológico

| Capa | Tecnologías |
| :--- | :--- |
| **Frontend** | Next.js 14 (App Router), TypeScript, Tailwind CSS, Framer Motion |
| **State Management** | Zustand (con persistencia en LocalStorage) |
| **Backend** | Node.js, Express, TypeScript |
| **Base de Datos** | PostgreSQL, Prisma ORM |
| **Seguridad** | JWT, RBAC (Role-Based Access Control), Bcryptjs |
| **Herramientas** | Sharp (Procesamiento de imágenes), ExcelJS, Stripe API, Recharts |

---

## 🚀 Características Principales

* **Gestión Automatizada:** Motor de ingesta de datos para carga masiva de productos mediante archivos Excel/TSV.
* **Optimización WPO:** Pipeline de procesamiento de imágenes con **Sharp** que convierte automáticamente a formato **WebP**.
* **Dashboard de Analíticas:** Panel administrativo con visualizaciones dinámicas (Recharts) para seguimiento de ventas en tiempo real.
* **Seguridad Avanzada:** Flujo de autenticación con JWT y control de acceso basado en roles (RBAC).
* **Pasarela de Pagos:** Integración de Stripe para procesos de checkout seguros.

---

## 🛠️ Technical Deep Dive: Ingeniería e Infraestructura

Esta sección detalla las decisiones arquitectónicas que garantizan la robustez y escalabilidad de la plataforma.

<details>
<summary><b>1. Arquitectura de Datos y Modelado con Prisma</b></summary>

* **Strong Typing:** Uso de PostgreSQL y Prisma para garantizar un tipado fuerte en toda la aplicación.
* **Modelado Relacional:** Relación de muchos-a-muchos (m:n) entre productos y categorías para una navegación dinámica.
* **Atomicidad:** Operaciones `upsert` basadas en SKU para garantizar que el motor de ingesta sea idempotente.
* **Rendimiento:** Implementación de ejecución paralela con `Promise.all` para reducir la latencia de respuesta en un 40%.
</details>

<details>
<summary><b>2. Motor de Ingesta Masiva (ExcelJS/TSV Processing)</b></summary>

* **Buffer Processing:** Ingesta mediante buffers en memoria para evitar escrituras en disco innecesarias.
* **Normalización:** Limpieza de caracteres especiales y estandarización de formatos SQL de forma automatizada.
* **Auto-Categorización:** Algoritmo de detección basado en keywords para organizar el catálogo sin intervención manual.
</details>

<details>
<summary><b>3. Pipeline de Imágenes y Optimización (Sharp)</b></summary>

* **Core Web Vitals:** Reducción del peso de imágenes entre un 50% y 80% mediante conversión dinámica a WebP.
* **LCP Optimization:** Redimensión automática a un máximo de 1200px para garantizar tiempos de carga óptimos.
* **Vínculo Lógico:** Asignación automática de medios a productos mediante el SKU extraído del nombre del archivo.
</details>

<details>
<summary><b>4. Gestión de Estado Global (Zustand)</b></summary>

* **Arquitectura:** Selección de Zustand para una gestión de estado sin boilerplate y con alto rendimiento.
* **Selective Rendering:** Uso de selectores para evitar re-renders innecesarios en el árbol de componentes.
* **Persistencia:** Sincronización automática del carrito con `localStorage` mediante middleware nativo.
</details>

<details>
<summary><b>5. Seguridad: JWT y Control de Acceso (RBAC)</b></summary>

* **Middleware:** Validación de firma y expiración de tokens en rutas críticas de la API.
* **RBAC:** Jerarquía de roles (`restrictToAdmin`) para proteger la integridad del inventario y datos de ventas.
* **Hashing:** Uso de `bcryptjs` con factor de coste adaptado para resistir ataques de fuerza bruta.
</details>

---

## 📸 Sneak Peek (Interfaz)

> *Las capturas de pantalla se actualizarán tras el lanzamiento oficial de la plataforma.*

* **Storefront:** (assets/Home.png)
* **Admin Panel:** (assets/Admin.png)
* ** Motor de Ingesta (Excel/TSV) ** (assets/Nora Joyeros _ Alta Joyería - Screencastify - April 21, 2026 1_27 PM.gif)
---

## 👨‍💻 Sobre el Autor

* [cite_start]**Nombre:** Arturo Orient Romero [cite: 2]
* [cite_start]**Rol:** Junior Web Developer & Cybersecurity [cite: 3]
* [cite_start]**Localización:** Valencia, España [cite: 4]
* [cite_start]**Formación Destacada:** * Especialización en Ciberseguridad (CISCO & Palo Alto) - 2026[cite: 15].
    * [cite_start]FP Superior en Desarrollo de Aplicaciones Web - 2025[cite: 38].

---
*Para más detalles sobre mi perfil técnico, visita mi [LinkedIn](https://www.linkedin.com/in/arturo-orient-romero/) o mi perfil principal de [GitHub](https://github.com/Matalentajas).*
