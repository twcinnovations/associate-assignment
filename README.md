# TWC Associate Software Engineer Assignment 📑

As the next step, your task is to complete a **full-stack project** to test your understanding of modern development practices. This assignment is designed to assess your skills in creating a scalable application, writing clean and maintainable code, implementing secure authentication, and working with containerized environments.

---

## Your Challenge - **TWC Contacts Portal App** 🖥️

![Login.png](assets/215062bdc7848a79a3f42019b57d4af655bc177e.png)

Your task is to build a **Contacts Portal App** with the following features:  
1. A **login page** for authentication.  
2. A **welcome page** displayed after login.  
3. A page to **add a new contact** via a form.  
4. A page to **view, edit, and delete contacts** in a table.  

All pages should adhere to the provided **UI design** and be desktop-friendly.  
**Design File:** [Contacts Portal UI Design](https://www.figma.com/file/4f8t98A25BOn8VmAvymWyF/Contacts-Portal---Intern?type=design&node-id=0%3A1&mode=design&t=HnIJJSl4OTwfHqpn-1)

---

## Key Areas to Be Assessed 🧩

This assignment will test your understanding of the following key areas:  

1. **Frontend Development** 🌐  
   - Building reusable and maintainable components using **React.js** (Vite with TypeScript template).  
   - Routing with **react-router-dom**.  
   - Form validation using **Zod** and **React Hook Form**.  
   - Component-level state management, data fetching, and refetching with **TanStack Query** (e.g., fetching contacts, handling mutations).  
   - Global state management with **React Context API** for handling global application states such as authentication.  
   - Styling with **TailwindCSS**.  

2. **Backend Development** ⚙️  
   - Building REST APIs with **Nest.js**.  
   - Implementing secure, cookie-based **JWT authentication**.  
   - Protecting routes with **Nest.js Route Guards**.  
   - Using proper validation with **DTOs** and `class-validator`.  
   - Storing passwords securely using best practices (e.g., hashing with `bcrypt`).  

3. **Database Management** 🗄️  
   - Use either **PrismaORM**, **TypeORM**, or direct **MySQL/MongoDB queries** (no ORM) to interact with the database.  
   - Seed the database with the following data when the application starts for the first time (if not already present):  
     - **Demo User:**  
       - Email: `admin@admin.com`  
       - Password: `admin`  
     - **Dummy Contacts (3 entries):** Include at least three contacts as sample data.  

4. **System Design** 🛠️  
   - Configuring **CORS** for secure API communication.  
   - Writing **Dockerfiles** for frontend and backend services.  
   - Orchestrating the system using **Docker Compose**.  
   - Ensure the entire system can be started locally using the command:  
     ```bash
     docker compose up
     ```  

5. **Security Practices** 🔒  
   - Protecting sensitive data.  
   - Implementing route guards to prevent unauthorized access.  

6. **Error Handling** 🚦  
   - Handling and displaying meaningful error messages to users.  
   - Logging errors for debugging.  

7. **Code Quality** 🧹  
   - Writing clean, modular, and well-documented **TypeScript** code.  
   - Adhering to best practices for maintainability and scalability.  

---

## Key Features for Making Your App Stand Out 💡

- **Implement Social Sign-On (SSO):** Add Google authentication for users (refer to the register page in the UI).  
- **Cloud Deployment:** Deploy your services in a cloud platform of your choice (e.g., **Google Cloud**, **AWS**, **DigitalOcean**, or others).  

---

## Project Requirements ✅

### **Frontend Routes**
1. `/login` - **Login Page**  
   - Allows users to log in using their email and password.  
   - Displays error messages for incorrect credentials.
   - Redirect users to the this page if they attempt to access other routes without being authenticated.

2. `/register` - **Register Page**  
   - Allows users to register with their email, password, and optional Google authentication (SSO).  
   - Validates inputs using **Zod** and **React Hook Form**.  
   - Displays error messages for invalid inputs or failed registrations.  

3. `/` - **Welcome Page**  
   - Displays a welcome message after login.  
   - Includes a button to navigate to the “Add Contact” page.  

4. `/contacts/new` - **Add Contact Page**  
   - Displays a form to add a new contact.  
   - Validates inputs (e.g., name, email) using **Zod** and **React Hook Form**.  

5. `/contacts` - **View Contacts Page**  
   - Displays a table of all contacts.  
   - Includes options to **edit** or **delete** each contact.  

6. `/contacts/edit/:id` - **Edit Contact Page**  (Same UI as Add Contact Page)
   - Displays a form to update the details of an existing contact.  
   - Pre-fills the form with the contact's current details.  
   - Validates updated inputs using **Zod** and **React Hook Form**.  
   - Displays error messages for invalid updates.
---

### **Backend Routes**

1. `POST /auth/login`  
   - Authenticates users and generates a JWT token.  

2. `POST /auth/register`  
   - Allows new users to register (optional but a plus).  

3. `GET /contacts`  
   - Fetches a list of all contacts for the authenticated user.  

4. `POST /contacts`  
   - Adds a new contact.  

5. `PUT /contacts/:id`  
   - Updates an existing contact by ID.  

6. `DELETE /contacts/:id`  
   - Deletes a contact by ID.  

---

### **Environment Configuration** 🌍

- Include an `.env.development` file in both the **web** and **api** projects with all the necessary environment variables for local development.  
- Document these variables and their usage in the `README.md` file.  

---

### **System Architecture** 🏗️

1. **Docker Setup**  
   - Write separate **Dockerfiles** for the frontend (`web/`) and backend (`api/`).  
   - Use a `docker-compose.yml` file to orchestrate:  
     - `api` (Nest.js backend)  
     - `web` (React.js frontend)  
     - `db` (MySQL/MongoDB database).  
   - Ensure the project can be started in a local environment with the following command:  
     ```bash
     docker compose up
     ```  

2. **Environment Configuration**  
   - Store sensitive data like database credentials, JWT secret, and CORS settings in `.env` files.  
   - Document how to set up and run the project in the `README.md`.  

---

## Submission Guidelines 📤

1. **GitHub Repository Structure**  
   - Use a single public GitHub repository named `twc-contacts-portal`.  
   - Structure your repository as:  
     ```
     twc-contacts-portal/
     ├── api/          # Nest.js backend
     ├── web/          # React.js frontend
     └── docker-compose.yml
     ```

2. **Deadline**  
   - You have **14 days** to complete the assignment.  
   - Share your GitHub repository link and any test credentials by the deadline.  

---

## Important Notes 📝  

1. **Usage of LLMs (Large Language Models):**  
   - LLMs like ChatGPT may be used **only for research and learning purposes.**  
   - Many LLMs provide outdated or incorrect information. You **must refer to official documentation** to verify and implement solutions.  
   - Blindly copying code from LLMs is considered plagiarism and is strictly prohibited.  

2. **Password Security:**  
   - Always store passwords securely using best practices, such as hashing with `bcrypt`. Do not store passwords in plain text.  

3. **Partial Completion Is Okay:**  
   - The project does not need to be 100% complete at submission.  
   - This assignment is meant to test your understanding of the technologies. Demonstrating clear implementation of concepts is more important than completing every feature.

---

<div align="center">  
<h1> Have fun building! 🚀 </h1>  
</div>
