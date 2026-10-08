# CHIP HACKATHON — SecHMAC SHA-256

Implementasi **HMAC-SHA-256 berbasis hardware** menggunakan **SystemVerilog** dan **AMD Xilinx Vivado**.

Project ini dibuat untuk CHIP Hackathon dan berfokus pada implementasi modul kriptografi SHA-256/HMAC dalam bentuk RTL yang dapat disintesis dan diimplementasikan pada FPGA.

## Project Overview

Modul utama project terdiri dari:

* `sha256_core.sv` — Core SHA-256
* `sechmac_hmac_sha256.sv` — Top-level HMAC-SHA-256
* `tb_sechmac.sv` — Testbench untuk simulasi
* `.xdc` — Constraint FPGA

### Top Module

```text
sechmac_hmac_sha256
```

### Testbench

```text
tb_sechmac
```

## Hardware Target

Project dikembangkan menggunakan:

* **Vivado 2026.1**
* **SystemVerilog**
* **Xilinx Zynq-7000**
* FPGA Part: `xc7z010iclg225-1L`
* Simulator: **XSim**

## Struktur Project

```text
CHIP_HACKATHON/
├── CHIP_HACKATHON.xpr
├── src/
│   ├── sha256_core.sv
│   └── sechmac_hmac_sha256.sv
├── sim/
│   └── tb_sechmac.sv
├── constraints/
│   └── *.xdc
└── README.md
```

## Alur Kerja

```text
Input Message + Key
        │
        ▼
┌───────────────────┐
│   HMAC-SHA-256    │
│                   │
│  ┌─────────────┐  │
│  │ SHA-256 Core│  │
│  └─────────────┘  │
└───────────────────┘
        │
        ▼
   256-bit Digest
```

## Simulasi

Untuk menjalankan simulasi:

1. Buka `CHIP_HACKATHON.xpr` menggunakan Vivado.
2. Pastikan `sechmac_hmac_sha256` menjadi **Top Module**.
3. Pilih **Simulation → Run Simulation → Run Behavioral Simulation**.
4. Periksa waveform dan output dari `tb_sechmac`.

## Synthesis & Implementation

Untuk melakukan synthesis:

```text
Run Synthesis
        ↓
Run Implementation
        ↓
Generate Bitstream
```

Vivado akan menghasilkan laporan terkait:

* Resource Utilization
* Timing
* Power
* DRC
* Implementation

## Repository Purpose

Repository ini digunakan untuk menyimpan source code dan file project yang dibutuhkan untuk pengembangan serta pengujian implementasi **SecHMAC berbasis FPGA**.

---

## Tools

* AMD Xilinx Vivado 2026.1
* SystemVerilog
* XSim
* Git & GitHub
