RUANG KOPI KITA — APLIKASI ADMIN & STAF (PWA)

Fail utama: app.html (buka melalui GitHub Pages HTTPS, bukan double-click dari Windows).
Pelanggan: index.html kekal sebagai web QR.
Admin: admin.html ialah salinan dashboard asal yang disediakan.

CARA TERBITKAN
1. Simpan salinan repo GitHub yang sedang digunakan.
2. Upload app.html, admin.html, manifest.webmanifest, sw.js dan folder icons ke akar repo ruang-kopi-kita.
   Jangan overwrite index.html pelanggan jika versi live sudah mempunyai kemas kini baharu.
3. Selepas GitHub Pages selesai deploy, buka:
   https://m-8834019-debug.github.io/ruang-kopi-kita/app.html
4. Android: Chrome > menu > Add to Home screen / Install app.
   iPhone: Safari > Share > Add to Home Screen.
5. Login akaun Supabase yang sudah ada dalam auth.users dan user_roles.
   user_roles.role perlu 'admin' untuk admin, atau 'staff' / 'staf' untuk staf.

PENTING
- Versi ini ialah PWA, bukan APK/IPA native dan bukan aplikasi App Store.
- Sambungan Supabase menggunakan public publishable key; keselamatan bergantung pada RLS.
- Pastikan staff diberi SELECT pesanan dan UPDATE status sahaja melalui polisi RLS / RPC yang selamat.
- Pastikan admin mendapat polisi akses kewangan yang sesuai.
- Jika RLS menghalang perubahan status, aplikasi akan tunjuk ralat (tidak melonggarkan polisi automatik).
- Pesanan staf dipaparkan masa nyata apabila Realtime untuk orders diaktifkan; polling 15 saat juga disediakan.
- Senarai item makanan setiap pesanan belum dipaparkan kerana skema order_items belum disahkan.
- Versi ini belum diuji secara langsung dengan pangkalan data pengguna; buat ujian sebelum operasi kedai.
- Internet diperlukan untuk login, pesanan, dan penyegerakan.
