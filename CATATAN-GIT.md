# Catatan Git

## Analogi
- Git = save point di game
- GitHub = salinan save point di internet
- Siklus harian: ubah -> diff -> add -> commit -> push

## Setup (sekali saja)
```
git config --global user.name "Nama Kamu"
git config --global user.email "email@contoh.com"
```

## Mulai
| Perintah | Fungsi |
|---|---|
| `git init` | Jadikan folder ini repo Git |
| `git clone <url>` | Unduh repo dari GitHub |

## Siklus harian
| Perintah | Fungsi |
|---|---|
| `git status` | Lihat kondisi file (untracked, modified, dll) |
| `git diff` | Lihat isi perubahan sebelum di-add |
| `git add <file>` | Masukkan file ke keranjang |
| `git commit -m "pesan"` | Buat save point dari isi keranjang |
| `git push` | Kirim save point ke GitHub |
| `git log --oneline` | Lihat daftar save point |

## Branch (jalur kerja terpisah)
| Perintah | Fungsi |
|---|---|
| `git branch` | Daftar branch (tanda * = posisi sekarang) |
| `git branch -v` | Daftar branch + commit terakhirnya |
| `git switch -c <nama>` | Buat branch baru dan pindah ke sana |
| `git switch <nama>` | Pindah branch |
| `git merge <nama>` | Gabungkan branch itu ke branch sekarang |
| `git branch -d <nama>` | Hapus branch yang sudah digabung |

## Remote (GitHub)
```
git remote add origin <url>
git branch -M main
git push -u origin main
```
- `origin` = nama panggilan untuk alamat GitHub
- `-u` cukup sekali; setelah itu `git push` saja

## .gitignore
Daftar file yang tidak ikut Git. Isi minimal:
```
.env
node_modules/
```
- `.env` = rahasia (password, API key), JANGAN naik ke GitHub
- `.gitignore` sendiri harus di-commit

## Status file
- `Untracked` = file baru, belum diawasi Git
- `new file` = sudah di keranjang, file baru
- `modified` = file lama yang diubah
- `working tree clean` = semua sudah tersimpan

## Kesalahan yang pernah kualami
- Lupa `cd` ke folder repo -> perintah Git error
- `git commit` saat keranjang kosong -> "nothing to commit"
- Pesan commit tidak sesuai isi perubahan