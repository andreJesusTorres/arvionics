# 🛩️ Arvionics - Aviation Electronics Management System

[![Windows](https://img.shields.io/badge/Windows-Desktop%20App-0078D6?logo=windows&logoColor=white)](https://www.microsoft.com/windows)
[![SQLite](https://img.shields.io/badge/SQLite-Database-003B57?logo=sqlite&logoColor=white)](https://www.sqlite.org/)
[![C++](https://img.shields.io/badge/C++-Application-00599C?logo=c%2B%2B&logoColor=white)](https://isocpp.org/)
[![License](https://img.shields.io/badge/License-Proprietary-red.svg)](LICENSE)

> Professional aviation electronics inventory and sales management system for aviation businesses. **This project is part of my professional portfolio to demonstrate my development skills and practices.**

## 📋 Table of Contents

- [✨ Features](#-features)
- [🛠️ Technologies](#️-technologies)
- [📦 Installation](#-installation)
- [🎮 Usage](#-usage)
- [🏗️ Project Structure](#️-project-structure)
- [🗄️ Database Schema](#️-database-schema)
- [🧪 Testing](#-testing)
- [📄 License](#-license)

## ✨ Features

### 🎯 Core Functionality
- **Inventory Management**: Track aviation electronics stock with detailed product information
- **Sales Processing**: Complete sales workflow with tax calculation (IVA)
- **Product Catalog**: Comprehensive database of aviation equipment and accessories
- **Multi-Branch Support**: Manage inventory across different business locations
- **Real-time Stock Updates**: Automatic inventory tracking and updates

### 🎨 User Experience
- **Intuitive GUI**: User-friendly Windows desktop interface
- **Audio Feedback**: Sound effects for user interactions (buttons, errors, confirmations)
- **Visual Branding**: Professional aviation-themed interface with light/dark modes
- **Receipt Generation**: Automatic ticket/receipt creation for sales
- **Data Integrity**: Foreign key relationships ensuring data consistency

## 🛠️ Technologies

### Application
| Technology | Version | Purpose |
|------------|---------|---------|
| [C++](https://isocpp.org/) | - | Core application development |
| [Windows API](https://docs.microsoft.com/en-us/windows/win32/) | - | GUI and system integration |
| [SQLite](https://www.sqlite.org/) | 3.x | Embedded database management |

### Assets
| Technology | Purpose |
|------------|---------|
| [WAV Audio](https://en.wikipedia.org/wiki/WAV) | Sound effects and user feedback |
| [PNG Graphics](https://en.wikipedia.org/wiki/Portable_Network_Graphics) | UI elements and branding |

### Development Tools
- Windows Development Environment
- SQLite Database Browser
- Audio/Graphics editing tools

## 📦 Installation

### Prerequisites
- Windows 10/11 (64-bit)
- No additional dependencies required (self-contained executable)

### Quick Start

1. **Download the application**
   ```bash
   # Download Arvionics.exe and associated files
   ```

2. **Extract files to desired location**
   ```bash
   # Ensure all files are in the same directory:
   # - Arvionics.exe
   # - ArvionicsSQL.db
   # - images/ folder
   # - sounds/ folder
   ```

3. **Run the application**
   ```bash
   # Double-click Arvionics.exe or run from command line:
   ./Arvionics.exe
   ```

4. **Access the application**
   - The application will start with the main inventory interface
   - Database is automatically initialized on first run

## 🎮 Usage

### Getting Started
1. **Launch Application**: Run `Arvionics.exe` to start the system
2. **Navigate Interface**: Use the main menu to access different modules
3. **Manage Inventory**: Add, edit, or view aviation electronics stock
4. **Process Sales**: Create sales transactions with automatic calculations

### Key Features Usage

#### Inventory Management
```sql
-- Example: Add new aviation equipment
INSERT INTO avionics_Stock (branch, model, year_manufacture, price) 
VALUES ('Main Branch', 'Garmin G1000', '2023', '45000');
```

#### Sales Processing
```sql
-- Example: Create a sale with automatic tax calculation
INSERT INTO avionics_Sale (product, date, subtotal, iva, total) 
VALUES ('Garmin GTR-200 Com', '2024-01-15', 1299.00, 259.80, 1558.80);
```

## 🏗️ Project Structure

```
arvionics/
├── 🖥️ Arvionics.exe              # Main application executable
├── 🗄️ ArvionicsSQL.db           # SQLite database
├── 🎨 Arvionics.ico              # Application icon
├── 📁 images/                    # UI graphics and branding
│   ├── 🏢 Arvionics_Logo.png     # Company logo
│   ├── 🎫 Ticket.png             # Receipt template
│   ├── ℹ️ info.png               # Information icon
│   ├── 🌙 Arvionics_Dark.png     # Dark theme assets
│   └── ☀️ Arvionics_Light.png    # Light theme assets
└── 🔊 sounds/                    # Audio feedback
    ├── 🎵 start.wav              # Application startup sound
    ├── ❌ error.wav              # Error notification
    ├── ✅ ok.wav                 # Success confirmation
    └── 🔘 button.wav             # Button click sound
```

## 🗄️ Database Schema

### Core Tables

#### `avionics_Stock`
| Column | Type | Description |
|--------|------|-------------|
| `id` | INTEGER | Primary key (auto-increment) |
| `branch` | TEXT | Business location |
| `model` | TEXT | Product model/name |
| `year_manufacture` | TEXT | Manufacturing year |
| `price` | TEXT | Product price |

#### `avionics_Sale`
| Column | Type | Description |
|--------|------|-------------|
| `id` | INTEGER | Primary key (auto-increment) |
| `product` | TEXT | Product reference (FK to Stock) |
| `date` | TEXT | Sale date |
| `subtotal` | REAL | Pre-tax amount |
| `iva` | REAL | Tax amount |
| `total` | REAL | Final sale amount |

### Relationships
- `avionics_Sale.product` → `avionics_Stock.model` (Foreign Key)

## 🧪 Testing

### Database Testing
```bash
# Test database connectivity
sqlite3 ArvionicsSQL.db "SELECT COUNT(*) FROM avionics_Stock;"

# Verify foreign key constraints
sqlite3 ArvionicsSQL.db "PRAGMA foreign_key_check;"
```

### Application Testing
- ✅ GUI functionality testing
- ✅ Database operations validation
- ✅ Audio feedback verification
- ✅ Sales calculation accuracy
- ✅ Inventory management workflows

## 📄 License

This project is proprietary software. All rights reserved. This code is made publicly available solely for portfolio demonstration purposes. See the [LICENSE](LICENSE) file for full terms and restrictions.

---

<div align="center">
  <p>
    <a href="#️-arvionics---aviation-electronics-management-system">Back to top</a>
  </p>
</div>
