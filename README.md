# final-bit-front
## 👨‍💻 Autor: 
Daniel Armando Ciendúa Ricaurte

# 🛒 Frontend - Sistema de Inventario (Supermercado)

## 📌 Descripción

Este proyecto corresponde al frontend de un sistema de gestión de inventario para supermercado, desarrollado con Angular bajo una arquitectura modular y basada en componentes.

Permite realizar operaciones CRUD sobre productos mediante una interfaz gráfica intuitiva, consumiendo una API REST desarrollada en Node.js y conectada a MongoDB.

---

## 🚀 Tecnologías utilizadas

* Angular
* TypeScript
* HTML5
* CSS3
* Bootstrap (opcional)
* RxJS
* API REST (Node.js + Express)
* MongoDB

---

## 🧠 Metodología de desarrollo en Angular

El proyecto sigue una **arquitectura basada en componentes y servicios**, aplicando buenas prácticas de Angular para mantener un código escalable y mantenible.

### 🔹 Principios aplicados

* 📦 Separación de responsabilidades
* 🔄 Reutilización de componentes
* 📡 Consumo de servicios desacoplados
* 🧩 Modularidad del proyecto
* 🔐 Tipado fuerte con TypeScript

---

## 📂 Estructura del proyecto

```id="9j7y2s"
src/
│
├── app/
│   ├── components/     # Componentes reutilizables
│   ├── pages/          # Vistas principales
│   ├── services/       # Comunicación con el backend
│   ├── models/         # Interfaces (TypeScript)
│   ├── shared/         # Componentes compartidos
│   │
│   ├── app-routing.module.ts
│   ├── app.module.ts
│   └── app.component.ts
│
└── assets/
```

---

## ⚙️ Instalación y ejecución

### 1. Clonar el repositorio

```bash id="cbh7p3"
git clone https://github.com/tu-usuario/tu-frontend.git
cd tu-frontend
```

### 2. Instalar dependencias

```bash id="px1c6v"
npm install
```

### 3. Ejecutar la aplicación

```bash id="0e8k6w"
ng serve
```

Aplicación disponible en:

```id="bzzx1m"
http://localhost:4200
```

---

## 🔌 Conexión con el Backend

El frontend consume una API REST mediante servicios en Angular.

### 📡 Ejemplo de servicio

```ts id="5j1b2n"
@Injectable({
  providedIn: 'root'
})
export class ProductService {

  private apiUrl = 'http://localhost:3000/products';

  constructor(private http: HttpClient) {}

  getProducts() {
    return this.http.get(this.apiUrl);
  }

  createProduct(product: Product) {
    return this.http.post(this.apiUrl, product);
  }

  updateProduct(id: string, product: Product) {
    return this.http.put(`${this.apiUrl}/${id}`, product);
  }

  deleteProduct(id: string) {
    return this.http.delete(`${this.apiUrl}/${id}`);
  }
}
```

---

## 🔄 Flujo de datos

El sistema sigue el siguiente flujo:

Componente → Servicio → API REST → MongoDB
MongoDB → API REST → Servicio → Componente

Esto permite mantener una arquitectura desacoplada y escalable.

---

## 🔐 Uso de TypeScript

Se implementa TypeScript para definir modelos y garantizar consistencia en los datos.

```ts id="q0w3r8"
export interface Product {
  _id?: string;
  name: string;
  price: number;
  stock: number;
  category: string;
}
```

---

## 🎨 Diseño Responsive

Se implementa diseño adaptable utilizando:

* Flexbox
* CSS Grid
* Media Queries
* Bootstrap (opcional)

Permitiendo compatibilidad con:

* 📱 Dispositivos móviles
* 💻 Tablets
* 🖥️ Escritorio

---

## 🧪 Pruebas

* Consumo de endpoints desde Angular
* Validación de datos en formularios
* Visualización de datos en tiempo real desde MongoDB

---

## ✨ Buenas prácticas implementadas

* Uso de servicios para lógica HTTP
* Separación entre componentes y lógica
* Tipado fuerte con TypeScript
* Organización modular del proyecto
* Código reutilizable

---

## 🔮 Mejoras futuras

* Autenticación (JWT)
* Manejo de estados (NgRx)
* Paginación y filtros
* Dashboard analítico
* Deploy en producción

---
