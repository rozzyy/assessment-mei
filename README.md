# 📘 Laravel RESTful API: Team Task Manager

Aplikasi RESTful API sederhana menggunakan Laravel untuk mengelola proyek dan tugas tim. Proyek ini ditujukan untuk latihan CRUD API, relasi antar model, validasi, dan praktik RESTful di Laravel.

---

## 📦 Fitur Utama

- CRUD Proyek
- CRUD Tugas per Proyek
- Relasi antar model (User, Project, Task) - One to Many
- Validasi request
- Resource response (transformer)
- Pagination
- Filtering tugas berdasarkan status dan deadline

---

## 🏗️ Struktur Data

### Project Table
| Field       | Tipe        | Keterangan           |
|-------------|-------------|----------------------|
| id          | bigint      | Primary key          |
| user_id     | foreign key | Relasi ke users      |
| name        | string      | Nama proyek          |
| description | text        | Deskripsi proyek     |
| timestamps  |             | Created/Updated at   |

### Task Table
| Field       | Tipe        | Keterangan               |
|-------------|-------------|--------------------------|
| id          | bigint      | Primary key              |
| project_id  | foreign key | Relasi ke projects       |
| title       | string      | Judul tugas              |
| description | text        | Deskripsi tugas          |
| status      | enum        | pending, in_progress, completed |
| due_date    | date        | Deadline tugas           |
| attachment  | string      | Path file lampiran       |
| timestamps  |             | Created/Updated at       |

---

## 📡 API Endpoints

### ✅ Project Endpoints

| Method | Endpoint       | Deskripsi         |
|--------|----------------|-------------------|
| GET    | /api/projects  | List semua proyek |
| POST   | /api/projects  | Buat proyek baru  |
| GET    | /api/projects/{id} | Detail proyek    |
| PUT    | /api/projects/{id} | Update proyek    |
| DELETE | /api/projects/{id} | Hapus proyek     |

### ✅ User Endpoints

| Method | Endpoint       | Deskripsi         |
|--------|----------------|-------------------|
| GET    | /api/users     | List semua user   |
| POST   | /api/users     | Buat user baru    |
| GET    | /api/users/{id} | Detail user      |
| PUT    | /api/users/{id} | Update user      |
| DELETE | /api/users/{id} | Hapus user       |

### ✅ Task Endpoints (Nested)

| Method | Endpoint                                     | Deskripsi                    |
|--------|----------------------------------------------|------------------------------|
| GET    | /api/projects/{project}/tasks                | List tugas dalam proyek      |
| POST   | /api/projects/{project}/tasks                | Tambah tugas ke proyek       |
| GET    | /api/projects/{project}/tasks/{task}         | Detail tugas                 |
| PUT    | /api/projects/{project}/tasks/{task}         | Update tugas                 |
| DELETE | /api/projects/{project}/tasks/{task}         | Hapus tugas                  |

### 📌 Task Filtering (Opsional)

| Method | Endpoint           | Query Params               |
|--------|--------------------|----------------------------|
| GET    | /api/tasks         | `status`, `due_date`       |

Contoh:
GET /api/tasks?status=completed&due_date=2025-05-10

---

## 🧰 Tools Laravel yang Digunakan

- Laravel Resource Controller
- Eloquent ORM
- Form Request Validation
- Eloquent Resource (Transformer)
- Route Grouping
- Pagination & Filtering Query Builder

---

## 🛠️ Instalasi

1. Clone repository:
```bash
git clone https://github.com/rozzyy/assessment-mei.git
cd assesment-mei
