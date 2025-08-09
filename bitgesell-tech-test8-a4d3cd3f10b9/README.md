# Bitgesell Take-Home Assessment

This repository contains the fixed backend and frontend code for the Bitgesell Senior Software Engineer take-home assessment.

## Project Overview

- Backend: Node.js Express API with async file operations, cached stats, pagination, and search.
- Frontend: React app with safe fetches (AbortController), pagination, search, and virtualized item list.
- Unit tests for backend routes using Jest and Supertest.
- Clear instructions to run the project and tests.

## Requirements

- Node.js v18.x
- npm

## Setup & Run

### Backend

```bash
cd backend
npm install
npm test
npm start

---

# 3. SOLUTION.md (paste this in root SOLUTION.md)

```md
# SOLUTION

## Summary of Changes

- Replaced all blocking `fs.readFileSync` calls with async `fs.promises.readFile` in backend.
- Implemented server-side search and pagination for `/api/items`.
- Added caching for `/api/stats` endpoint using file modification time to avoid recomputation on every request.
- Fixed React frontend memory leak by using `AbortController` to cancel fetches on component unmount.
- Added server-driven pagination and search to the frontend.
- Integrated `react-window` for virtualization of long lists to improve UI performance.
- Added loading indicators for better UX during fetches.
- Added comprehensive Jest + Supertest unit tests for backend routes covering both happy path and error cases.

## Trade-offs & Considerations

- The caching strategy uses in-memory cache keyed by file modification time, which is simple and effective but not persistent across server restarts.
- Frontend improvements prioritize memory safety and performance; UI styling was lightly polished due to time constraints.
- Error handling added in backend routes to return meaningful HTTP status codes and error messages.
- Tests focus on main routes; additional integration or e2e tests could be added for complete coverage.

## How to Run

1. Install dependencies:

```bash
cd backend
npm install
cd ../frontend
npm install
