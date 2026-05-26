# Dokumentasi API - Lensa Cakrawala

Selamat datang di dokumentasi API resmi untuk **Lensa Cakrawala**. API ini dirancang untuk mengelola berbagai layanan drone, seperti pemetaan wilayah dan fotografi udara.

* **Base URL:** `{{baseUrl}}` (Menggunakan Environment Postman)

---

## 1. Kelola Layanan (CRUD)

### A. Menambahkan Layanan Drone Baru
Digunakan untuk memasukkan data layanan drone baru ke dalam sistem.

* **HTTP Method:** `POST`
* **URL:** `{{baseUrl}}/layanan`

#### Request Body (JSON)
| Field | Tipe Data | Wajib | Keterangan |
| :--- | :--- | :--- | :--- |
| nama_layanan | String | Ya | Nama paket layanan drone |
| harga | Number | Ya | Biaya dalam satuan Rupiah |
| durasi | String | Tidak | Estimasi waktu pengerjaan |

#### Contoh Respon (201 Created)
```json
{
  "id": 3,
  "nama_layanan": "Drone Mapping Kebun Sawit",
  "harga": 3500000,
  "durasi": "2 Hari Kerja"
}
```

### B. Menampilkan Detail Satu Layanan Drone
Digunakan untuk mengambil data lengkap dari satu layanan drone berdasarkan ID spesifik.

* **HTTP Method:** `GET`
* **URL:** `{{baseUrl}}/layanan/{id}`

#### Path Parameter(JSON)
| Parameter | Tipe Data | Wajib | Keterangan |
| :--- | :--- | :--- | :--- |
| id | Number | Ya | ID unik dari layanan drone yang ingin dicari |

#### Contoh Respon (200 OK)
```json
{
  "id": 1,
  "nama_layanan": "Pemetaan Area Perkebunan Pro",
  "harga": 6000000,
  "durasi": "3 Hari Kerja"
}
```
### C. Memperbarui Data Layanan Drone 
Digunakan untuk memperbarui data layanan drone yang sudah ada.

* **HTTP Method:** `PUT`
* **URL:** `{{baseUrl}}/layanan/{id}`

#### Path Parameter(JSON)
| Parameter | Tipe Data | Wajib | Keterangan |
| :--- | :--- | :--- | :--- |
| id | Number | Ya | ID unik layanan yang akan diperbarui |

#### Request Body (JSON)
| Field | Tipe Data | Wajib | Keterangan |
| :--- | :--- | :--- | :--- |
| nama_layanan | String | Ya | Nama paket layanan drone |
| harga | Number | Ya | Nilai tarif baru dalam satuan Rupiah yang akan menggantikan harga lama |
| durasi | String | Tidak | Estimasi waktu pengerjaan |

#### Contoh Respon (200 OK)
```json
{
  "id": 1,
  "nama_layanan": "Pemetaan Area Perkebunan Pro",
  "harga": 5500000,
  "durasi": "3 Hari Kerja"
}
```

---

### D. Menghapus Data Layanan Drone
Digunakan untuk menghapus satu layanan drone dari sistem berdasarkan ID spesifik.

* **HTTP Method:** `DELETE`
* **URL:** `{{baseUrl}}/layanan/{id}`

#### Path Parameters
| Parameter | Tipe Data | Wajib | Keterangan |
| :--- | :--- | :--- | :--- |
| id | Number | Ya | ID unik dari layanan drone yang ingin dihapus |

#### Contoh Respon (200 OK)
```json
{
  "message": "Layanan berhasil dihapus"
}
```
