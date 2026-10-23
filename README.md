# Pendaftaran B16 2026

Web pendaftaran pasukan negeri untuk Kejohanan Bola Tampar Remaja B16 Malaysia 2026 (14–18 November 2026, Kota Kinabalu, Sabah).

- Satu borang mengisi **O-2** (pendaftaran, sehingga 20 pemain) dan **O-2Bis** (pasukan akhir, 14 pemain, posisi dan kapten).
- Data disimpan dalam Supabase. Setiap negeri log masuk dengan PIN sendiri dan hanya boleh membuka pasukan negerinya. PIN admin membuka semua pasukan dan muat turun ZIP.
- Perubahan disimpan automatik ke pelayan, dan salinan disimpan dalam pelayar supaya tidak hilang jika halaman di-refresh sebelum sempat disimpan.
- Muat turun Excel menggunakan templat asal O-2 dan O-2Bis (`templates/O-2_O-2Bis.xlsx`).

Fail:
- `index.html` laman web
- `flags/` bendera negeri (ISO 3166-2:MY)
- `templates/` templat Excel gabungan O-2 + O-2Bis

PIN tidak disimpan dalam repo ini.
