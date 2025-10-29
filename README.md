# Interview Challenge: Address Book App

This is a [T3 Stack](https://create.t3.gg/) project built for an interview challenge, featuring an Address Book application that fetches and displays user data with interactive filtering, sorting, and search capabilities.

🚀 **Live Demo**: [https://interview-eight-rosy.vercel.app/](https://address-book-challenge-ten.vercel.app/)

## Challenge Overview

The goal is to create an Address Book app that:

- Fetches user data from [https://dummyjson.com/users](https://dummyjson.com/users)
- Displays users in a clean, structured layout
- Enables interactive filtering, sorting, and search functionality
- Emphasizes type safety, clean architecture, and maintainability

### Tech Stack Used

- **React** - UI framework
- **Next.js** - Full-stack React framework
- **TypeScript** - Type safety throughout
- **tRPC** - End-to-end typesafe APIs
- **Prisma** - Database ORM
- **SQLite** - Database
- **Tailwind CSS** - Styling
- **Zod** - Runtime type validation

## Features Implemented

- ✅ Fetches and validates user data from external API
- ✅ Clean, responsive card-based layout
- ✅ Search functionality (name and email)
- ✅ Filtering by gender and other user properties
- ✅ Sorting by name, age, and other fields
- ✅ Loading and error state handling
- ✅ Type-safe data validation with Zod
- ✅ Clean component architecture
- ✅ Responsive design

## Getting Started

1. Clone the repository:

```bash
git clone https://github.com/andrashejj/interview
cd interview
```

2. Install dependencies:

```bash
pnpm install
```

3. Set up the database:

```bash
pnpm db:push
```

4. Start the development server:

```bash
pnpm dev
```

Open [http://localhost:3000](http://localhost:3000) to view the application.

## Project Structure

```text
src/
├── app/
│   ├── _components/
│   │   ├── challenge.tsx      # Challenge description component
│   │   └── address-book/      # Address book components
│   └── page.tsx               # Main page
├── server/
│   └── api/                   # tRPC API routes
└── trpc/                      # tRPC configuration
```

## Learn More

To learn more about the [T3 Stack](https://create.t3.gg/), take a look at the following resources:

- [Documentation](https://create.t3.gg/)
- [Learn the T3 Stack](https://create.t3.gg/en/faq#what-learning-resources-are-currently-available) — Check out these awesome tutorials

You can check out the [create-t3-app GitHub repository](https://github.com/t3-oss/create-t3-app) — your feedback and contributions are welcome!

## Deployment

This application is deployed on [Vercel](https://vercel.com/). For more deployment options, see the [T3 deployment guides](https://create.t3.gg/en/deployment/vercel).
