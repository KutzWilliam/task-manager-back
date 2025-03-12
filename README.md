
# To-Do List API (NestJS + TypeORM + PostgreSQL)

## Objective

To-Do List API where users can create, retrieve, update, and delete tasks using **NestJS** and **TypeORM** with **PostgreSQL** for database management.

## Requirements

### NestJS:
- Use **NestJS** to build the API.

### TypeORM + PostgreSQL:
- Set up **TypeORM** with **PostgreSQL** as the database.
- Ensure database connection configuration in `.env` file, such as:
  ```bash
  POSTGRES_HOST=localhost
  POSTGRES_PORT=5432
  POSTGRES_USER=your_username
  POSTGRES_PASSWORD=your_password
  POSTGRES_DB=todolist
  ```
- Create a **Task** entity with the following fields:
  - `id`: auto-generated unique identifier (UUID or number).
  - `title`: string, required.
  - `description`: string, optional.
  - `status`: enum with values like "pending", "in-progress", "completed".
  - `createdAt`: timestamp of when the task was created (default to current time).
  - `updatedAt`: timestamp of when the task was last updated (auto-update).
  - `deletedAt`: timestamp of when the task was last deleted.

## API Endpoints

- **POST /tasks**: Create a new task. New tasks will start with status **pending**.
  - Request body: `{ title: string, description?: string }`

- **GET /tasks**: Retrieve all tasks.
  - Optional query parameters to filter by status.

- **GET /tasks/:id**: Retrieve a single task by id.

- **PATCH /tasks/:id**: Update a task’s title, description, or status.

- **DELETE /tasks/:id**: Soft delete a task by id.

## PostgreSQL Integration

- Use **TypeORM** to manage interactions with PostgreSQL.
- Set up a local PostgreSQL database for development.
- Implement **TypeORM** migrations to manage database schema changes.

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/KutzWilliam/task-manager-back.git
   ```

2. Navigate to the project directory:
   ```bash
   cd task-manager-back
   ```

3. Install dependencies:
   ```bash
   npm install
   ```

4. Perform the migration :
   ```bash
   npm run migration:run
   ```

5. Start the service :
   ```bash
   npm start
   ```


