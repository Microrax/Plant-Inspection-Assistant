# Plant Inspection Assistant

**Plant Inspection Assistant** is a mobile application designed to streamline and simplify inspection tasks for operators in industrial environments. Using QR codes for both authentication and inspection point identification, the app ensures accurate data collection and efficient workflows on the field.

> ⚠️ **Note:** The source code for this project is **not open-source**. It was developed as a **private, custom solution for a company** and is not available for public distribution.

## 📲 Key Features

- 🔐 **Login via QR Code**  
  Operators scan a personal QR code to authenticate. Credentials are verified through a secure API connected to a **MySQL** database.

- 🏷️ **Inspection Point QR Scanning**  
  Each inspection point in the plant has a unique QR code. Scanning it loads a corresponding inspection form.

- 📝 **Dynamic Inspection Forms**  
  Each form includes:
  - ✅❌ **Yes/No** questions
  - 🧩 **Predefined text fragments**
  - 🧾 **Detailed notes area** for optional extended input

- ✍️ **Inspector Signature**  
  Before submitting a form, the inspector must provide a digital signature. This is sent along with the inspection data.

- ☁️ **Data Storage**  
  - ✅ **Inspector login credentials** are stored and validated against a **MySQL** database via an authentication API.
  - ✅ **Inspection data** is submitted to a separate API that stores it in a **MongoDB** non-relational database.

## ⚙️ How It Works

1. **Operator logs in** by scanning their personal QR code.
2. The app authenticates the user via a **.NET Core API** connected to **MySQL**.
3. The operator scans the QR code located at an inspection point.
4. A specific form is loaded dynamically.
5. Before the form begins, the operator provides a **digital signature**.
6. The operator completes the form using **Yes/No**, **predefined text**, and **detailed comments**.
7. Upon submission, the entire inspection (including the signature) is sent to a **MongoDB database** via a second **.NET Core API**.

## 🛠️ Technologies Used

- **Android Studio (Java)** – Native mobile app development
- **ZXing** – QR code scanning
- **MySQL** – Stores and verifies inspector credentials
- **MongoDB** – Stores inspection reports and signatures
- **.NET Core (C#)** – Backend APIs for:
  - **Authentication** (MySQL)
  - **Inspection submission** (MongoDB)
- **IIS (Internet Information Services)** – Used to deploy both APIs
- **RESTful APIs** – For secure communication between app and backend
- **Multithreading** – To handle networking and QR scanning without blocking the UI

## 🔐 Security

- Secure login with hashed password validation
- Digital signature capture per inspection
- QR data validation and encoding
  
## ✅ Use Cases

- Routine and scheduled maintenance inspections
- Safety checklists and incident reporting
- Digitalization of paper-based inspection processes
