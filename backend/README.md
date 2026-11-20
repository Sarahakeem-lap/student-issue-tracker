# Student Issue Tracker: Backend Setup Guide

This document describes how to set up and run the backend (NestJS, Prisma, PostgreSQL) on a local machine. Please follow the steps in order.

## 1. Prerequisites

Install the following before you begin:

- **Node.js v24** (all team members should use the same major version)
- **Git**
- **PostgreSQL** (a recent stable version) and **pgAdmin**

## 2. Clone the Repository

```bash
git clone https://github.com/Sarahakeem-lap/student-issue-tracker.git
cd student-issue-tracker/backend
```

All commands in this guide must be run from the `backend` directory, which contains the NestJS `package.json`. Run `pwd` to confirm your location before executing any `npm` or `npx` command.

## 3. Install Dependencies

```bash
npm install
```

> **Important:** Do not install Prisma manually and do not run `npx prisma@latest`. The project pins Prisma to version `6.19.3` in `package.json`. Newer major versions use a different configuration format and are not compatible with this project.

## 4. Create the Database

Create an empty PostgreSQL database named `student_affairs`.

**Using pgAdmin:** right-click **Databases**, select **Create**, then **Database...**, enter `student_affairs`, and click **Save**.

**Using the terminal:**

```bash
psql -U postgres -c "CREATE DATABASE student_affairs;"
```

## 5. Configure Environment Variables

Copy the example file:

```bash
cp .env.example .env
```

Open `.env` and set your local PostgreSQL password:

```
DATABASE_URL="postgresql://postgres:YOUR_PASSWORD@localhost:5432/student_affairs"
JWT_SECRET="any_long_random_string"
```

Notes:

- Use a password containing only letters and digits. Special characters (such as `@`, `#`, `/`, `:`) must be URL-encoded and commonly cause connection errors.
- If your PostgreSQL server uses a port other than `5432`, update the URL accordingly.
- The `.env` file contains credentials and **must never be committed** to the repository.

## 6. Set Up the Database Schema

```bash
npx prisma generate
npx prisma migrate dev
```

- `prisma generate` creates the Prisma Client. It must be run explicitly in this project because `npm` does not execute dependency install scripts automatically.
- `prisma migrate dev` applies the existing migrations in `prisma/migrations` and creates all tables in your local database. If prompted for a migration name, press Enter.

Verify in pgAdmin (right-click the database, then **Refresh**, then **Schemas > public > Tables**) that the tables were created.

## 7. Run the Application

```bash
npm run start:dev
```

The server should start without errors at `http://localhost:3000`.

## 8. Daily Workflow

After every `git pull`, run:

```bash
npm install
npx prisma generate
npx prisma migrate dev
```

This installs any newly added packages and applies any new database migrations.

## 9. Team Conventions

### Database schema changes

1. Edit `prisma/schema.prisma`.
2. Generate a migration:
   ```bash
   npx prisma migrate dev --name <short_description_of_change>
   ```
3. Commit the updated schema **together with** the new folder in `prisma/migrations`.
4. Notify the team before pushing.

Never edit or delete an existing migration. To change something, create a new migration.

### Dependencies

- When adding a package, commit both `package.json` and `package-lock.json`.
- Do not run `npm audit fix --force`, as it may upgrade packages to incompatible major versions.

### Resetting a local database

If your local database is in an inconsistent state, you may reset it. **This deletes all local data.**

```bash
npx prisma migrate reset
```

Use this in development only.

## 10. Troubleshooting

| Error | Cause and solution |
|---|---|
| `P1000: Authentication failed` | The password in `.env` does not match your PostgreSQL password. |
| `P1003` or "database does not exist" | The `student_affairs` database has not been created, or the name in `.env` is incorrect. |
| `P1012` "Argument url is missing" | A Prisma version other than `6.19.3` is installed. Run `npm install` and verify with `npx prisma -v`. |
| `Cannot find module '@prisma/client'` or "did not initialize yet" | Run `npx prisma generate`. |
| Pasted command fails with `[200~npm: command not found` | A terminal paste artifact. Type the command manually or paste with `Shift+Insert`. |
| Commands run in the wrong folder (a second `package.json` appears) | Delete the extra `package.json`, `package-lock.json`, and `node_modules` outside `backend`, then return to `backend`. |

## 11. Project Notes

- The AI agent (regulations assistant) is planned as a separate FastAPI service, and the NestJS backend will communicate with it over HTTP.
- Access control is role-based (`ADMIN`, `STAFF`, `STUDENT`) using a single `User` table.
- National ID numbers are sensitive data and must not appear in application logs.