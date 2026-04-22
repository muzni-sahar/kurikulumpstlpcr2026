[index.html](https://github.com/user-attachments/files/26962148/index.html)
<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Peta Hubungan PEO – Profil Lulusan – CPL</title>
<style>
  @import url('https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700;900&family=Source+Sans+3:wght@300;400;600&display=swap');

  :root {
    --bg: #0c0e14;
    --surface: #13161f;
    --surface2: #181c28;
    --border: #1f2535;
    --peo1: #f0a030;
    --peo2: #28c4a0;
    --peo3: #e0456e;
    --prof1: #4f8ef7;
    --prof2: #a76bf0;
    --text: #cdd3e8;
    --muted: #5e6880;
    --white: #eef0f8;
  }

  * { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'Source Sans 3', sans-serif;
    font-weight: 300;
    min-height: 100vh;
    padding: 48px 28px 80px;
  }

  /* ── HEADER ── */
  header { text-align: center; margin-bottom: 52px; }
  .sup-label {
    font-size: 10px; letter-spacing: 5px; text-transform: uppercase;
    color: var(--muted); margin-bottom: 14px;
  }
  header h1 {
    font-family: 'Playfair Display', serif;
    font-size: clamp(26px, 5vw, 46px);
    font-weight: 900; color: var(--white); line-height: 1.1;
  }
  header h1 em { color: var(--peo1); font-style: normal; }
  header p {
    margin-top: 14px; color: var(--muted); font-size: 13.5px;
    max-width: 600px; margin-inline: auto; line-height: 1.7;
  }

  /* ── LEGEND ── */
  .legend {
    display: flex; flex-wrap: wrap; gap: 10px 20px;
    justify-content: center; margin-bottom: 48px;
  }
  .legend-item { display: flex; align-items: center; gap: 7px; font-size: 11.5px; color: var(--muted); }
  .leg-dot { width: 9px; height: 9px; border-radius: 50%; flex-shrink: 0; }

  /* ── SECTION TITLE ── */
  .section-title {
    font-family: 'Playfair Display', serif;
    font-size: 20px; font-weight: 700; color: var(--white);
    margin-bottom: 24px; padding-bottom: 10px;
    border-bottom: 1px solid var(--border);
  }

  /* ════════════════════════════════════════════
     MATRIX
  ════════════════════════════════════════════ */
  .matrix-wrap {
    overflow-x: auto; border-radius: 14px;
    border: 1px solid var(--border); margin-bottom: 64px;
    box-shadow: 0 4px 60px rgba(0,0,0,0.5);
  }

  table { width: 100%; border-collapse: collapse; min-width: 860px; font-size: 12.5px; }

  thead th {
    padding: 16px 12px; text-align: center;
    font-weight: 600; font-size: 11px; letter-spacing: 1px; text-transform: uppercase;
    background: var(--surface2); border-bottom: 1px solid var(--border);
    position: sticky; top: 0; z-index: 2;
  }
  thead th.th-label { text-align: left; min-width: 220px; color: var(--muted); }
  .th-peo1 { color: var(--peo1); }
  .th-peo2 { color: var(--peo2); }
  .th-peo3 { color: var(--peo3); }
  .th-p1   { color: var(--prof1); }
  .th-p2   { color: var(--prof2); }

  tbody tr { border-bottom: 1px solid var(--border); transition: background 0.15s; }
  tbody tr:last-child { border-bottom: none; }
  tbody tr:hover { background: rgba(255,255,255,0.025); }

  td {
    padding: 13px 10px; vertical-align: middle;
    border-right: 1px solid var(--border); text-align: center;
  }
  td:last-child { border-right: none; }

  td.cpl-label {
    text-align: left; font-weight: 600; font-size: 12.5px;
    color: var(--white); background: rgba(255,255,255,0.015);
    min-width: 220px; padding: 14px 16px;
  }
  td.cpl-label .cpl-num {
    font-size: 9.5px; letter-spacing: 2.5px; text-transform: uppercase;
    color: var(--muted); margin-bottom: 4px; display: block;
  }
  td.cpl-label .cpl-short {
    font-size: 11.5px; color: var(--muted); font-weight: 300; margin-top: 3px; line-height: 1.4;
  }

  /* ── MARKS ── */
  .mark {
    display: inline-flex; align-items: center; justify-content: center;
    width: 30px; height: 30px; border-radius: 50%;
    font-size: 15px; font-weight: 700; cursor: default;
    transition: transform 0.18s, box-shadow 0.18s;
  }
  .mark:hover { transform: scale(1.35); }

  .m-s  { box-shadow: 0 0 10px 2px currentColor; }
  .m-w  { opacity: 0.38; }
  .m-no { opacity: 0; pointer-events: none; }

  .m-peo1 { background: var(--peo1); color: #0c0e14; }
  .m-peo2 { background: var(--peo2); color: #0c0e14; }
  .m-peo3 { background: var(--peo3); color: #fff; }
  .m-p1   { background: var(--prof1); color: #fff; }
  .m-p2   { background: var(--prof2); color: #fff; }

  .m-peo1-w { background: rgba(240,160,48,0.18); color: var(--peo1); }
  .m-peo2-w { background: rgba(40,196,160,0.18); color: var(--peo2); }
  .m-peo3-w { background: rgba(224,69,110,0.18); color: var(--peo3); }
  .m-p1-w   { background: rgba(79,142,247,0.18); color: var(--prof1); }
  .m-p2-w   { background: rgba(167,107,240,0.18); color: var(--prof2); }

  /* ════════════════════════════════════════════
     SUMMARY CARDS
  ════════════════════════════════════════════ */
  .cards-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(290px, 1fr));
    gap: 18px; margin-bottom: 64px;
  }

  .card {
    background: var(--surface); border: 1px solid var(--border);
    border-radius: 14px; padding: 22px 20px;
    position: relative; overflow: hidden;
    transition: transform 0.2s, box-shadow 0.2s;
  }
  .card:hover { transform: translateY(-3px); box-shadow: 0 14px 40px rgba(0,0,0,0.4); }

  .card::before {
    content: ''; position: absolute; top: 0; left: 0; right: 0; height: 3px;
  }
  .card.c-peo1::before { background: var(--peo1); }
  .card.c-peo2::before { background: var(--peo2); }
  .card.c-peo3::before { background: var(--peo3); }
  .card.c-p1::before   { background: var(--prof1); }
  .card.c-p2::before   { background: var(--prof2); }

  .card-badge {
    display: inline-block; font-size: 9.5px; font-weight: 600;
    letter-spacing: 2px; text-transform: uppercase;
    padding: 3px 10px; border-radius: 20px; margin-bottom: 10px;
  }
  .b-peo1 { background: rgba(240,160,48,0.12); color: var(--peo1); }
  .b-peo2 { background: rgba(40,196,160,0.12); color: var(--peo2); }
  .b-peo3 { background: rgba(224,69,110,0.12); color: var(--peo3); }
  .b-p1   { background: rgba(79,142,247,0.12); color: var(--prof1); }
  .b-p2   { background: rgba(167,107,240,0.12); color: var(--prof2); }

  .card h3 { font-size: 13.5px; font-weight: 600; color: var(--white); margin-bottom: 9px; line-height: 1.4; }
  .card p  { font-size: 12px; color: var(--muted); line-height: 1.65; }

  .chips { margin-top: 14px; display: flex; flex-wrap: wrap; gap: 5px; }
  .chip {
    font-size: 9.5px; font-weight: 600; letter-spacing: 1px;
    padding: 3px 8px; border-radius: 4px; border: 1px solid;
  }
  .ch-peo1 { color: var(--peo1); border-color: rgba(240,160,48,0.3); }
  .ch-peo2 { color: var(--peo2); border-color: rgba(40,196,160,0.3); }
  .ch-peo3 { color: var(--peo3); border-color: rgba(224,69,110,0.3); }
  .ch-p1   { color: var(--prof1); border-color: rgba(79,142,247,0.3); }
  .ch-p2   { color: var(--prof2); border-color: rgba(167,107,240,0.3); }

  /* ════════════════════════════════════════════
     CPL DOMAIN GROUPING
  ════════════════════════════════════════════ */
  .domain-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
    gap: 16px; margin-bottom: 64px;
  }
  .domain-box {
    background: var(--surface); border: 1px solid var(--border);
    border-radius: 12px; padding: 18px 16px;
  }
  .domain-title {
    font-size: 10px; font-weight: 600; letter-spacing: 2.5px;
    text-transform: uppercase; margin-bottom: 12px; padding-bottom: 8px;
    border-bottom: 1px solid var(--border);
  }
  .domain-cpl {
    display: flex; align-items: flex-start; gap: 10px; margin-bottom: 9px;
  }
  .domain-cpl:last-child { margin-bottom: 0; }
  .cpl-tag {
    font-size: 9.5px; font-weight: 700; letter-spacing: 1px; padding: 3px 6px;
    border-radius: 4px; white-space: nowrap; flex-shrink: 0; margin-top: 1px;
  }
  .cpl-desc { font-size: 11.5px; color: var(--muted); line-height: 1.5; }

  .dt-sikap   { color: var(--peo2); border-bottom-color: rgba(40,196,160,0.3); }
  .cpl-tag-s  { background: rgba(40,196,160,0.15); color: var(--peo2); }
  .dt-penget  { color: var(--peo1); border-bottom-color: rgba(240,160,48,0.3); }
  .cpl-tag-p  { background: rgba(240,160,48,0.15); color: var(--peo1); }
  .dt-keter   { color: var(--peo3); border-bottom-color: rgba(224,69,110,0.3); }
  .cpl-tag-k  { background: rgba(224,69,110,0.15); color: var(--peo3); }
  .dt-prof    { color: #7ec8f0; border-bottom-color: rgba(126,200,240,0.3); }
  .cpl-tag-pr { background: rgba(126,200,240,0.12); color: #7ec8f0; }

  /* ── TOOLTIP ── */
  [data-tip] { position: relative; cursor: help; }
  [data-tip]:hover::after {
    content: attr(data-tip);
    position: absolute; bottom: calc(100% + 8px); left: 50%; transform: translateX(-50%);
    background: #1a2030; border: 1px solid var(--border); border-radius: 8px;
    padding: 10px 13px; font-size: 11.5px; color: var(--text); width: 250px;
    line-height: 1.55; z-index: 200; pointer-events: none; white-space: normal;
    box-shadow: 0 8px 32px rgba(0,0,0,0.55);
  }

  footer {
    text-align: center; color: var(--muted); font-size: 11px;
    letter-spacing: 1px; margin-top: 32px;
  }
</style>
</head>
<body>

<header>
  <div class="sup-label">Program Studi Teknik Ketenagalistrikan</div>
  <h1>Peta Hubungan <em>PEO</em> –<br>Profil Lulusan – CPL</h1>
  <p>Visualisasi keterkaitan antara 3 Program Educational Objectives, 2 Profil Lulusan, dan 10 Capaian Pembelajaran Lulusan secara komprehensif dan sistematis.</p>
</header>

<!-- LEGEND -->
<div class="legend">
  <div class="legend-item"><div class="leg-dot" style="background:var(--peo1)"></div> PEO 1 – Kompetensi Teknik</div>
  <div class="legend-item"><div class="leg-dot" style="background:var(--peo2)"></div> PEO 2 – Karakter &amp; Etika</div>
  <div class="legend-item"><div class="leg-dot" style="background:var(--peo3)"></div> PEO 3 – Daya Saing Global</div>
  <div class="legend-item"><div class="leg-dot" style="background:var(--prof1)"></div> Profil 1 – Designer &amp; Ops</div>
  <div class="legend-item"><div class="leg-dot" style="background:var(--prof2)"></div> Profil 2 – Install &amp; Maint</div>
  <div class="legend-item">
    <span style="width:18px;height:14px;border-radius:3px;background:var(--peo1);display:inline-flex;align-items:center;justify-content:center;font-size:11px;font-weight:700;color:#0c0e14;box-shadow:0 0 6px var(--peo1)">●</span>&nbsp;Kuat &nbsp;|&nbsp;
    <span style="width:18px;height:14px;border-radius:3px;background:rgba(240,160,48,0.18);display:inline-flex;align-items:center;justify-content:center;font-size:11px;font-weight:700;color:var(--peo1)">○</span>&nbsp;Parsial
  </div>
</div>

<!-- ══════════════════════════════════════════════════
     SECTION 1 — MATRIX
═══════════════════════════════════════════════════ -->
<div class="section-title">① Matriks Hubungan CPL × PEO &amp; Profil Lulusan</div>
<div class="matrix-wrap">
<table>
  <thead>
    <tr>
      <th class="th-label">Capaian Pembelajaran Lulusan</th>
      <th class="th-peo1">PEO 1<br><span style="font-weight:300;font-size:10px">Kompetensi Teknik</span></th>
      <th class="th-peo2">PEO 2<br><span style="font-weight:300;font-size:10px">Karakter &amp; Etika</span></th>
      <th class="th-peo3">PEO 3<br><span style="font-weight:300;font-size:10px">Daya Saing Global</span></th>
      <th class="th-p1">Profil 1<br><span style="font-weight:300;font-size:10px">Designer &amp; Ops</span></th>
      <th class="th-p2">Profil 2<br><span style="font-weight:300;font-size:10px">Install &amp; Maint</span></th>
    </tr>
  </thead>
  <tbody>

    <!-- CPL 1 -->
    <tr>
      <td class="cpl-label"><span class="cpl-num">CPL 1</span>Sikap &amp; Nilai Kebangsaan<div class="cpl-short">Pancasila, etika, tanggung jawab, kemandirian</div></td>
      <td data-tip="Landasan karakter profesional seorang engineer yang bertanggung jawab.">
        <span class="mark m-s m-peo1-w m-w">○</span></td>
      <td data-tip="CPL 1 inti PEO 2: nilai Pancasila, etika akademik & profesi, tanggung jawab.">
        <span class="mark m-s m-peo2">●</span></td>
      <td data-tip="Integritas dari CPL 1 menjadi syarat bersaing di level global.">
        <span class="mark m-w m-peo3-w">○</span></td>
      <td data-tip="Profil 1 mensyaratkan integritas, etika, dan profesionalisme dari CPL 1.">
        <span class="mark m-s m-p1">●</span></td>
      <td data-tip="Profil 2 mensyaratkan karakter unggul yang berakar dari CPL 1.">
        <span class="mark m-s m-p2">●</span></td>
    </tr>

    <!-- CPL 2 -->
    <tr>
      <td class="cpl-label"><span class="cpl-num">CPL 2</span>Nilai IDEAL &amp; Berpikir Kritis<div class="cpl-short">Integrity, Dignity, Excellence, Agility, Loyalty</div></td>
      <td data-tip="Excellence & Agility dalam CPL 2 mendukung inovasi teknis di PEO 1.">
        <span class="mark m-w m-peo1-w">○</span></td>
      <td data-tip="CPL 2 secara langsung mendukung PEO 2 melalui nilai IDEAL dan anti korupsi.">
        <span class="mark m-s m-peo2">●</span></td>
      <td data-tip="Agility & Excellence mendukung kemampuan adaptasi teknologi dan daya saing global (PEO 3).">
        <span class="mark m-s m-peo3">●</span></td>
      <td data-tip="Profil 1 memerlukan inovasi & kepemimpinan yang dilandasi nilai IDEAL dari CPL 2.">
        <span class="mark m-s m-p1">●</span></td>
      <td data-tip="Profil 2 memerlukan karakter inovatif & adaptif dari CPL 2.">
        <span class="mark m-s m-p2">●</span></td>
    </tr>

    <!-- CPL 3 -->
    <tr>
      <td class="cpl-label"><span class="cpl-num">CPL 3</span>Komunikasi Efektif &amp; Tim<div class="cpl-short">Tertulis, lisan, grafis; multidisiplin</div></td>
      <td data-tip="Komunikasi dibutuhkan untuk menyampaikan solusi teknis kepada pemangku kepentingan.">
        <span class="mark m-w m-peo1-w">○</span></td>
      <td data-tip="CPL 3 inti PEO 2: komunikasi efektif dan kerja sama tim.">
        <span class="mark m-s m-peo2">●</span></td>
      <td data-tip="Komunikasi lintas budaya dan bahasa penting untuk bersaing di level global.">
        <span class="mark m-s m-peo3">●</span></td>
      <td data-tip="Profil 1 mensyaratkan komunikasi efektif untuk kepemimpinan dan koordinasi.">
        <span class="mark m-s m-p1">●</span></td>
      <td data-tip="Profil 2 memerlukan komunikasi lintas tim dalam operasi lapangan.">
        <span class="mark m-w m-p2-w">○</span></td>
    </tr>

    <!-- CPL 4 -->
    <tr>
      <td class="cpl-label"><span class="cpl-num">CPL 4</span>Perancangan Sistem &amp; Berkelanjutan<div class="cpl-short">K3, lingkungan, pembangunan berkelanjutan</div></td>
      <td data-tip="CPL 4 inti PEO 1: perancangan sistem sesuai standar K3 dan prinsip berkelanjutan.">
        <span class="mark m-s m-peo1">●</span></td>
      <td data-tip="Aspek K3 dan tanggung jawab lingkungan beririsan dengan profesionalisme PEO 2.">
        <span class="mark m-w m-peo2-w">○</span></td>
      <td data-tip="Perancangan sistem berkelanjutan mendukung daya saing dan reputasi global (PEO 3).">
        <span class="mark m-s m-peo3">●</span></td>
      <td data-tip="Profil 1 secara langsung membutuhkan kompetensi perancangan sistem dari CPL 4.">
        <span class="mark m-s m-p1">●</span></td>
      <td data-tip="Profil 2 memerlukan pemahaman K3 dan keberlanjutan dalam instalasi & pemeliharaan.">
        <span class="mark m-w m-p2-w">○</span></td>
    </tr>

    <!-- CPL 5 -->
    <tr>
      <td class="cpl-label"><span class="cpl-num">CPL 5</span>Ilmu Dasar &amp; Rekayasa Terapan<div class="cpl-short">Matematika, IPA, komputasi, rekayasa</div></td>
      <td data-tip="CPL 5 fondasi ilmu dasar yang mendukung seluruh kompetensi teknis PEO 1.">
        <span class="mark m-s m-peo1">●</span></td>
      <td><span class="mark m-no">–</span></td>
      <td data-tip="Penguasaan rekayasa terapan mendukung adopsi teknologi terkini (PEO 3).">
        <span class="mark m-w m-peo3-w">○</span></td>
      <td data-tip="Profil 1 membutuhkan fondasi rekayasa kuat dari CPL 5 untuk merancang sistem.">
        <span class="mark m-s m-p1">●</span></td>
      <td data-tip="Profil 2 membutuhkan ilmu dasar rekayasa untuk troubleshooting dan instalasi.">
        <span class="mark m-s m-p2">●</span></td>
    </tr>

    <!-- CPL 6 -->
    <tr>
      <td class="cpl-label"><span class="cpl-num">CPL 6</span>Analisis Sistem Tenaga Listrik<div class="cpl-short">Pemodelan &amp; pemecahan masalah teknis</div></td>
      <td data-tip="CPL 6 inti PEO 1: analisis, pemodelan, pemecahan permasalahan teknis terstandar.">
        <span class="mark m-s m-peo1">●</span></td>
      <td><span class="mark m-no">–</span></td>
      <td data-tip="Kemampuan analisis mendalam diperlukan untuk troubleshooting & optimalisasi (PEO 3).">
        <span class="mark m-s m-peo3">●</span></td>
      <td data-tip="Profil 1 membutuhkan analisis dan optimalisasi kinerja sistem dari CPL 6.">
        <span class="mark m-s m-p1">●</span></td>
      <td data-tip="Profil 2 membutuhkan analisis untuk troubleshooting di lapangan.">
        <span class="mark m-s m-p2">●</span></td>
    </tr>

    <!-- CPL 7 -->
    <tr>
      <td class="cpl-label"><span class="cpl-num">CPL 7</span>Rancang, Instalasi, Proteksi, Otomasi, Operasi<div class="cpl-short">Komprehensif, inovatif, aman, berdaya saing</div></td>
      <td data-tip="CPL 7 puncak kompetensi teknis PEO 1: rancang, instalasi, proteksi, otomasi, operasi.">
        <span class="mark m-s m-peo1">●</span></td>
      <td data-tip="Aspek keselamatan kerja dalam CPL 7 beririsan dengan profesionalisme PEO 2.">
        <span class="mark m-w m-peo2-w">○</span></td>
      <td data-tip="CPL 7 inti PEO 3: solusi inovatif berdaya saing nasional-global.">
        <span class="mark m-s m-peo3">●</span></td>
      <td data-tip="Profil 1 secara penuh mengandalkan seluruh kompetensi teknis CPL 7.">
        <span class="mark m-s m-p1">●</span></td>
      <td data-tip="Profil 2 mengandalkan kompetensi instalasi, otomasi, dan operasi dari CPL 7.">
        <span class="mark m-s m-p2">●</span></td>
    </tr>

    <!-- CPL 8 -->
    <tr>
      <td class="cpl-label"><span class="cpl-num">CPL 8</span>Troubleshooting, Pemeliharaan &amp; Optimalisasi<div class="cpl-short">Sistematis, efektif, keandalan sistem</div></td>
      <td data-tip="CPL 8 mendukung PEO 1 dalam aspek pemeliharaan dan optimalisasi sistem.">
        <span class="mark m-s m-peo1">●</span></td>
      <td data-tip="Tanggung jawab profesional dalam pemeliharaan beririsan dengan etika PEO 2.">
        <span class="mark m-w m-peo2-w">○</span></td>
      <td data-tip="CPL 8 inti PEO 3: troubleshooting & pemeliharaan sistem di industri secara kompetitif.">
        <span class="mark m-s m-peo3">●</span></td>
      <td data-tip="Profil 1 memerlukan kemampuan diagnosis dan optimalisasi kinerja dari CPL 8.">
        <span class="mark m-s m-p1">●</span></td>
      <td data-tip="CPL 8 inti Profil 2: troubleshooting dan pemeliharaan di lapangan industri.">
        <span class="mark m-s m-p2">●</span></td>
    </tr>

    <!-- CPL 9 -->
    <tr>
      <td class="cpl-label"><span class="cpl-num">CPL 9</span>Adopsi &amp; Implementasi Teknologi Terkini<div class="cpl-short">Evaluasi kelayakan, integrasi inovasi</div></td>
      <td data-tip="CPL 9 mendukung PEO 1 melalui implementasi teknologi terkini dalam sistem.">
        <span class="mark m-s m-peo1">●</span></td>
      <td data-tip="Inovasi dalam CPL 9 selaras dengan semangat inovatif dan adaptif di PEO 2.">
        <span class="mark m-w m-peo2-w">○</span></td>
      <td data-tip="CPL 9 inti PEO 3: adopsi & implementasi teknologi terkini untuk daya saing global.">
        <span class="mark m-s m-peo3">●</span></td>
      <td data-tip="Profil 1 memerlukan kemampuan integrasi teknologi inovatif dari CPL 9.">
        <span class="mark m-s m-p1">●</span></td>
      <td data-tip="Profil 2 memerlukan kemampuan implementasi teknologi terkini di lapangan dari CPL 9.">
        <span class="mark m-s m-p2">●</span></td>
    </tr>

    <!-- CPL 10 -->
    <tr>
      <td class="cpl-label"><span class="cpl-num">CPL 10</span>Profesionalisme &amp; Kepemimpinan Engineer<div class="cpl-short">Integritas, inovasi, kolaborasi, dampak nyata</div></td>
      <td data-tip="Kepemimpinan teknis dan inovasi dalam CPL 10 mendukung solusi rekayasa PEO 1.">
        <span class="mark m-w m-peo1-w">○</span></td>
      <td data-tip="CPL 10 inti PEO 2: integritas, tanggung jawab profesional, kepemimpinan, kerja tim.">
        <span class="mark m-s m-peo2">●</span></td>
      <td data-tip="Orientasi dampak nyata dan inovasi berkelanjutan dalam CPL 10 mendukung PEO 3.">
        <span class="mark m-s m-peo3">●</span></td>
      <td data-tip="Profil 1 mensyaratkan kepemimpinan efektif dan inovasi teknis dari CPL 10.">
        <span class="mark m-s m-p1">●</span></td>
      <td data-tip="Profil 2 memerlukan profesionalisme dan tanggung jawab dari CPL 10.">
        <span class="mark m-s m-p2">●</span></td>
    </tr>

  </tbody>
</table>
</div>

<!-- ══════════════════════════════════════════════════
     SECTION 2 — DOMAIN GROUPING
═══════════════════════════════════════════════════ -->
<div class="section-title">② Pengelompokan CPL berdasarkan Domain</div>
<div class="domain-grid">

  <div class="domain-box">
    <div class="domain-title dt-sikap">Domain Sikap &amp; Tata Nilai</div>
    <div class="domain-cpl"><span class="cpl-tag cpl-tag-s">CPL 1</span><div class="cpl-desc">Ketakwaan, Pancasila, etika, tanggung jawab, kewirausahaan</div></div>
    <div class="domain-cpl"><span class="cpl-tag cpl-tag-s">CPL 2</span><div class="cpl-desc">Nilai IDEAL, anti korupsi, budaya Melayu, berpikir kritis</div></div>
  </div>

  <div class="domain-box">
    <div class="domain-title dt-sikap" style="color:#5bc4e0;border-bottom-color:rgba(91,196,224,0.3)">Domain Keterampilan Umum</div>
    <div class="domain-cpl"><span class="cpl-tag" style="background:rgba(91,196,224,0.12);color:#5bc4e0">CPL 3</span><div class="cpl-desc">Komunikasi efektif, kerja tim, multidisiplin, inklusif</div></div>
    <div class="domain-cpl"><span class="cpl-tag" style="background:rgba(91,196,224,0.12);color:#5bc4e0">CPL 10</span><div class="cpl-desc">Profesionalisme, kepemimpinan, kolaborasi, inovasi berkelanjutan</div></div>
  </div>

  <div class="domain-box">
    <div class="domain-title dt-penget">Domain Pengetahuan Rekayasa</div>
    <div class="domain-cpl"><span class="cpl-tag cpl-tag-p">CPL 4</span><div class="cpl-desc">Perancangan sistem, K3, pembangunan berkelanjutan</div></div>
    <div class="domain-cpl"><span class="cpl-tag cpl-tag-p">CPL 5</span><div class="cpl-desc">Matematika, IPA, komputasi, dasar rekayasa terapan</div></div>
    <div class="domain-cpl"><span class="cpl-tag cpl-tag-p">CPL 6</span><div class="cpl-desc">Analisis, pemodelan, pemecahan masalah teknis sistem</div></div>
  </div>

  <div class="domain-box">
    <div class="domain-title dt-keter">Domain Keterampilan Khusus</div>
    <div class="domain-cpl"><span class="cpl-tag cpl-tag-k">CPL 7</span><div class="cpl-desc">Rancang, instalasi, proteksi, otomasi, operasi sistem</div></div>
    <div class="domain-cpl"><span class="cpl-tag cpl-tag-k">CPL 8</span><div class="cpl-desc">Troubleshooting, pemeliharaan, optimalisasi di industri</div></div>
    <div class="domain-cpl"><span class="cpl-tag cpl-tag-k">CPL 9</span><div class="cpl-desc">Adopsi, evaluasi, implementasi teknologi terkini</div></div>
  </div>

</div>

<!-- ══════════════════════════════════════════════════
     SECTION 3 — NARASI KETERKAITAN
═══════════════════════════════════════════════════ -->
<div class="section-title">③ Narasi Keterkaitan PEO &amp; Profil Lulusan</div>
<div class="cards-grid">

  <div class="card c-peo1">
    <div class="card-badge b-peo1">PEO 1</div>
    <h3>Kompetensi Teknik Ketenagalistrikan</h3>
    <p>Didukung terutama oleh <strong>CPL 4, 5, 6, 7, 8, dan 9</strong>. CPL 5 &amp; 6 membangun fondasi analitis, CPL 4 &amp; 7 mengembangkan kemampuan perancangan dan operasi komprehensif, sementara CPL 8 &amp; 9 memastikan kompetensi pemeliharaan dan adopsi teknologi terkini.</p>
    <div class="chips">
      <span class="chip ch-p1">Profil 1</span>
      <span class="chip ch-p2">Profil 2</span>
    </div>
  </div>

  <div class="card c-peo2">
    <div class="card-badge b-peo2">PEO 2</div>
    <h3>Karakter, Etika &amp; Kepemimpinan</h3>
    <p>Didukung langsung oleh <strong>CPL 1, 2, 3, dan 10</strong>. CPL 1 membangun fondasi etika dan Pancasila, CPL 2 menginternalisasi nilai IDEAL, CPL 3 mengembangkan komunikasi &amp; tim, sedangkan CPL 10 membentuk jiwa kepemimpinan profesional yang bertanggung jawab.</p>
    <div class="chips">
      <span class="chip ch-p1">Profil 1</span>
      <span class="chip ch-p2">Profil 2</span>
    </div>
  </div>

  <div class="card c-peo3">
    <div class="card-badge b-peo3">PEO 3</div>
    <h3>Daya Saing Nasional &amp; Global</h3>
    <p>Merupakan sintesis dari <strong>CPL 2, 3, 4, 6, 7, 8, 9, dan 10</strong>. Daya saing global dibangun melalui kemampuan troubleshooting &amp; optimalisasi (CPL 8), adopsi teknologi terkini (CPL 9), solusi inovatif berdaya saing (CPL 7), serta komunikasi dan kepemimpinan lintas budaya (CPL 3 &amp; 10).</p>
    <div class="chips">
      <span class="chip ch-p1">Profil 1</span>
      <span class="chip ch-p2">Profil 2</span>
    </div>
  </div>

  <div class="card c-p1">
    <div class="card-badge b-p1">Profil Lulusan 1</div>
    <h3>Electrical Systems Designer &amp; Operational Engineer</h3>
    <p>Manifestasi dari <strong>PEO 1 + 2 + 3</strong> secara penuh. Profil ini memerlukan hampir seluruh CPL, dengan penekanan pada <strong>CPL 4, 5, 6, 7, 9</strong> untuk kompetensi perancangan, analisis, dan inovasi, serta <strong>CPL 1, 2, 3, 10</strong> untuk integritas, kepemimpinan, dan komunikasi yang berdaya saing global.</p>
    <div class="chips">
      <span class="chip ch-peo1">PEO 1</span>
      <span class="chip ch-peo2">PEO 2</span>
      <span class="chip ch-peo3">PEO 3</span>
    </div>
  </div>

  <div class="card c-p2">
    <div class="card-badge b-p2">Profil Lulusan 2</div>
    <h3>Electrical Installation, Automation &amp; Maintenance Engineer</h3>
    <p>Manifestasi dari <strong>PEO 1 + 3</strong> dengan kontribusi signifikan PEO 2. Profil ini bertumpu pada <strong>CPL 5, 6, 7, 8, 9</strong> untuk instalasi, otomasi, troubleshooting, dan pemeliharaan di lapangan, serta <strong>CPL 1, 2, 10</strong> untuk karakter unggul, inovatif, dan adaptif yang dibutuhkan industri.</p>
    <div class="chips">
      <span class="chip ch-peo1">PEO 1</span>
      <span class="chip ch-peo2">PEO 2</span>
      <span class="chip ch-peo3">PEO 3</span>
    </div>
  </div>

</div>

<footer>
  Program Studi Teknik Ketenagalistrikan &nbsp;|&nbsp; Dokumen Peta Kurikulum &nbsp;|&nbsp; Hover pada sel matriks untuk keterangan detail
</footer>

</body>
</html>
