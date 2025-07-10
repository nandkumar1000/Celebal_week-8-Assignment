

# 📁 Express.js Advanced Features Assignment

This project is a Node.js + Express.js backend server that demonstrates advanced features including:

- ✅ File Upload with Cloudinary
- ✅ Centralized Error Handling
- ✅ Third-Party API Integration (Public APIs)
- ✅ File Type/Size Validation
- ✅ Static File Serving with Upload Form
- ✅ Logger Utility
- ✅ Environment Variable Management via `.env`

---

## 🚀 Features

| Feature                         | Description                                                                 |
|--------------------------------|-----------------------------------------------------------------------------|
| 📤 **File Upload**              | Uploads files to [Cloudinary](https://cloudinary.com/) using `multer`      |
| 🛑 **Error Handling**           | Custom middleware to handle application-level errors                       |
| 🔌 **Third-Party API**          | Fetches public API data using `axios`                                      |
| ✅ **Validation**               | Validates file type (`jpg/png`) and file size (max 2MB) before upload       |
| 🌍 **Static File Hosting**      | Serves HTML frontend using `express.static()`                              |
| 🧠 **Logger Utility**           | Logs messages with timestamps via `utils/logger.js`                        |
| 🔐 **Environment Configuration**| Uses `dotenv` to manage API keys and config securely                       |

---

## 📁 Project Structure

```

project-root/
│
├── index.js                     # Main server entry point
├── .env                         # Environment variables
├── config/
│   └── cloudinary.js            # Cloudinary configuration
├── controllers/
│   ├── uploadController.js      # File upload logic
│   └── apiController.js         # Third-party API handler
├── middlewares/
│   ├── errorHandler.js          # Global error middleware
│   └── uploadMiddleware.js      # Multer setup for file upload
├── routes/
│   ├── uploadRoutes.js          # Upload routes
│   └── apiRoutes.js             # External API routes
├── services/
│   └── apiService.js            # Axios call to external APIs
├── utils/
│   ├── logger.js                # Logging utility
│   └── validateFile.js          # File type/size validation
├── uploads/                     # Temporary local file storage
└── public/
└── index.html               # Frontend file upload form

````

---

## 🌐 Frontend Upload Form

This form lets you upload a file directly from the browser using the `/api/upload` endpoint.

### `public/index.html`:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>File Upload</title>
</head>
<body>
  <h1>Upload a File</h1>
  <form action="/api/upload" method="POST" enctype="multipart/form-data">
    <input type="file" name="file" required />
    <button type="submit">Upload</button>
  </form>
</body>
</html>
````

Once your server is running, open [http://localhost:3000](http://localhost:3000) to access this form.

---

## ⚙️ Installation

1. **Clone the repository**

   ```bash
   git clone https://github.com/nandkumar1000/Celebal_week-8-Assignment
   cd express-file-upload-assignment
   ```

2. **Install dependencies**

   ```bash
   npm install
   ```

3. **Create `.env` file**

   ```env
   PORT=3000
   CLOUDINARY_CLOUD_NAME=your_cloud_name
   CLOUDINARY_API_KEY=your_api_key
   CLOUDINARY_API_SECRET=your_api_secret
   ```

4. **Run the server**

   ```bash
   npx nodemon index.js
   ```

---

## 🧪 API Endpoints

### 🔼 Upload File

```
POST /api/upload
```

* Accepts `multipart/form-data` with field name: `file`
* Returns Cloudinary-hosted image URL

### 🔽 Fetch Public APIs

```
GET /api/thirdparty
```

* Fetches data from: [https://api.publicapis.org/entries](https://api.publicapis.org/entries)

---

## 🛠 Technologies Used

* Node.js
* Express.js
* Multer
* Cloudinary SDK
* Axios
* Dotenv

---

## 🧠 Bonus Features

| Feature                   | Status      | Description                                   |
| ------------------------- | ----------- | --------------------------------------------- |
| File Type/Size Validation | ✅ Done      | Only accepts `.jpg` or `.png` files below 2MB |
| Logger Utility            | ✅ Done      | Console logger with timestamps                |
| Frontend HTML Upload      | ✅ Done      | Accessible at `/` route                       |
| .env Config Management    | ✅ Done      | All sensitive info in `.env`                  |
| Unit Tests with Jest      | 🟡 Optional | Can be added for controller logic             |

---

## 👨‍💻 Author

**Nand Kumar Sahu**
Assignment for backend file upload and API integration
[GitHub](https://github.com/nandkumar1000)

