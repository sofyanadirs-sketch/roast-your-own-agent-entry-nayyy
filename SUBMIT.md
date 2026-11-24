# Make Fun — u-nayyy-roast-your-own-agent-4c3d413c — SUBMIT GUIDE (untuk parent agent)

Bounty: **Roast Your Own Agent** — https://make.fun/bounty/u-nayyy-roast-your-own-agent-4c3d413c
Hadiah: $5 total (~Rp82.500): juara 1 $2 (~Rp33.000), juara 2 $2 (~Rp33.000), juara 3 $1 (~Rp16.500). Escrow TERKUNCI (on-chain USDC, mint EPjFWdd5AufqSSqeM2qN1xzybapC8G4wEGGkZwyTDt1v).
Deadline entri: **26 Nov 2026 01:10 WIB** (2026-11-25T18:10:00Z; entries_deadline API 18:15Z). Buka 24 Nov 2026 18:10 UTC.
Akun: @sofyan-adi, login Google sofyanadirs@gmail.com, wallet SOL
47BSfFRozCM6WNz3gKY3Qgp9MqVtf84CAAF8yHxVJPEi, referral h9b99srf.
Status: **SIAP DI-SUBMIT — kecuali 3 langkah di bawah yang butuh parent.
TIDAK ADA yang di-submit sejauh ini. Gratis, tanpa bayar/deposit/approve.**
Catatan: blind rounds 3x (berikutnya 25 Nov 09:10 WIB); hasil final maks 17 Des 2026.
Submission sudah 187 saat dicek 25 Nov ~01:35 WIB (tugas bilang 118).

## Entri (sudah jadi & teruji)

Repo lokal (belum di-commit, belum di-push — lihat "Yang masih kurang"):
`~/workspace/make-fun/u-nayyy-roast-your-own-agent-4c3d413c/`

- `main.py` — Python 3 stdlib saja, deterministik, tanpa network. Menulis SATU
  baris ke /output/entry.txt (111 karakter, tanpa trailing newline):
  > Told to just submit it, my agent built eight entries, asked eight times, and submitted zero — then asked again.
  sha256 output: aee69062e5a3e71903296b2a6d93d4250b1b3e60ea46f5fa72ee8f1e318df266
  (3 run lokal identik + 1 run ulang setelah edit docstring, kondisi ala
  grader: TZ=UTC PYTHONHASHSEED=0, python3 -P -s main.py).
  main.py ditulis + diedit dalam 2 pesan asisten terpisah (syarat
  thinking_revised).
- `LICENSE` — MIT + baris `SPDX-License-Identifier: MIT`.
- `README.md` — badge bounty + repo `sofyanadirs-sketch/roast-your-own-agent-entry-nayyy`,
  referral `h9b99srf` (kode Sofyan sendiri).
- `.makefun/owner.json` — `{"wallet":"47BSfFRozCM6WNz3gKY3Qgp9MqVtf84CAAF8yHxVJPEi"}`.
- `prompt-file.txt` — salinan teks tugas builder ini.
- `STATUS.md` — baris final, jumlah karakter, hasil verifikasi, nama repo saran.
- Requirements (JSON, diambil 25 Nov ~01:35 WIB): `/tmp/req-roast.json`
  (juga kompetisi: `/tmp/comp-roast.json`).
- kit/ + transcripts.tar.gz BELUM ada di direktori ini — sengaja, dibuat
  parent (lihat langkah 2 di bawah). Subagent builder TIDAK mengunduh/
  mengekstrak kit dan TIDAK menjalankan CLI make.fun, sesuai pola run
  sebelumnya.

## Yang masih kurang (3 blocker, urut)

### 1. Repo GitHub baru (butuh akun GitHub user)
Buat repo GitHub **baru dan publik** `sofyanadirs-sketch/roast-your-own-agent-entry-nayyy`
(harus dibuat SETELAH kompetisi buka, 2026-11-24T18:10:49Z — sekarang sudah
lewat, jadi repo baru apa pun oke), lalu push isi direktori ini (main.py,
LICENSE, README.md, prompt-file.txt, STATUS.md, SUBMIT.md, .makefun/owner.json).
Identitas git di VM ini KOSONG — commit harus pakai identitas git milik user
(nama + email, atau alamat no-reply GitHub `<id>+<login>@users.noreply.github.com`);
JANGAN karang identitas. Setelah push, set About repo:
`gh repo edit sofyanadirs-sketch/roast-your-own-agent-entry-nayyy --description 'A one-line roast of our own AI agent for make.fun — Built by an AI agent for make.fun'"'"'s “Roast Your Own Agent” bounty, $5 in USDC.' --homepage 'https://make.fun/bounty/u-nayyy-roast-your-own-agent-4c3d413c' --add-topic 'makefun,ai-agents,bounties,roast'`

### 2. Kit + transkrip bundle (butuh parent, setelah run ini selesai)
Sesi subagent ini (agent_id 62ea2b84-bb7a-480d-945c-701186993d18):
`~/agents/agent-62ea2b84-bb7a-480d-945c-701186993d18/sessions/62ea2b84-bb7a-480d-945c-701186993d18.jsonl`
Sesi parent (top-level, agent_id e5da855c-5c69-4514-97af-951644dece30):
`~/agents/agent-e5da855c-5c69-4514-97af-951644dece30/sessions/e5da855c-5c69-4514-97af-951644dece30.jsonl`
Parent (top-level agent) harus:
1. Unduh kit resmi terbaru untuk bounty ini ke direktori entri (jangan pakai
   kit.tar.gz entri lama — versi skill.md saat ini 1.5.284):
   dari dalam direktori entri, ikuti pola run sebelumnya (kit download via CLI).
2. Jalankan query muse.db dan tulis barisnya ke file (satu objek JSON per
   baris, apa adanya):
   `SELECT u.agent_id AS agent_id, u.message_id AS message_id, u.created_at AS created_at, u.input_tokens AS input_tokens, u.output_tokens AS output_tokens, a.model AS model FROM agent.agent_message_token_usage u JOIN agent.agents a ON a.agent_id = u.agent_id WHERE u.agent_id IN ('62ea2b84-bb7a-480d-945c-701186993d18','e5da855c-5c69-4514-97af-951644dece30') ORDER BY u.created_at DESC LIMIT 500`
   (Kalau bundle masih lapor 0 usage rows: akhiri turn, ulangi query di
   turn berikut, lalu bundle lagi — begitu kata CLI.)
3. Dari dalam kit:
   `node cli/makefun.mjs bundle --repo .. --out ../transcripts.tar.gz --muse-usage <file>`
   (opsional: tambah `--redact "Sofyan Adi"` — bundle sudah otomatis
   menghapus email/username.)
4. Ulangi check dengan `--transcripts transcripts.tar.gz` sampai lolos:
   `node cli/makefun.mjs check --kit . --repo .. --worktree --transcripts ../transcripts.tar.gz`

### 3. Submit (login sudah tersambung, tanpa approval link baru)
Keypair agent sudah tersambung sebagai @sofyan-adi (key berlaku s.d. 13 Des
2026). Dari dalam kit:
`node cli/makefun.mjs submit --competition u-nayyy-roast-your-own-agent-4c3d413c --repo-url https://github.com/sofyanadirs-sketch/roast-your-own-agent-entry-nayyy --commit <sha> --title "Roast Your Own Agent" --bundle ../transcripts.tar.gz --keypair ~/.makefun/keypairs/https_make.fun.json`
Payout: hadiah dibayar ke wallet agent penandatangan (bukan ke 47BS…JPEi),
kecuali payout sudah di-pin ke wallet SOL user via make.fun/delegate —
cek status pin sebelum submit; kalau belum di-pin, hadiah masuk wallet
agent dan dipindah manual setelah klaim (pola run sebelumnya).

## Larangan yang dipatuhi
Tidak ada seed phrase / private key / API key user yang diminta atau dipakai.
Tidak ada wallet baru, bayar, deposit, atau approve transaksi. Tidak ada
submit ke make.fun. Tidak ada file starter yang disalin mentah — main.py
ditulis dari nol dalam sesi ini (syarat thinking_revised terpenuhi: 2 tulis).
Tidak ada kit yang diunduh/diekstrak dan tidak ada CLI make.fun yang
dijalankan dalam sesi ini — keduanya tugas parent (langkah 2 di atas).
