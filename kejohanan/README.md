# Pendaftaran Kejohanan Bola Tampar

Sistem pendaftaran pasukan dalam talian berdasarkan **Borang O-2** MAVA, untuk banyak kejohanan sekaligus. Laman: https://hakim14-d.github.io/MAVA_B16/kejohanan/ (data dalam **Supabase**).

## Peranan & log masuk (PIN)
| Peranan | Log masuk | Boleh buat |
|---|---|---|
| **Super Admin** | PIN super admin | Cipta/padam kejohanan, tetapkan PIN urus setia setiap kejohanan, tukar PIN super admin |
| **Urus Setia Kejohanan** | Pilih kejohanan + PIN urus setia | Tetapan (tarikh, tempat, tarikh tutup, denda), terbit & kongsi, jana kod/PIN pasukan, papan pemuka, sunting borang, tanda denda dibayar, PDF |
| **Pengurus Pasukan** | Pilih kejohanan + kod pasukan + PIN | Isi Borang O-2 (Lelaki/Perempuan), gambar pasport, hantar, muat turun PDF |

Pautan terus ke kejohanan: `…/#e-<id kejohanan>` · pautan log masuk urus setia: `…/#a-<id kejohanan>`.

## Ciri
- Banyak kejohanan; draf → terbit → kongsi (pautan + mesej sedia WhatsApp)
- Tarikh & masa tutup (MYT); selepas tarikh tutup: **terima lewat dengan denda** (amaun & arahan bayaran) atau **tutup pendaftaran**
- Borang O-2: 20 pemain, posisi, kapten (C), libero (L), 6 pegawai, warna 2 uniform, semakan No. KP / tarikh lahir / kelayakan umur
- Gambar saiz pasport 35×45 mm (dipotong automatik)
- Papan pemuka: dihantar/draf, Lelaki/Perempuan, pasukan lewat & denda tertunggak
- PDF: Borang O-2 + lampiran gambar, semua borang dalam satu fail, senarai induk

## Supabase
Jadual berawalan `kj_` (`kj_events`, `kj_access`, `kj_teams`, `kj_photos`, `kj_super`, `kj_attempts`). RLS dihidupkan tanpa polisi: semua akses melalui fungsi `kj_*` (SECURITY DEFINER) yang menyemak PIN, dengan had 8 cubaan salah setiap 15 minit. PIN disimpan sebagai hash bcrypt. Kunci dalam `index.html` ialah kunci awam (anon) Supabase. Tiada PIN disimpan dalam repo ini.

© 2026 ZAINDRA
