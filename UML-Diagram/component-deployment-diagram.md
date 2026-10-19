# Component Diagram dan Deployment Diagram

**Proyek:** Smart Parking Digital Twin Kampus  
**Teknologi prototipe:** HTML, CSS, JavaScript

## 1. Component Diagram

Component Diagram menunjukkan bagian-bagian perangkat lunak dalam sistem Smart Parking dan hubungan antarkomponen.

```mermaid
flowchart TB
    subgraph SP["Sistem Smart Parking Digital Twin"]
        UI["Antarmuka Pengguna<br/>HTML, CSS, JavaScript"]
        SIM["Modul Simulasi Kendaraan"]
        MAP["Modul Denah Parkir"]
        SLOT["Modul Pengelolaan Slot"]
        REPORT["Modul Statistik Parkir"]
        DATA[("Penyimpanan Data Parkir")]

        UI --> MAP
        UI --> SLOT
        UI --> REPORT
        SIM --> SLOT
        SLOT <--> DATA
        REPORT --> DATA
        MAP --> SLOT
    end

    M["Mahasiswa"]
    P["Petugas Parkir"]
    A["Admin Kampus"]

    M --> UI
    P --> UI
    A --> UI
```

## 2. Deployment Diagram

Deployment Diagram menunjukkan perangkat yang menjalankan aplikasi serta penempatan file dan data sistem.

```mermaid
flowchart TB
    subgraph CLIENT["Perangkat Pengguna"]
        B["Web Browser<br/>Chrome / Edge"]
    end

    subgraph HOST["Komputer atau Laptop yang Menjalankan Aplikasi"]
        APP["Aplikasi Smart Parking<br/>index.html"]
        CSS["Tampilan<br/>style.css"]
        JS["Logika Sistem<br/>script.js"]
        STORE[("Data Slot di Memori Browser")]

        APP --- CSS
        APP --- JS
        JS <--> STORE
    end

    USER["Mahasiswa / Petugas / Admin"]

    USER -->|"Interaksi pengguna"| B
    B <-->|"Memuat halaman dan menjalankan JavaScript"| APP
```

antarkomponen. Deployment Diagram menjelaskan tempat aplikasi dijalankan dan bagaimana browser, file aplikasi, serta data sementara digunakan. Kedua diagram saling melengkapi dalam dokumentasi perancangan sistem.
