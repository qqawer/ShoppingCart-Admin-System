## 🚀 Project Title

**SP (Service/Product Management System)**

A modern React-based frontend application for managing products and users. This project serves as a client-side interface for an admin/back-office system, designed to interact with a Spring Boot backend.

-----

## ✨ Features

This application provides a user-friendly interface for managing core business entities.

### Admin/Back Office Experience

  * **Product Management**:
      * Browse a list of all products (`/products`).
      * Add new products to the catalogue (`/products/add`).
      * Edit existing product details (`/products/:id`).

### Shared APIs / Integrations

  * **Backend Integration**: Consumes a generic REST API for data persistence (Products and Users).
  * **Proxy Configuration**: configured in Vite to proxy requests to a local backend (default: `http://localhost:8080`).

-----

## 📐 Architecture and Technologies

The project is built as a Single Page Application (SPA) using the modern frontend ecosystem.

  * **Frontend Framework:** **React 19** with **TypeScript** for type-safe component development.
  * **Build Tooling:** **Vite 7** for fast development and building.
  * **Styling:** **Bootstrap 5** and **Sass** for responsive and consistent UI components.
  * **Routing:** **React Router DOM 7** using `HashRouter` navigation.
  * **HTTP Client:** **Axios** for API requests.
  * **Linting:** **ESLint 9** with typescript configurations.

-----

## 📁 Project Layout

Overview of the source structure:

```text
.
├── src
│   ├── assets/            (Static assets)
│   ├── types/             (TypeScript type definitions, e.g., User, Product)
│   ├── views/             (Page components/Screens)
│   │   ├── home/          (Layout components: Header, SideBar)
│   │   ├── products/      (Product-related views: List, Add, Edit)
│   │   └── users/         (User-related views: List)
│   ├── App.tsx            (Main layout container)
│   ├── main.tsx           (Entry point)
│   └── router.tsx         (Route definitions)
├── public/                (Public static files)
├── dist/                  (Production build output)
├── vite.config.ts         (Vite configuration)
└── package.json           (Dependencies and scripts)
```

-----

## 🔧 Prerequisites

Ensure you have the following installed before running the project:

  * **Node.js**: (v18+ recommended).
  * **npm** (comes with Node) or **yarn**.
  * **Backend Service**: A backend service running on `http://localhost:8080` (expected to provide `/users` and `/products` endpoints).

-----

## ⚙️ Configuration

Configuration is primarily handled via `vite.config.ts`.

### Proxy Configuration
The development server is configured to proxy requests to `http://localhost:8080`.

```typescript
// vite.config.ts
server: {
  proxy: {
    '/api': {
      target: 'http://localhost:8080/',
      changeOrigin: true,
    },
  },
}
```
-----

## 🛠️ Setup and Running

Follow these steps to get the frontend running locally.

### Installation

1.  **Clone the repository:**
    ```bash
    git clone <repository-url>
    cd <project-directory>
    ```
2.  **Install dependencies:**
    ```bash
    npm install
    ```

### Running the Application

1.  **Start the development server:**
    ```bash
    npm run dev
    ```
    The application will be accessible at: `http://localhost:5173` (or the port shown in your terminal).

2.  **Build for production:**
    ```bash
    npm run build
    ```

3.  **Preview production build:**
    ```bash
    npm run preview
    ```

-----

## 🧪 Testing

Currently, the project focuses on static analysis via linting.

To check for code quality issues:

```bash
npm run lint
```

-----

## 🔗 HTTP Entry Points / API Reference

The frontend expects the following API endpoints to be available on the backend:

| Entity | Method | Path | Purpose |
|--------|--------|------|---------|
| Products | GET, POST | `/api/products/lists` | Fetch list of products. |
| Products | POST | `/api/addProduct` | Add a new product. |
| Products | POST | `/api/deleteProduct/:id` | Delete a product. |
| Products | POST | `/api/updateProduct` | Update a product. |
| Products | GET | `/api/products/:id` | Get a product. |

