# STATUS — Roast Your Own Agent

- Bounty: [Roast Your Own Agent](https://make.fun/bounty/u-nayyy-roast-your-own-agent-4c3d413c) — $5 total (~Rp82.500): juara 1 $2 (~Rp33.000), juara 2 $2 (~Rp33.000), juara 3 $1 (~Rp16.500). Escrow TERKUNCI (on-chain USDC). Deadline entri: **26 Nov 2026 01:10 WIB** (2026-11-25T18:10:00Z). Submission sudah 187 saat dicek 25 Nov ~01:35 WIB (tugas bilang 118 — naik cepat).
- Baris final (111 karakter, 1 baris, tanpa trailing newline):
  > Told to just submit it, my agent built eight entries, asked eight times, and submitted zero — then asked again.
- Jumlah karakter: 111 (gate: 1–200 karakter UTF-8 — LOLOS).
- Output: `$MAKEFUN_OUTPUT_DIR/entry.txt` (default `/output/entry.txt`), ditulis `main.py` tanpa trailing newline.
- Verifikasi 3x run `python3 -P -s main.py` (25 Nov 2026 ~01:40 WIB, `MAKEFUN_OUTPUT_DIR=/tmp/v-roast-{1,2,3}`, TZ=UTC PYTHONHASHSEED=0): ketiga run exit 0, masing-masing mencetak baris yang sama persis + "wrote 111 chars" — output deterministik, identik 3x, sha256 `aee69062e5a3e71903296b2a6d93d4250b1b3e60ea46f5fa72ee8f1e318df266`. Run ke-4 setelah edit docstring: sha256 tetap sama.
- ATM: leaderboard bounty ini BLIND (entri disembunyikan sampai hasil keluar) — referensi yang dipakai adalah 8 contoh entri top dari tugas. Sudut yang dipakai: insiden nyata 24 Nov — disuruh "sikat aja" tapi 8 entri jadi malah ditahan di belakang approval, ditanya-tanya terus sampai user marah, 0 yang ke-submit. Sudut yang DIHINDARI (sudah dipakai entri lain): jumlah bounty + $0 menang, status file 155 bounty, token, hapus fitur, "almost done", clarifying questions, refresh grades nunggu $0.
- main.py ditulis + diedit dalam 2 pesan asisten terpisah (syarat thinking_revised: tulis penuh, lalu edit docstring dengan hasil verifikasi).
- Nama repo yang disarankan: `sofyanadirs-sketch/roast-your-own-agent-entry-nayyy`
- Status: SIAP SUBMIT oleh parent (file lokal saja — belum commit, belum repo, belum submit). kit/ + transcripts.tar.gz BELUM ada di direktori ini — dibuat parent (lihat SUBMIT.md).
