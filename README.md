## Overview

This Invoice App is a modern web application built with React and Vite that allows users to create, read, update, and delete invoices. The application features a clean interface, dark/light theme support, and persistent data storage using localStorage.

## Features

- Create new invoices with detailed line items
- View all invoices in a filterable list
- Edit existing invoices
- Delete invoices with confirmation
- Mark invoices as paid
- Save invoices as drafts
- Support for multiple payment terms (1, 7, 14, 30 days)
- Form validation with error messages
- Responsive design for mobile and desktop
- Dark/Light theme toggle
- Local data persistence

## Tech Stack

- React 19.2.5
- Vite 8.0.9
- React Router DOM 7.14.1
- React Hook Form 7.73.1
- date-fns 4.1.0
- ESLint for code quality

## How to Run Locally

### Prerequisites

- Node.js (v16 or higher)
- npm (v8 or higher)

### Installation Steps

1. Clone the repository:
   ```bash
   git clone https://github.com/devv-leo/invoice-app.git
   cd invoice-app

### Install dependencies:

> npm install

Start the development server:
> npm run dev
> 
Open your browser and navigate to:
> http://localhost:5173

Available Scripts
npm run dev - Start the development server
npm run build - Build the application for production
npm run lint - Run ESLint to check code quality
npm run preview - Preview the production build locally


## Project Structure

```
src/
├── components/           # Reusable UI components
│   ├── DeleteModal.jsx
│   ├── EmptyState.jsx
│   ├── FilterDropdown.jsx
│   ├── InvoiceCard.jsx
│   ├── InvoiceForm.jsx
│   ├── Sidebar.jsx
│   └── StatusBadge.jsx
├── context/             # React Context for state management
│   ├── InvoiceContext.jsx
│   └── ThemeContext.jsx
├── pages/               # Page components
│   ├── InvoiceList.jsx
│   └── InvoiceDetail.jsx
├── styles/              # CSS files
├── utils/               # Utility functions
├── data/                # Mock data
├── App.jsx
└── main.jsx
```

## Decisions Made
### State Management with React Context
I chose React Context API over Redux to keep the application lightweight while managing invoice data and theme state. This provides a good balance between simplicity and functionality for the current scope.

### Local Storage for Persistence
Invoice data is persisted using browser localStorage, eliminating the need for a backend database during development. Data automatically syncs whenever invoices change.

### React Hook Form for Form Handling
React Hook Form was selected for efficient form state management with minimal re-renders. It provides built-in validation and error handling without heavy library dependencies.

### Client-Side Validation
Form validation occurs on the client side with clear, actionable error messages. Required fields include street address, city, postal code, country, client name, email, and at least one invoice item.

### Vite as Build Tool
Vite provides fast hot module replacement (HMR) during development and optimized production builds. It's significantly faster than Create React App for development workflows.

### Modular Component Architecture
Components are organized by responsibility (components, pages, context) to improve maintainability and make the codebase easier to scale.

### Trade-offs
Client-Side Data Storage vs. Backend Database
Trade-off: localStorage has a 5-10MB limit per domain and is not shared across devices. Benefit: No server setup required; faster initial development. Recommendation: For production use, implement a backend API and database.

### Context API vs. Redux
Trade-off: Context API requires prop drilling in deeply nested components; less sophisticated debugging tools. Benefit: Less boilerplate code; smaller bundle size. Impact: Works well for the current app scope but may need Redux for larger applications.

### Client-Side Only Validation vs. Server-Side Validation
Trade-off: Data can be manipulated in the browser; no audit trail. Benefit: Better user experience with immediate feedback; reduced server requests. Recommendation: Add server-side validation if implementing a backend.

### No Authentication/Authorization
Trade-off: All invoices are visible to anyone with access to the browser. Benefit: Simplified development; no user management complexity. Recommendation: Add authentication when deploying to production.

### Single-Page Application Architecture
Trade-off: Entire app loads upfront; can impact initial load time with more features. Benefit: Smooth navigation; no full page reloads; better user experience. Mitigation: Code splitting and lazy loading can be implemented for larger apps.
ailable under the MIT License.

Author
devv-leo

Contributing
Contributions are welcome. Please feel free to submit a Pull Request.
