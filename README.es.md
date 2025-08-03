# ⚡ PHP DB Helper

Snippets útiles para desarrollo PHP moderno con soporte para:

-   Conexiones a bases de datos (PDO y MySQLi)
-   Transacciones seguras
-   Subida de archivos
-   Depuración rápida
-   Cierre de conexión
-   **Nuevo**: Snippets para HTML en archivos PHP

¡Ideal para quienes no quieren memorizar código repetitivo!

---

## ✨ Características

-   🔌 Conexión a bases de datos (PDO y MySQLi)
-   🔒 Consultas preparadas seguras
-   📂 Snippet para subir archivos con validación
-   ⚙️ Transacciones y manejo de errores
-   🐞 Snippets para depuración (`print_r`, `var_dump`)
-   🌐 Snippets para HTML en archivos PHP
-   📄 Código limpio, claro y reutilizable

---

## 🚀 Cómo usar

### Requisitos

    -   Visual Studio Code `^1.90.0`
    -   PHP `^7.4` o superior

1. Instala la extensión desde el Marketplace o como `.vsix`
2. Abre un archivo `.php` o `.html`
3. Escribe uno de los siguientes prefijos y presiona `Tab` o `Enter`:

---

## 📚 Lista de snippets

### PDO

| Prefijo            | Descripción                       |
| ------------------ | --------------------------------- |
| `pdo-conn`         | Conexión a MySQL con PDO          |
| `pdo-query`        | Consulta sql con parámetros       |
| `pdo-query-simple` | Consulta SQL simple               |
| `pdo-transaction`  | Transacción con manejo de errores |
| `pdo-close`        | Cerrar conexión PDO               |

### MySQLi

| Prefijo               | Descripción                         |
| --------------------- | ----------------------------------- |
| `mysqli-conn`         | Conexión a MySQL con MySQLi         |
| `mysqli-query`        | Consulta SQL con prepared statement |
| `mysqli-query-simple` | Consulta SQL simple                 |
| `mysqli-transaction`  | Transacción con rollback            |
| `mysqli-close`        | Cerrar conexión MySQLi              |

### Archivos

| Prefijo           | Descripción                             |
| ----------------- | --------------------------------------- |
| `php-upload-file` | Subir archivo con validación y guardado |

### Depuración

| Prefijo     | Descripción                      |
| ----------- | -------------------------------- |
| `debug-var` | Mostrar variable con `print_r()` |

### HTML en PHP

| Prefijo         | Descripción                    |
| --------------- | ------------------------------ |
| `echo-var-html` | Imprimir variable con `<?= ?>` |

---

## 💡 Ejemplos de uso

### Conexión PDO

```php
// Escribe: pdo-conn
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

### Subida de archivos

```php
// Escribe: php-upload-file
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

### HTML en PHP

```php
<!-- Escribe: echo-var-html -->
<?= $variable ?>
```

---

## 📞 Contacto

Para preguntas, soporte o colaboración, por favor contacta:

-   Andrés Gutiérrez Hurtado
-   Correo: [andres52885241@gmail.com](mailto:andres52885241@gmail.com)
-   LinkedIn: [Andrés Gutiérrez](https://www.linkedin.com/in/andr%C3%A9s-guti%C3%A9rrez-hurtado-25946728b/)
-   GitHub: [@AndresGutierrezHurtado](https://github.com/AndresGutierrezHurtado)
-   Portafolio: [Link portafolio](https://andres-portfolio-b4dv.onrender.com)
