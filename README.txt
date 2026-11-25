What I implemented in the ElderEase Project:

1. Created a new ASP.NET Core Web API project and configured Entity Framework Core with the database (SQL Server or PostgreSQL).
2. Designed the database tables: Users, HelpRequests, Appointments, and RefreshTokens — along with their relationships.
3. Built AuthController: user registration (Register), login (Login), and issuing a time-limited JWT Token.
4. Built HelpRequestsController in full: GET (list of requests with status filtering), POST (add a new request), PUT (update status), and DELETE (delete).
5. Built AppointmentsController: GET (list of appointments per user), POST (book a new appointment with conflict checking), and DELETE (cancel an appointment).
6. Built UsersController for the admin: view the list of users, update roles (Admin / User), and delete a user account.
7. Added Seed Data to the database: 10 sample help requests, 5 appointments, and 3 users — for testing the user interface.
8. Documented all endpoints in Swagger with full details for Request Body, Response, and HTTP status codes (200, 201, 400, 401, 404).
