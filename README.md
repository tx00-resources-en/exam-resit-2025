### Exam

---

## Overview

This exam revolves around modifying a Book App, with both frontend and backend components provided. The **GET** routes are public, while the **POST**, **PUT**, and **DELETE** routes are protected. Functional tests are also included.

The exam is worth 300 points, distributed across **six** iterations as follows:
- Iteration 1: **50 points**
- Iteration 2: **50 points**
- Iteration 3: **50 points**
- Iteration 4: **50 points**
- Iteration 5: **50 points**
- Iteration 6: **50 points**


- Note: 
  - The last commit must be made within 3 hours of starting the exam.
  - Please use a separate branch for iteration 5 and 6.

---

## Iteration 1: **50 points**

This iteration focuses on setting up the environment and running the app.

1. **Clone this Repository**  
   - Both the backend and frontend contain outdated dependencies.
   - Update all packages so that running `npm install` in both folders completes without any warnings. 

2. **Install Backend Dependencies**  
   - Rename `.env.example` to `.env` in the backend directory.
   - Install the necessary dependencies:
      ```sh
      npm install express dotenv cors mongoose jsonwebtoken bcryptjs colors validator
      ```
   - Install Dev Dependencies
      ```sh
      npm install nodemon jest supertest  cross-env -D
      ```
   - Run the Tests and ensure all provided tests **pass** at this stage.  
      ```sh
      npm test
      ```      
   - Run the backend:
     ```sh
     npm run dev
     ```

3. **Install Frontend Dependencies & Start the App**  
   - Navigate to the frontend directory, install dependencies, and start the app:
     ```sh
     cd frontend
     npm install
     npm run dev
     ```

4. **Access the App**  
   - Open [http://localhost:3000](http://localhost:3000) to view the app.


5. **Push to a Private GitHub Repository**  
   - Make the project directory a PRIVATE git repository, push to GitHub.
   - Add `55d41251` as a collaborator.

---

## Iteration 2: **50 points**

1. **Backend Update:**
   - Modify the `Book` model to match the schema below.
   - Test the backend using Postman, and verify that the `Book` routes (CRUD operations) work as expected with the new schema.

```javascript
const bookSchema = new mongoose.Schema({
  title: { type: String, required: true },
  summary: { type: String, required: true },
  language: { type: String, required: true },
  publisher: { type: String, required: true },
  genre: { type: String, required: true },
  availability: {
    isAvailable: { type: Boolean, required: true },
    dueDate: { type: Date },
    borrower: { type: String }
  },
  user_id: { type: mongoose.Schema.Types.ObjectId, ref: 'User', required: true } 
}, { timestamps: true });
```


2. **Frontend Update:**
   - Adjust the frontend forms and API calls to reflect the updated `Book` model.
   - Test the frontend to confirm it integrates smoothly with the backend changes.

3. **Commit and Push:**
   - After making the changes, create a **second commit** with a descriptive message (e.g., "Updated Book model and frontend for new availability structure, tested with Postman").
   - In the commit message, *indicate whether the code is fully functional or if there are any remaining issues*.
   - Push the changes to GitHub.

---

## Iteration 3: **50 points**

Update the `User` model to match this schema:

```javascript
const userSchema = new Schema({
  name: { type: String, required: true },
  email: { type: String, required: true, unique: true },
  password: { type: String, required: true },
  companyName: { type: String, required: true },
  githubUsername: { type: String, required: true },
  phoneNumber: { type: String, required: true },
}, { timestamps: true, versionKey: false });
```

1. Start by updating the backend and test with Postman.
2. Make necessary frontend changes to ensure smooth functioning.
3. Make a **third** commit with a descriptive message, then push the changes to GitHub. 
   - In the commit message, *indicate whether the code is fully functional or if there are any remaining issues*.
   - Push the changes to GitHub.
   
---

## Iteration 4: **50 points**

Update the test cases to match the modified models.

1. Adjust the `users` tests to work with the updated API.
2. Update the `books` tests to ensure compatibility with the API.
3. Make a **fourth** commit with a descriptive message, then push the changes to GitHub. 
   - In the commit message, indicate whether the code is fully functional or if there are any remaining issues.
   - Push the changes to GitHub.
   

---

## Iteration 5: **50 points**

Refactor `AddBookPage` to Use `useField` Hook

1. Based on the `main` branch, create a new branch with a descriptive name.

2. **Refactor `AddBookPage.jsx`:**
   - In the file `frontend/src/pages/AddBookPage.jsx`, replace the current state hook usage for form fields with the `useField` hook from `frontend/src/hooks/useField.jsx`.
   - Ensure that all form fields (e.g., title, summary, genre) are updated to use the `useField` hook for state management.

3. **Test the refactored form:**
   - Verify that the form works correctly after the refactor (ensure fields update, validation works, and form submission behaves as expected).

4. **Commit and push changes:**
   - After refactoring and testing, commit with a descriptive message and push the changes to GitHub.
   - In the commit message, mention whether the code is fully functional or if any issues remain.
   - Push the branch to GitHub.
   
---

## Iteration 6: **50 points**

1. Based on the previous branch, create a new branch with a descriptive name.

2. The Login form crashes if the user enter wrong credentials. 
   - Resolve the crash that occurs when the user enters incorrect credentials.
   - If a complete solution isn't possible, implement a partial fix and ensure the app handles the error gracefully (e.g., displaying an error message rather than crashing).
   - Ensure proper error handling and logging.

3. **Commit and Push Changes:**
   - After fixing the issue, commit with a descriptive message.
   - In the commit message, specify whether the issue is fully resolved or if there are any remaining concerns.
   - Push the branch to GitHub.

<!-- 

---

## Bonus Iteration 7: **20 points**

Refactor the frontend to use the Context API.

1. Based on the previous branch, create a new branch with a descriptive name.

2. **Implement `AuthContext`:**
   - Create an `AuthContext` that manages authentication-related state.
   - Provide the `AuthContext` to the entire application by wrapping the necessary components in the context provider.
   - Ensure that components that need authentication information or actions consume the context properly.

3. **Test the implementation:**
   - Verify that the `AuthContext` works as expected across the app (e.g., logging in, logging out, accessing protected routes).

4. **Commit and push changes:**
   - After implementing and testing, commit with a descriptive message and push the changes to GitHub.
   - In the commit message, mention whether the code is fully functional or if there are any remaining issues.
   - Push the branch to GitHub.
-->