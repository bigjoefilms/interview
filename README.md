# Interview Challenge: Address Book App

A T3 Stack Address Book application with interactive filtering, sorting, and search capabilities.

🚀 **Live Demo**: <https://interview-eight-rosy.vercel.app/>

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

✅ Paginated users list with search & multi-filter support  
✅ Dynamic table columns based on active filters  
✅ User detail pages with comprehensive information  
✅ Todos drawer with full CRUD functionality  
✅ Loading, error, and empty states  
✅ Responsive design with smooth animations  

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

## Available Scripts

- `pnpm dev` - Start development server
- `pnpm build` - Build for production
- `pnpm db:seed` - Seed the database
- `pnpm db:studio` - Open Prisma Studio