# Changelog

All notable changes to the PHP DB Helper extension will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.0.0] - 2024-12-19

### Added

-   **Initial release** of PHP DB Helper extension
-   **PDO Database Snippets**:

    -   `pdo-conn`: MySQL connection with PDO
    -   `pdo-query`: SELECT query with parameters using bindParam
    -   `pdo-query-simple`: Simple SELECT query
    -   `pdo-transaction`: Transaction with error handling
    -   `pdo-close`: Close PDO connection

-   **MySQLi Database Snippets**:

    -   `mysqli-conn`: MySQL connection with MySQLi
    -   `mysqli-query`: SELECT query with prepared statements
    -   `mysqli-query-simple`: Simple SELECT query
    -   `mysqli-transaction`: Transaction with rollback
    -   `mysqli-close`: Close MySQLi connection

-   **File Upload Snippets**:

    -   `php-upload-file`: Secure file upload with validation and storage

-   **Debugging Snippets**:

    -   `debug-var`: Print variable content with `print_r()`

-   **HTML in PHP Snippets**:
    -   `echo-var-html`: Print variable with `<?= ?>` syntax

### Features

-   **Multi-language support**: Snippets work in `.php` and `.html` files
-   **Scope configuration**: Proper file type activation for each snippet
-   **Placeholder variables**: Interactive snippets with tab navigation
-   **Security-focused**: Prepared statements and secure file upload patterns
-   **Modern PHP practices**: PDO and MySQLi support with error handling

### Documentation

-   **README.md**: Comprehensive documentation with usage examples
-   **vsc-extension-quickstart.md**: Development guide for contributors
-   **CHANGELOG.md**: Version history and changes tracking

### Project Structure

```
pdo-snippets/
├── package.json                    # Extension configuration
├── README.md                      # Main documentation
├── vsc-extension-quickstart.md    # Development guide
├── CHANGELOG.md                   # This file
└── snippets/
    ├── php.code-snippets          # PHP-specific snippets
    └── html.code-snippets         # HTML snippets for PHP files
```

### Technical Details

-   **VS Code Engine**: `^1.90.0`
-   **PHP Version**: `^7.4` or higher
-   **Categories**: Snippets
-   **Languages**: PHP, HTML
-   **File Extensions**: `.php`, `.html`

### Development Setup

-   **Extension Host**: VS Code Extension API
-   **Snippet Format**: JSON with VS Code snippet syntax
-   **Testing**: Local development with F5 debugging
-   **Packaging**: VSCE for `.vsix` creation

### Author

**Andrés Gutiérrez Hurtado**

-   Email: andres52885241@gmail.com
-   LinkedIn: [Andrés Gutiérrez](https://www.linkedin.com/in/andr%C3%A9s-guti%C3%A9rrez-hurtado-25946728b/)
-   GitHub: [@AndresGutierrezHurtado](https://github.com/AndresGutierrezHurtado)
-   Portfolio: [Link portfolio](https://andres-portfolio-b4dv.onrender.com)

---

## [Unreleased]

### Planned

-   Additional database operation snippets (INSERT, UPDATE, DELETE)
-   More debugging and logging snippets
-   Framework-specific snippets (Laravel, Symfony)
-   Unit testing snippets
-   API development snippets

### Known Issues

-   None reported yet
