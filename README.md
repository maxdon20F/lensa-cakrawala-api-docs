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
