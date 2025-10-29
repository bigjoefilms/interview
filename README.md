# Interview Challenge: Address Book App

A T3 Stack Address Book application with interactive filtering, sorting, and search capabilities.

 **Live Demo**: <https://interview-eight-rosy.vercel.app/>

## Overview

Create an Address Book app that fetches user data from [dummyjson.com/users](https://dummyjson.com/users) with:
- Clean, structured layout
- Interactive filtering, sorting, and search
- Type safety and clean architecture

## Tech Stack

- **React** + **Next.js** + **TypeScript**
- **tRPC** + **Prisma** + **SQLite**
- **Tailwind CSS** + **Zod**

## Features

Paginated users list with search & multi-filter support  
Dynamic table columns based on active filters  
User detail pages with comprehensive information  
Todos drawer with full CRUD functionality  
Loading, error, and empty states  
Responsive design with smooth animations  

## Quick Start

```bash
git clone https://github.com/bigjoefilms/interview
cd interview
pnpm install
pnpm db:push
pnpm dev
```

Open <http://localhost:3000>

## Project Structure

```
src/
├── pages/           # Pages Router
├── _components/    # UI components
├── hooks/          # React Query hooks
├── server/api/     # tRPC routers
└── utils/          # Utilities
```

##  What Was Completed

### Backend
-  Prisma schema with User/Todo models and database indices
-  tRPC routers for users and todos with full CRUD operations
-  Database seeding with DummyJSON API data
-  Type-safe API with Zod validation

### Frontend
-  Paginated users list with search & multi-filter support
-  Dynamic table columns based on active filters
-  User detail pages with comprehensive information display
-  Todos drawer with CRUD functionality and optimistic updates
-  Reusable UI components (Button, Input, Select, Badge, Drawer)
-  Loading, error, and empty states
-  Responsive design with smooth animations

##  What's Missing or Could Be Improved

-  **Testing**: No unit, integration, or E2E tests
-  **User Editing**: No ability to edit user information
-  **Bulk Operations**: No bulk todo operations
-  **Export Functionality**: No CSV/JSON export
-  **Mobile Optimization**: Table could be better for mobile
-  **Accessibility**: Could improve ARIA labels and keyboard navigation

## 🎯 What Was Easy or Difficult

### Easy
- **Component Structure**: Modular design made navigation easy
- **Type Safety**: tRPC + Prisma provided excellent type inference
- **React Query**: Seamless caching and invalidation
- **Tailwind CSS**: Fast styling with utility classes

### Difficult
- **Prisma Cache Issues**: Permission errors on macOS requiring workarounds
- **Dynamic Table Columns**: Complex state management for conditional rendering
- **URL State Management**: Syncing query params without unnecessary re-renders
- **Optimistic Updates**: Ensuring cache consistency with rollbacks

## 🚀 Next Steps

### Immediate (1-2 weeks)
1. **Add Unit Tests** (8-12 hours) - Jest + React Testing Library
2. **Fix Mobile Experience** (4-6 hours) - Card-based mobile view
3. **Performance Optimization** (4-6 hours) - Virtual scrolling, bundle analysis

### Short-term (2-4 weeks)
4. **E2E Testing** (8-12 hours) - Playwright/Cypress setup
5. **User Editing Features** (6-8 hours) - Form validation, permissions
6. **Export Functionality** (3-4 hours) - CSV/JSON export

### Long-term (2-3 months)
7. **Advanced Features** (12-16 hours) - Auth, saved filters, regex search
8. **Complete Documentation** (8-10 hours) - API docs, Storybook
9. **Security Enhancements** (6-8 hours) - Rate limiting, CSRF protection

## 💡 What I'd Do Differently with More Time

1. **Testing First**: Implement TDD from the beginning
2. **Component Library**: Create Storybook documentation
3. **Accessibility**: Implement ARIA patterns and keyboard navigation
4. **Mobile-First**: Design mobile experience first, then enhance for desktop
5. **CI/CD Pipeline**: Set up automated testing and deployment early
6. **Error Tracking**: Add comprehensive error monitoring with Sentry

## Available Scripts

- `pnpm dev` - Start development server
- `pnpm build` - Build for production
- `pnpm test` - Run tests with Jest
- `pnpm test:watch` - Run tests in watch mode
- `pnpm test:coverage` - Run tests with coverage report
- `pnpm db:seed` - Seed the database
- `pnpm db:studio` - Open Prisma Studio
