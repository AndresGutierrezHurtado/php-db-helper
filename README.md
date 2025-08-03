# ⚡ PHP DB Helper

Useful snippets for modern PHP development with support for:

-   Database connections (PDO and MySQLi)
-   Secure transactions
-   File uploads
-   Quick debugging
-   Connection closing
-   **New**: HTML snippets for PHP files

Perfect for those who don't want to memorize repetitive code!

<video width="640" height="360" controls>
    <source src="https://github.com/AndresGutierrezHurtado/php-db-helper/extra/demo.mp4" type="video/mp4">
    Your browser does not support video playback.
</video>

---

## ✨ Features

-   🔌 Database connections (PDO and MySQLi)
-   🔒 Secure prepared queries
-   📂 File upload snippet with validation
-   ⚙️ Transactions and error handling
-   🐞 Debugging snippets (`print_r`, `var_dump`)
-   🌐 HTML snippets for PHP files
-   📄 Clean, clear, and reusable code

---

## 🚀 How to use

### Requirements

    -   Visual Studio Code `^1.90.0`
    -   PHP `^7.4` or higher

1. Install the extension from the Marketplace or as `.vsix`
2. Open a `.php` or `.html` file
3. Type one of the following prefixes and press `Tab` or `Enter`:

---

## 📚 Snippet list

### PDO

| Prefix             | Description                     |
| ------------------ | ------------------------------- |
| `pdo-conn`         | MySQL connection with PDO       |
| `pdo-query`        | SQL query with parameters       |
| `pdo-query-simple` | Simple SQL query                |
| `pdo-transaction`  | Transaction with error handling |
| `pdo-close`        | Close PDO connection            |

### MySQLi

| Prefix                | Description                       |
| --------------------- | --------------------------------- |
| `mysqli-conn`         | MySQL connection with MySQLi      |
| `mysqli-query`        | SQL query with prepared statement |
| `mysqli-query-simple` | Simple SQL query                  |
| `mysqli-transaction`  | Transaction with rollback         |
| `mysqli-close`        | Close MySQLi connection           |

### Files

| Prefix            | Description                             |
| ----------------- | --------------------------------------- |
| `php-upload-file` | Upload file with validation and storage |

### Debugging

| Prefix      | Description                    |
| ----------- | ------------------------------ |
| `debug-var` | Show variable with `print_r()` |

### HTML in PHP

| Prefix          | Description                  |
| --------------- | ---------------------------- |
| `echo-var-html` | Print variable with `<?= ?>` |

---

## 💡 Usage examples

### PDO Connection

```php
// Type: pdo-conn
$host = '127.0.0.1';
$dbname = 'database_name';
$user = 'root';
$password = '';
$port = '3306';
$charset = 'utf8mb4';

try {
    $conn = new PDO("mysql:host=$host;dbname=$dbname;port=$port;charset=$charset", $user, $password);
    $conn->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);

    echo 'Connection successful';
} catch (PDOException $e) {
    echo 'Connection error: ' . $e->getMessage();
    exit();
}
```

### File Upload

```php
// Type: php-upload-file
if (isset($_FILES["filename"]) && $_FILES["filename"]["error"] === UPLOAD_ERR_OK) {
    $fileTmpPath = $_FILES["filename"]["tmp_name"];
    $fileName = $_FILES["filename"]["name"];
    $fileSize = $_FILES["filename"]["size"];
    $fileType = $_FILES["filename"]["type"];

    $fileExtension = strtolower(pathinfo($fileName, PATHINFO_EXTENSION));
    $newFileName = uniqid("file_") . '.' . $fileExtension;

    $uploadDir = __DIR__ . "/uploads/";
    $destPath = $uploadDir . $newFileName;

    if (!is_dir($uploadDir)) {
        mkdir($uploadDir, 0755, true);
    }

    if (move_uploaded_file($fileTmpPath, $destPath)) {
        echo 'File uploaded successfully: ' . $newFileName;
    } else {
        echo 'Error moving the uploaded file.';
    }
}
```

### HTML in PHP

```php
<!-- Type: echo-var-html -->
<?= $variable ?>
```

---

## 📞 Contact

For questions, support, or collaboration, please contact:

-   Andrés Gutiérrez Hurtado
-   Email: [andres52885241@gmail.com](mailto:andres52885241@gmail.com)
-   LinkedIn: [Andrés Gutiérrez](https://www.linkedin.com/in/andr%C3%A9s-guti%C3%A9rrez-hurtado-25946728b/)
-   GitHub: [@AndresGutierrezHurtado](https://github.com/AndresGutierrezHurtado)
-   Portfolio: [Portfolio link](https://andres-portfolio-b4dv.onrender.com)

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
