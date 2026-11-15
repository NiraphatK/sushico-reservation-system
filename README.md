<h1 align="center">🍣 Sushico Queue Reservation System</h1>
<p align="center">
  Same-day reservation system for a sushi restaurant.  
  Built with <b>Laravel 12 (Blade)</b>, <b>PHP</b> & <b>Bootstrap</b>.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/PHP-8.2+-777BB4?logo=php"/>
  <img src="https://img.shields.io/badge/Laravel-12-FF2D20?logo=laravel"/>
  <img src="https://img.shields.io/badge/Blade-Template-orange"/>
  <img src="https://img.shields.io/badge/Bootstrap-5-7952B3?logo=bootstrap"/>
  <img src="https://img.shields.io/badge/MySQL-Database-4479A1?logo=mysql"/>
</p>

---

## ✨ Overview
**Sushico Queue Reservation System** supports **same-day reservations** via web application.  
Customers can sign in with **email or phone number**, select **time, party size, and seat type (BAR or TABLE)**.  

The system confirms reservations only if active bookings do not exceed available seats.  
Table numbers are **not assigned at booking time** — instead, staff assign them during **check-in** to optimize usage and reduce no-shows.  

In addition, the system provides a **Menu Page** where customers can view food items (name, price, and image).  
Admins can upload and manage menu items alongside store policies like **Cut-off Time, Grace Period, Store Hours, and Table Settings**.  

---

## ✨ Features
### 👤 Customer
- Register & log in with email or phone  
- Book, cancel, or edit reservations before cut-off time  
- Choose time, party size, and seat type (BAR / TABLE)  
- Check booking status and confirm arrival (check-in)  
- Browse restaurant menu items (name, price, image)

### 🧑‍🍳 Staff
- View daily reservations overview  
- Check in customers and assign actual tables  
- Update reservation status (Confirmed → Seated → Completed / No Show / Cancelled)  
- Assist customers in editing or cancelling after cut-off  

### 🔧 Admin
- Manage table information (add/edit/remove/enable/disable)  
- Configure cut-off, grace period, buffer, store hours, and slot granularity  
- View daily statistics, no-show rate, and peak hours reports  
- Add, edit, delete, or hide menu items
- Upload menu item images for display on the customer-facing menu page

---


## 🛠 Tech Stack
- **Language** → [PHP 8.2+](https://www.php.net/)  
- **Framework** → [Laravel 12](https://laravel.com/)  
- **View Engine** → [Blade Templates](https://laravel.com/docs/12.x/blade)  
- **Frontend** → [Bootstrap 5](https://getbootstrap.com/)  
- **Database** → [MySQL](https://www.mysql.com/)
---

## Getting started

### Requirements

- PHP 8.2+, Composer 2+, and MySQL.
- Node.js/npm if rebuilding frontend assets.
- XAMPP is an optional way to run MySQL locally; it is not required when an equivalent PHP/MySQL environment is already configured.

### Install the Laravel application

The application lives in **`Web/`**, not the repository root:

```bash
git clone https://github.com/NiraphatK/sushico-reservation-system.git
cd sushico-reservation-system/Web
composer install
cp .env.example .env
php artisan key:generate
```

On Windows without `cp`, copy `.env.example` to `.env` in Explorer or use `Copy-Item` in PowerShell.

Create a new local MySQL database named `sushico`. Set these values in `Web/.env`, replacing the credentials with your local account:

```dotenv
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=sushico
DB_USERNAME=your_local_user
DB_PASSWORD=your_local_password
```

Import **`Web/database/127_0_0_1.sql`** into the new database using phpMyAdmin or your MySQL client. Review the SQL before importing and use a disposable development database; do not import it over an existing production database. The dump may contain historical sample accounts/data; do not treat their credentials as suitable for deployment.

From `Web/`, prepare frontend assets and start Laravel:

```bash
npm ci
npm run build
php artisan storage:link
php artisan serve
```

Open `http://localhost:8000`. To develop frontend assets interactively, run `npm run dev` in a second terminal from `Web/`.

## Verification

```bash
php artisan test
```

After configuring the database, check customer booking, staff check-in, admin menu management, and image display using test data. A successful unit test run alone does not establish that the imported database and all role-specific flows work.

---

## 📄 Documentation
> [📘 Full Project Documentation](https://github.com/NiraphatK/sushico-reservation-system/blob/main/Document/Sushico-Report.pdf)
