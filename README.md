# Address Book App - Interview Challenge

A full-stack address book application built with Next.js, tRPC, Prisma, React Query, and Tailwind CSS. Features comprehensive user search, filtering, pagination, and a todos management system.

## 📋 Table of Contents

- [Overview](#overview)
- [What Was Completed](#what-was-completed)
- [What's Missing or Could Be Improved](#whats-missing-or-could-be-improved)
- [What Was Easy or Difficult and Why](#what-was-easy-or-difficult-and-why)
- [Next Steps](#next-steps)
- [What I'd Do Differently with More Time](#what-id-do-differently-with-more-time)

---

## 🎯 Overview

This project implements an address book application with the following key features:

- **User Directory**: Browse and search through a database of users
- **Advanced Filtering**: Filter by gender, hair color, eye color, and blood group
- **Real-time Search**: Debounced search across name, email, phone, and company fields
- **Responsive Pagination**: Efficient data loading with customizable page sizes
- **User Detail Pages**: Comprehensive user profiles with personal information, addresses, and company details
- **Todos Management**: Full CRUD operations for user-specific todo items in a slide-out drawer
- **Beautiful UI**: Modern design with smooth animations, hover effects, and responsive layouts

---

## ✅ What Was Completed

### Backend Implementation

#### Database Setup & Optimization
- ✅ Configured Prisma with SQLite database
- ✅ Created comprehensive User and Todo models with proper relations
- ✅ Added database indices for performance optimization:
  - Filterable fields: `gender`, `hairColor`, `eyeColor`, `bloodGroup`
  - Searchable fields: `firstName`, `lastName`, `email`, `phone`, `companyName`
- ✅ Implemented database seeding with realistic data from DummyJSON API

#### tRPC Router Implementation
- ✅ **User Router** (`src/server/api/routers/user.ts`):
  - `getUsers`: Paginated user list with search and filtering
  - `getUserById`: Individual user details with todo count
  - Proper input validation using Zod schemas
  - Efficient query building with Prisma ORM
  - Returns active filter metadata for UI display

- ✅ **Todo Router** (`src/server/api/routers/todo.ts`):
  - `getByUserId`: Fetch all todos for a specific user
  - `create`: Add new todo items
  - `update`: Update todo text and completion status
  - `delete`: Remove todo items
  - Full input validation and error handling

#### API Configuration
- ✅ tRPC setup with proper typing and error handling
- ✅ React Query integration for efficient data fetching
- ✅ Optimized caching strategies with stale time configuration

### Frontend Implementation

#### Core Components

**UI Components** (`src/components/ui/`):
- ✅ `Button.tsx` - Reusable button with variants (primary, secondary, danger, ghost)
- ✅ `Input.tsx` - Styled input with icon support
- ✅ `Select.tsx` - Dropdown component for filters
- ✅ `Badge.tsx` - Display components for active filters
- ✅ `Spinner.tsx` - Loading indicators
- ✅ `Drawer.tsx` - Slide-out drawer component for todos

**Feature Components**:
- ✅ `SearchBar.tsx` - Debounced search with 300ms delay
- ✅ `FilterPanel.tsx` - Multi-filter dropdown with active filter badges
- ✅ `UserTable.tsx` - Responsive table with dynamic columns, hover effects, and row spacing
- ✅ `Pagination.tsx` - Full pagination controls with page size selector
- ✅ `TodosDrawer.tsx` - Complete CRUD interface for todos with optimistic updates
- ✅ `LoadingState.tsx`, `ErrorState.tsx`, `EmptyState.tsx` - State handling components

#### Custom Hooks
- ✅ `useUsers.ts` - Paginated user list with filters and search
- ✅ `useUser.ts` - Single user details hook
- ✅ `useTodos.ts` - Todo management with optimistic updates and cache invalidation

#### Pages
- ✅ **Home Page** (`src/pages/index.tsx`):
  - Integrated search, filters, table, and pagination
  - URL state management with query parameters
  - Smooth scrolling to top on page changes
  - Complete loading and error handling

- ✅ **User Detail Page** (`src/pages/users/[id].tsx`):
  - Comprehensive user information display
  - Personal details, contact info, physical attributes
  - Address and company information sections
  - Bank and crypto details (parsed from JSON)
  - Todos management integration
  - Beautiful card-based layout with animations

### Design & UX

- ✅ **Modern UI Design**:
  - Clean, professional color scheme
  - Dark gray (#222) primary buttons with white text
  - Consistent spacing and typography
  - Professional card-based layouts

- ✅ **Animations & Interactions**:
  - Smooth hover effects on table rows with scale transformation
  - Shadow elevation on hover
  - Drawer slide-in animations
  - Filter panel dropdown animations
  - Loading spinners with pulse effects
  - Row spacing with border-separate layout

- ✅ **Responsive Design**:
  - Mobile-friendly layouts
  - Adaptive table columns
  - Touch-friendly interactive elements

### Engineering Excellence

- ✅ **Type Safety**: Full TypeScript coverage with Prisma-generated types
- ✅ **Performance Optimization**:
  - React Query caching with 5-minute stale time
  - Debounced search queries
  - Efficient database queries with proper indexing
  - Optimistic updates for instant UI feedback
- ✅ **Error Handling**: Comprehensive error states and user feedback
- ✅ **Code Organization**: Clean separation of concerns, reusable components

---

## ⚠️ What's Missing or Could Be Improved

### Testing
- ❌ **No Unit Tests**: Missing unit tests for components, hooks, and utilities
- ❌ **No Integration Tests**: No testing for API endpoints and data flow
- ❌ **No E2E Tests**: Missing end-to-end testing for critical user flows
- ⚠️ **Recommendation**: Add testing with Jest, React Testing Library, and Playwright

### Performance Enhancements
- ⚠️ **Virtual Scrolling**: Large lists could benefit from virtual scrolling
- ⚠️ **Image Optimization**: User avatars could use Next.js Image component for optimization
- ⚠️ **Bundle Size**: Could analyze and optimize bundle size further
- ⚠️ **Database Query Optimization**: Could add more efficient query patterns for complex filters

### Features
- ❌ **User Editing**: No ability to edit user information
- ❌ **Bulk Operations**: No bulk todo operations (bulk delete, bulk complete)
- ❌ **Export Functionality**: No CSV/JSON export of user data
- ❌ **Advanced Search**: No regex or wildcard search options
- ❌ **Saved Filters**: No ability to save favorite filter combinations
- ❌ **Keyboard Shortcuts**: No keyboard navigation for power users

### Accessibility
- ⚠️ **ARIA Labels**: Some interactive elements could use better ARIA labels
- ⚠️ **Keyboard Navigation**: Could improve keyboard navigation throughout
- ⚠️ **Focus Indicators**: Some focus states could be more visible
- ⚠️ **Screen Reader Support**: Could enhance screen reader announcements

### UI/UX Improvements
- ⚠️ **Mobile Optimization**: Table could be better optimized for mobile (card view alternative)
- ⚠️ **Loading Skeletons**: Could add skeleton loaders for better perceived performance
- ⚠️ **Toast Notifications**: Could add toast notifications for actions
- ⚠️ **Undo Functionality**: Could add undo for delete operations
- ⚠️ **Bulk Actions**: Could add row selection for bulk operations

### Documentation
- ⚠️ **API Documentation**: Could add OpenAPI/Swagger documentation
- ⚠️ **Component Documentation**: Could add Storybook for component showcase
- ⚠️ **Deployment Guide**: Could add detailed deployment instructions
- ⚠️ **Architecture Documentation**: Could document design decisions

### Security & Best Practices
- ⚠️ **Input Sanitization**: Could add more robust input validation
- ⚠️ **Rate Limiting**: Could add API rate limiting
- ⚠️ **CORS Configuration**: Could add proper CORS configuration for production
- ⚠️ **Environment Variables**: Could add more comprehensive environment configuration

---

## 🎯 What Was Easy or Difficult and Why

### Easy

#### 1. **Component Structure and Organization**
- **Why Easy**: The modular component structure with clear separation of UI components and feature components made the codebase easy to navigate and extend.

#### 2. **Type Safety with tRPC and Prisma**
- **Why Easy**: The combination of Prisma's type generation and tRPC's type inference created excellent end-to-end type safety with minimal boilerplate.

#### 3. **React Query Integration**
- **Why Easy**: React Query's caching and invalidation strategies worked seamlessly with tRPC, making data fetching straightforward and efficient.

#### 4. **Tailwind CSS Styling**
- **Why Easy**: Tailwind's utility-first approach made implementing designs fast and consistent without writing custom CSS.

#### 5. **Filter and Search Logic**
- **Why Easy**: The Prisma ORM made building complex filter and search queries straightforward with its query builder API.

### Difficult

#### 1. **Prisma Client Generation Issues**
- **Why Difficult**: Encountered permission errors with Prisma's engine cache directory on macOS, requiring workarounds with environment variables.
- **Solution**: Used `SKIP_POSTINSTALL_GENERATE` and `SKIP_ENV_VALIDATION` flags to bypass cache issues.

#### 2. **Dynamic Table Columns**
- **Why Difficult**: Implementing dynamic columns based on active filters required careful state management and conditional rendering logic.
- **Challenge**: Maintaining proper column alignment and styling when columns appear/disappear.

#### 3. **URL State Management**
- **Why Difficult**: Syncing URL query parameters with component state while maintaining backward compatibility required careful orchestration.
- **Challenge**: Ensuring URL updates don't cause unnecessary re-renders while keeping state in sync.

#### 4. **Optimistic Updates**
- **Why Difficult**: Implementing optimistic updates for todos while ensuring cache consistency and handling rollbacks on errors.
- **Solution**: Used React Query's `useMutation` with `onMutate`, `onError`, and `onSettled` callbacks.

#### 5. **Table Row Spacing and Styling**
- **Why Difficult**: Achieving proper spacing between table rows with shadows required using `border-separate` layout, which introduced complexity with border styling.
- **Challenge**: Balancing visual design with table semantic structure.

#### 6. **Data Seeding with External API**
- **Why Difficult**: Fetching data from DummyJSON API and parsing complex nested JSON structures (bank, crypto) into SQLite.
- **Challenge**: Handling API rate limits and managing large datasets efficiently.

---

## 🚀 Next Steps (with Rough Time Estimates)

### Immediate Priority (1-2 weeks)

1. **Fix Critical Issues** (4-6 hours)
   - Resolve Prisma cache permission issues permanently
   - Fix any remaining type errors
   - Optimize database queries

2. **Add Unit Tests** (8-12 hours)
   - Test hooks (useUsers, useUser, useTodos)
   - Test tRPC routers
   - Test utility functions
   - Setup Jest and React Testing Library

3. **Improve Mobile Experience** (4-6 hours)
   - Create card-based mobile view for user table
   - Optimize drawer for small screens
   - Improve touch targets

### Short-term (2-4 weeks)

4. **Add Component Tests** (6-8 hours)
   - Test all UI components
   - Test user interactions
   - Test edge cases and error states

5. **Performance Optimization** (4-6 hours)
   - Implement virtual scrolling for large lists
   - Add Next.js Image optimization
   - Bundle size analysis and optimization
   - Implement React.memo for expensive components

6. **Enhance Todo Features** (3-4 hours)
   - Add bulk operations (select all, delete multiple)
   - Add todo categories/tags
   - Add due dates and priorities

### Medium-term (1-2 months)

7. **Add E2E Testing** (8-12 hours)
   - Setup Playwright or Cypress
   - Test critical user flows
   - Add CI/CD integration

8. **User Editing Features** (6-8 hours)
   - Allow editing user information
   - Add form validation
   - Implement proper permissions

9. **Export Functionality** (3-4 hours)
   - CSV export
   - JSON export
   - PDF generation

10. **Deploy to Production** (4-6 hours)
    - Setup Vercel deployment
    - Configure environment variables
    - Add monitoring and analytics
    - Implement proper error tracking

### Long-term (2-3 months)

11. **Advanced Features** (12-16 hours)
    - User authentication
    - Saved filters and preferences
    - Advanced search with regex
    - Import functionality

12. **Complete Documentation** (8-10 hours)
    - API documentation with OpenAPI
    - Component library with Storybook
    - Architecture documentation
    - Deployment guides

13. **Security Enhancements** (6-8 hours)
    - Add rate limiting
    - Implement CSRF protection
    - Add input sanitization
    - Security audit

---

## 💡 What I'd Do Differently with More Time

### Architecture Decisions

1. **Testing First Approach**
   - Would implement TDD (Test-Driven Development)
   - Write tests alongside features from the beginning
   - This would save debugging time and improve code quality

2. **Component Library**
   - Would create a proper component library with Storybook
   - Document component APIs and usage
   - This would improve reusability and consistency

3. **State Management**
   - For larger state management needs, might introduce Zustand or Jotai
   - Current approach is sufficient but could scale better

4. **Database Choice**
   - Would consider PostgreSQL for production instead of SQLite
   - Better for concurrent access and advanced query features
   - SQLite chosen for simplicity and portability

### Development Process

5. **Git Workflow**
   - Would use more granular feature branches
   - Implement proper PR review process
   - Add conventional commit messages

6. **Documentation**
   - Would document design decisions (ADR - Architecture Decision Records)
   - Add inline code documentation
   - Create developer onboarding guide

7. **CI/CD Pipeline**
   - Would implement early in the project
   - Automated testing, linting, and building
   - Deployment automation

### Technical Choices

8. **Accessibility**
   - Would implement accessibility from the start
   - Use ARIA patterns consistently
   - Keyboard navigation throughout
   - Screen reader testing

9. **Performance Monitoring**
   - Would add performance monitoring early
   - Track Core Web Vitals
   - Monitor API response times
   - Real user monitoring

10. **Error Handling**
    - Would implement comprehensive error tracking
    - Use Sentry or similar for error monitoring
    - Better error boundary implementation
    - User-friendly error messages

### Design & UX

11. **Design System**
    - Would create a comprehensive design system
    - Define all design tokens (colors, spacing, typography)
    - Design component variants systematically
    - Maintain design consistency documentation

12. **Mobile-First Approach**
    - Would design mobile experience first
    - Progressive enhancement for desktop
    - Better mobile navigation patterns

13. **User Testing**
    - Would conduct user testing sessions
    - Gather feedback early and iterate
    - A/B testing for critical features

### Code Quality

14. **Code Review Process**
    - Would implement mandatory code reviews
    - Use linting rules more strictly
    - Add pre-commit hooks with Husky
    - Use ESLint and Prettier consistently

15. **Type Safety**
    - Would use stricter TypeScript configuration
    - Add runtime validation with Zod
    - Use branded types for IDs and sensitive data

16. **Code Splitting**
    - Would implement route-based code splitting
    - Lazy load heavy components
    - Reduce initial bundle size

---

## 🛠️ Tech Stack

- **Frontend**: Next.js 15, React 19, TypeScript
- **Backend**: tRPC, Prisma ORM
- **Database**: SQLite
- **Styling**: Tailwind CSS 4
- **Data Fetching**: React Query (TanStack Query)
- **Validation**: Zod
- **Icons**: SVG (built-in)

---

## 🚀 Getting Started

### Prerequisites

- Node.js 18+ and pnpm

### Installation

```bash
# Install dependencies
pnpm install

# Generate Prisma client
pnpm prisma generate

# Seed the database
pnpm db:seed

# Run development server
pnpm dev
```

Visit `http://localhost:3000` to see the application.

### Available Scripts

- `pnpm dev` - Start development server
- `pnpm build` - Build for production
- `pnpm start` - Start production server
- `pnpm lint` - Run ESLint
- `pnpm typecheck` - Run TypeScript compiler
- `pnpm db:studio` - Open Prisma Studio
- `pnpm db:seed` - Seed the database

---

## 📝 License

This project was created as part of a technical interview challenge.

---

## 📧 Contact

For questions about this implementation, please open an issue on GitHub.
