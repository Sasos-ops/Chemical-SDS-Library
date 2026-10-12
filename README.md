<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Chemical SDS Library</title>
    <style>
      :root {
        --bg: #f5f7fb;
        --panel: #ffffff;
        --primary: #113b75;
        --primary-soft: #eaf1ff;
        --text: #1d2433;
        --muted: #5d697d;
        --border: #dfe7f1;
        --success: #0f7a6d;
        --warning: #b76a1f;
        --shadow: 0 10px 30px rgba(17, 59, 117, 0.08);
      }

      * { box-sizing: border-box; }

      body {
        margin: 0;
        font-family: Arial, Helvetica, sans-serif;
        background: linear-gradient(180deg, #eef4ff 0%, var(--bg) 100%);
        color: var(--text);
      }

      .wrap {
        max-width: 1200px;
        margin: 0 auto;
        padding: 40px 20px 80px;
      }

      .hero {
        background: linear-gradient(135deg, var(--primary), #234f97);
        color: white;
        border-radius: 20px;
        padding: 36px 32px;
        box-shadow: var(--shadow);
      }

      .hero h1 {
        margin: 0 0 12px;
        font-size: clamp(2rem, 3vw, 3rem);
      }

      .hero p {
        margin: 0;
        color: rgba(255,255,255,0.9);
        max-width: 780px;
        line-height: 1.6;
      }

      .search-box {
        margin-top: 30px;
        background: var(--panel);
        border: 1px solid var(--border);
        border-radius: 14px;
        padding: 16px 18px;
        display: flex;
        gap: 12px;
        align-items: center;
        box-shadow: var(--shadow);
      }

      .search-box input {
        flex: 1;
        border: none;
        outline: none;
        font-size: 1rem;
        color: var(--text);
      }

      .search-box .label {
        color: var(--muted);
        font-weight: 700;
        letter-spacing: 0.02em;
      }

      .category-grid {
        margin-top: 36px;
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
        gap: 24px;
      }

      .category {
        background: var(--panel);
        border: 1px solid var(--border);
        border-radius: 16px;
        padding: 20px;
        box-shadow: var(--shadow);
      }

      .category.hidden {
        display: none;
      }

      .category h2 {
        margin: 0 0 18px;
        font-size: 1.2rem;
        color: var(--primary);
      }

      .doc-list {
        list-style: none;
        padding: 0;
        margin: 0;
        display: flex;
        flex-direction: column;
        gap: 10px;
      }

      .doc-list li {
        border: 1px solid var(--border);
        border-radius: 10px;
        background: #fbfcff;
        transition: 0.2s ease;
      }

      .doc-list li:hover {
        background: var(--primary-soft);
        border-color: #bfd1ff;
      }

      .doc-list a {
        display: flex;
        align-items: center;
        gap: 10px;
        text-decoration: none;
        color: var(--text);
        padding: 10px 12px;
        font-size: 0.95rem;
        line-height: 1.4;
      }

      .tag {
        display: inline-flex;
        align-items: center;
        justify-content: center;
        min-width: 56px;
        padding: 5px 8px;
        border-radius: 999px;
        font-size: 0.72rem;
        font-weight: 700;
        letter-spacing: 0.03em;
        text-transform: uppercase;
      }

      .tag-sds { background: #e4f7f2; color: var(--success); }
      .tag-msds { background: #fff1dc; color: var(--warning); }
      .tag-tds { background: #eaf1ff; color: var(--primary); }

      .meta {
        margin-top: 26px;
        display: flex;
        justify-content: space-between;
        align-items: center;
        gap: 12px;
        color: var(--muted);
        font-size: 0.9rem;
      }

      @media (max-width: 640px) {
        .hero {
          padding: 28px 20px;
        }

        .search-box {
          flex-direction: column;
          align-items: stretch;
        }
      }
    </style>
  </head>
  <body>
    <div class="wrap">
      <header class="hero">
        <h1>Chemical SDS Library</h1>
        <p>
          A centralized catalog of safety, material, and technical data sheets for operational and maintenance chemicals.
          Use the search box below to quickly locate the required document and open it in a new tab for review.
        </p>
      </header>

      <div class="search-box">
        <span class="label">Search</span>
        <input id="searchInput" type="text" placeholder="Search by product, chemical, or document type..." aria-label="Search documents" />
      </div>

      <div class="meta">
        <span>Document index: <strong id="docCount">0</strong> files</span>
        <span>Open behavior: New tab/window</span>
      </div>

      <main class="category-grid">
        <section class="category" data-name="adhesives and sealants">
          <h2>Adhesives &amp; Sealants</h2>
          <ul class="doc-list">
            <li><a href="../101501_WEICON_F_Epoxy_Resin_SDS.pdf" target="_blank" rel="noopener noreferrer"><span class="tag tag-sds">SDS</span>101501 WEICON F Epoxy Resin</a></li>
            <li><a href="../101502_WEICON_F_Epoxy_Hardener_SDS.pdf" target="_blank" rel="noopener noreferrer"><span class="tag tag-sds">SDS</span>101502 WEICON F Epoxy Hardener</a></li>
            <li><a href="../103501_Weicon_WR2_Resin_SDS.pdf" target="_blank" rel="noopener noreferrer"><span class="tag tag-sds">SDS</span>103501 Weicon WR2 Resin</a></li>
            <li><a href="../Hylomar_Universal_Blue_SDS.pdf" target="_blank" rel="noopener noreferrer"><span class="tag tag-sds">SDS</span>Hylomar Universal Blue</a></li>
            <li><a href="../Loctite_243_SDS.PDF" target="_blank" rel="noopener noreferrer"><span class="tag tag-sds">SDS</span>Loctite 243</a></li>
            <li><a href="../Loctite_401_SDS.PDF" target="_blank" rel="noopener noreferrer"><span class="tag tag-sds">SDS</span>Loctite 401</a></li>
            <li><a href="../Loctite_510_SDS.pdf" target="_blank" rel="noopener noreferrer"><span class="tag tag-sds">SDS</span>Loctite 510</a></li>
            <li><a href="../Loctite_577_SDS.pdf" target="_blank" rel="noopener noreferrer"><span class="tag tag-sds">SDS</span>Loctite 577</a></li>
            <li><a href="../Loctite_641_SDS.PDF" target="_blank" rel="noopener noreferrer"><span class="tag tag-sds">SDS</span>Loctite 641</a></li>
            <li><a href="../Permatex_Red_Silicone_81160_SDS.pdf" target="_blank" rel="noopener noreferrer"><span class="tag tag-sds">SDS</span>Permatex Red Silicone 81160</a></li>
            <li><a href="../Wurth_White_Silicone_SDS.PDF" target="_blank" rel="noopener noreferrer"><span class="tag tag-sds">SDS</span>Wurth White Silicone</a></li>
            <li><a href="../Weicon_AntiSeize_HighTech_Assembly_Paste_SDS.pdf" target="_blank" rel="noopener noreferrer"><span class="tag tag-sds">SDS</span>Weicon AntiSeize HighTech Assembly Paste</a></li>
            <li><a href="../Weicon_Leak_Spray_SDS.pdf" target="_blank" rel="noopener noreferrer"><span class="tag tag-sds">SDS</span>Weicon Leak Spray</a></li>
          </ul>
        </section>

        <section class="category" data-name="lubricants and greases">
          <h2>Lubricants &amp; Greases</h2>
          <ul class="doc-list">
            <li><a href="../ADNOC_Grease_SDS.pdf" target="_blank" rel="noopener noreferrer"><span class="tag tag-sds">SDS</span>ADNOC Grease</a></li>
            <li><a href="../Bechem_High_Lub_LT2_EP_MSDS.pdf" target="_blank" rel="noopener noreferrer"><span class="tag tag-msds">MSDS</span>Bechem High Lub LT2 EP</a></li>
            <li><a href="../Chemico_Grinding_Paste_SDS.pdf" target="_blank" rel="noopener noreferrer"><span class="tag tag-sds">SDS</span>Chemico Grinding Paste</a></li>
            <li><a href="../Copaslip_AntiSeize_SDS.pdf" target="_blank" rel="noopener noreferrer"><span class="tag tag-sds">SDS</span>Copaslip AntiSeize</a></li>
            <li><a href="../Cutlight_VC212_Cutting_Oil_MSDS.PDF" target="_blank" rel="noopener noreferrer"><span class="tag tag-msds">MSDS</span>Cutlight VC212 Cutting Oil</a></li>
            <li><a href="../Diamant_Lapping_Paste_SDS.pdf" target="_blank" rel="noopener noreferrer"><span class="tag tag-sds">SDS</span>Diamant Lapping Paste</a></li>
            <li><a href="../Molykote_111_Compound_SDS.pdf" target="_blank" rel="noopener noreferrer"><span class="tag tag-sds">SDS</span>Molykote 111 Compound</a></li>
            <li><a href="../Molykote_55_ORing_Grease_SDS.pdf" target="_blank" rel="noopener noreferrer"><span class="tag tag-sds">SDS</span>Molykote 55 O-Ring Grease</a></li>
            <li><a href="../Molykote_GnPlus_Paste_SDS.pdf" target="_blank" rel="noopener noreferrer"><span class="tag tag-sds">SDS</span>Molykote GN Plus Paste</a></li>
            <li><a href="../Molykote_P37_AntiSeize_Paste_SDS.pdf" target="_blank" rel="noopener noreferrer"><span class="tag tag-sds">SDS</span>Molykote P37 AntiSeize Paste</a></li>
            <li><a href="../SKF_LGHP2_Grease_SDS.pdf" target="_blank" rel="noopener noreferrer"><span class="tag tag-sds">SDS</span>SKF LGHP2 Grease</a></li>
          </ul>
        </section>

        <section class="category" data-name="coatings and paints">
          <h2>Coatings &amp; Paints</h2>
          <ul class="doc-list">
            <li><a href="../ASMACO_Spray_Paint_SDS.pdf" target="_blank" rel="noopener noreferrer"><span class="tag tag-sds">SDS</span>ASMACO Spray Paint</a></li>
            <li><a href="../Berger_Luxathane_5160_Hardener_SDS.pdf" target="_blank" rel="noopener noreferrer"><span class="tag tag-sds">SDS</span>Berger Luxathane 5160 Hardener</a></li>
            <li><a href="../Jotun_Hardtop_XP_Component_A_SDS.pdf" target="_blank" rel="noopener noreferrer"><span class="tag tag-sds">SDS</span>Jotun Hardtop XP Component A</a></li>
            <li><a href="../Jotun_Hardtop_XP_Component_B_SDS.pdf" target="_blank" rel="noopener noreferrer"><span class="tag tag-sds">SDS</span>Jotun Hardtop XP Component B</a></li>
            <li><a href="../Jotun_Solvalitt_Aluminium_SDS.pdf" target="_blank" rel="noopener noreferrer"><span class="tag tag-sds">SDS</span>Jotun Solvalitt Aluminium</a></li>
            <li><a href="../National_Synthetic_Enamel_SDS.pdf" target="_blank" rel="noopener noreferrer"><span class="tag tag-sds">SDS</span>National Synthetic Enamel</a></li>
            <li><a href="../National_Thinner.pdf" target="_blank" rel="noopener noreferrer"><span class="tag tag-sds">SDS</span>National Thinner</a></li>
            <li><a href="../Permatex_Prussian_Blue_80038_MSDS.pdf" target="_blank" rel="noopener noreferrer"><span class="tag tag-msds">MSDS</span>Permatex Prussian Blue 80038</a></li>
            <li><a href="../WEICON_Keramik_BL_Hardener.pdf" target="_blank" rel="noopener noreferrer"><span class="tag tag-sds">SDS</span>WEICON Keramik BL Hardener</a></li>
            <li><a href="../WEICON_Keramik_BL_Resin.pdf" target="_blank" rel="noopener noreferrer"><span class="tag tag-sds">SDS</span>WEICON Keramik BL Resin</a></li>
            <li><a href="../WEICON_WL_Hardener.pdf" target="_blank" rel="noopener noreferrer"><span class="tag tag-sds">SDS</span>WEICON WL Hardener</a></li>
            <li><a href="../WEICON_WL_Resin.pdf" target="_blank" rel="noopener noreferrer"><span class="tag tag-sds">SDS</span>WEICON WL Resin</a></li>
            <li><a href="../WEICON_WR2_Hardener.pdf" target="_blank" rel="noopener noreferrer"><span class="tag tag-sds">SDS</span>WEICON WR2 Hardener</a></li>
          </ul>
        </section>

        <section class="category" data-name="cleaners corrosion and rust removal">
          <h2>Cleaners, Corrosion &amp; Rust Removal</h2>
          <ul class="doc-list">
            <li><a href="../Ambersil_Corrosion_Inhibitor_SDS.pdf" target="_blank" rel="noopener noreferrer"><span class="tag tag-sds">SDS</span>Ambersil Corrosion Inhibitor</a></li>
            <li><a href="../Chemex_Degreaser_Liquid_DG226_Datasheet.pdf" target="_blank" rel="noopener noreferrer"><span class="tag tag-tds">TDS</span>Chemex Degreaser Liquid DG226</a></li>
            <li><a href="../Diesel_SDS.PDF" target="_blank" rel="noopener noreferrer"><span class="tag tag-sds">SDS</span>Diesel</a></li>
            <li><a href="../Unispec_Rust_Remover_SDS.pdf" target="_blank" rel="noopener noreferrer"><span class="tag tag-sds">SDS</span>Unispec Rust Remover</a></li>
            <li><a href="../Unispec_Rust_Remover_TDS.pdf" target="_blank" rel="noopener noreferrer"><span class="tag tag-tds">TDS</span>Unispec Rust Remover</a></li>
            <li><a href="../WD40_MultiUse_Product_Aerosol_SDS.pdf" target="_blank" rel="noopener noreferrer"><span class="tag tag-sds">SDS</span>WD-40 MultiUse Product Aerosol</a></li>
            <li><a href="../WD40_MultiUse_Product_SDS.pdf" target="_blank" rel="noopener noreferrer"><span class="tag tag-sds">SDS</span>WD-40 MultiUse Product</a></li>
            <li><a href="../Weicon_Cleaner_Spray_S_SDS.pdf" target="_blank" rel="noopener noreferrer"><span class="tag tag-sds">SDS</span>Weicon Cleaner Spray S</a></li>
          </ul>
        </section>

        <section class="category" data-name="inspection and ndt">
          <h2>NDT &amp; Inspection</h2>
          <ul class="doc-list">
            <li><a href="../Magnaflux_Spotcheck_Penetrant_SKL_WP2_SDS.pdf" target="_blank" rel="noopener noreferrer"><span class="tag tag-sds">SDS</span>Magnaflux Spotcheck Penetrant SKL WP2</a></li>
            <li><a href="../Magnaflux_Spotcheck_SKC_S_SDS.pdf" target="_blank" rel="noopener noreferrer"><span class="tag tag-sds">SDS</span>Magnaflux Spotcheck SKC S</a></li>
            <li><a href="../Magnaflux_Spotcheck_SKD_S2_SDS.pdf" target="_blank" rel="noopener noreferrer"><span class="tag tag-sds">SDS</span>Magnaflux Spotcheck SKD S2</a></li>
            <li><a href="../Magnaflux_Spotcheck_SKL_SP2_SDS.pdf" target="_blank" rel="noopener noreferrer"><span class="tag tag-sds">SDS</span>Magnaflux Spotcheck SKL SP2</a></li>
            <li><a href="../Magnaflux_Spotcheck_SKL_WP2_SDS.pdf" target="_blank" rel="noopener noreferrer"><span class="tag tag-sds">SDS</span>Magnaflux Spotcheck SKL WP2</a></li>
          </ul>
        </section>

        <section class="category" data-name="miscellaneous and maintenance">
          <h2>Miscellaneous &amp; Maintenance</h2>
          <ul class="doc-list">
            <li><a href="../Cortec_VpCI_368_SDS.pdf" target="_blank" rel="noopener noreferrer"><span class="tag tag-sds">SDS</span>Cortec VpCI 368</a></li>
            <li><a href="../Cortec_VpCI_414_SDS.pdf" target="_blank" rel="noopener noreferrer"><span class="tag tag-sds">SDS</span>Cortec VpCI 414</a></li>
            <li><a href="../WEICON_WL_Hardener.pdf" target="_blank" rel="noopener noreferrer"><span class="tag tag-sds">SDS</span>WEICON WL Hardener</a></li>
            <li><a href="../WEICON_WL_Resin.pdf" target="_blank" rel="noopener noreferrer"><span class="tag tag-sds">SDS</span>WEICON WL Resin</a></li>
            <li><a href="../WEICON_WR2_Hardener.pdf" target="_blank" rel="noopener noreferrer"><span class="tag tag-sds">SDS</span>WEICON WR2 Hardener</a></li>
            <li><a href="../WEICON_Keramik_BL_Hardener.pdf" target="_blank" rel="noopener noreferrer"><span class="tag tag-sds">SDS</span>WEICON Keramik BL Hardener</a></li>
            <li><a href="../WEICON_Keramik_BL_Resin.pdf" target="_blank" rel="noopener noreferrer"><span class="tag tag-sds">SDS</span>WEICON Keramik BL Resin</a></li>
          </ul>
        </section>
      </main>
    </div>

    <script>
      const searchInput = document.getElementById('searchInput');
      const categories = [...document.querySelectorAll('.category')];
      const docCount = document.getElementById('docCount');

      const countDocs = () => {
        const count = [...document.querySelectorAll('.doc-list a')].length;
        docCount.textContent = count;
      };

      const filterDocs = () => {
        const term = searchInput.value.trim().toLowerCase();
        let visibleCount = 0;

        categories.forEach((category) => {
          const items = category.querySelectorAll('.doc-list a');
          let hasVisible = false;

          items.forEach((link) => {
            const text = link.textContent.toLowerCase();
            const isVisible = !term || text.includes(term);
            link.parentElement.style.display = isVisible ? 'block' : 'none';
            if (isVisible) hasVisible = true;
            if (isVisible) visibleCount++;
          });

          category.classList.toggle('hidden', !hasVisible);
        });

        docCount.textContent = visibleCount;
      };

      searchInput.addEventListener('input', filterDocs);
      countDocs();
    </script>
  </body>
</html>
