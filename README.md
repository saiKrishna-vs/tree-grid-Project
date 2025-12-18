# Client Dashboard (Tree & Grid Viewer)

## Project Description
This is a comprehensive full-stack application designed to visualize and manage client data. It features a responsive dashboard with a dual-pane layout: a "Gender/Age Tree" sidebar for filtering and a "Client Grid" for displaying detailed client records. The application allows users to toggle between Table and Card views, filter by demographics, and supports dark/light mode theming.

**Key Features:**
*   **Dynamic Filtering:** Filter clients by Gender and Age Group using the interactive sidebar.
*   **Dual Views:** Toggle between a data-rich Table View and a visual Card View for client lists.
*   **Responsive Design:** Fully responsive layout that adapts to mobile, tablet, and desktop screens.
*   **Dark & Light Mode:** Seamless theme switching with persistent user preference.
*   **Real-time Data:** Fetches data efficiently from a backend API.

## Tech Stack
*   **Frontend:** React (Vite), Material UI (MUI)
*   **Backend:** Node.js, Express.js
*   **Database:** NeonDB (PostgreSQL)
*   **ORM:** Prisma
*   **Styling:** CSS-in-JS (MUI System), Responsive Flex/Grid Layouts

## API Documentation
The backend provides the following RESTful endpoints:

### 1. Get Gender List
*   **Endpoint:** `GET /api/getGenderList`
*   **Description:** Retrieves a list of all distinct genders present in the database, along with their respective counts and detailed age group distributions.
*   **Usage:** Used to populate the "Gender Tree" sidebar.

### 2. Find Count of Gender
*   **Endpoint:** `GET /api/findCountOfGender/:gender`
*   **Description:** Returns the total count of clients for a specific gender.
*   **Parameters:** `gender` (string) - The gender to count (e.g., 'Male').

### 3. Get Clients for Age
*   **Endpoint:** `GET /api/getClientsForAge`
*   **Description:** Retrieves a list of clients filtered by gender and a specific age range.
*   **Query Parameters:**
    *   `gender`: The selected gender.
    *   `lowAge`: The minimum age (inclusive).
    *   `highAge`: The maximum age (inclusive).
*   **Usage:** Used to populate the "Client Grid" when an age group is selected.

## Setup Instructions

### Prerequisites
*   Node.js (v16 or higher)
*   npm or yarn

### 1. Clone the Repository
```bash
git clone <repository_url>
cd <repository_name>
```

### 2. Backend Setup
Navigate to the backend directory and install dependencies:
```bash
cd backend
npm install
```

**Environment Variables:**
Create a `.env` file in the `backend` directory and add your NeonDB connection string:
```env
DATABASE_URL="postgres://<user>:<password>@<host>/<dbname>?sslmode=require"
PORT=5000
```

**Database Migration & Seeding:**
Run migration to set up the schema and seed the database with initial data:
```bash
npx prisma generate
npx prisma db push
node seed.js # Optional: Seeds the database with dummy data
```

**Start the Server:**
```bash
npm start
# Server will run on http://localhost:5000
```

### 3. Frontend Setup
Open a new terminal, navigate to the frontend directory, and install dependencies:
```bash
cd frontend
npm install
```

**Start the Frontend:**
```bash
npm run dev
# Application will open at http://localhost:5173 (or similar)
```

## Folder Structure
*   `/backend` - Express server, Prisma schema, and API routes.
*   `/frontend` - React application, Components, and Assets.
