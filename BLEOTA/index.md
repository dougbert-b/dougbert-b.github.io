<!DOCTYPE html>
<html><head>
<meta http-equiv="content-type" content="text/html; charset=UTF-8"><meta name="viewport" content="width=device-width"><title>https://gb88.github.io/BLEOTA/</title><link rel="stylesheet" type="text/css" href="resource://content-accessible/viewsource.css"></head><body id="viewsource" style="tab-size: 4"><span id="line1"><span></span><span class="doctype">&lt;!DOCTYPE html&gt;</span><span>
</span></span><span id="line2"><span></span><span>&lt;<span class="start-tag">html</span> <span class="attribute-name">lang</span>="<a class="attribute-value">it</a>"&gt;</span><span>
</span></span><span id="line3"><span></span><span>&lt;<span class="start-tag">head</span>&gt;</span><span>
</span></span><span id="line4"><span></span><span>&lt;<span class="start-tag">meta</span> <span class="attribute-name">charset</span>="<a class="attribute-value">UTF-8</a>"&gt;</span><span>
</span></span><span id="line5"><span></span><span>&lt;<span class="start-tag">meta</span> <span class="attribute-name">name</span>="<a class="attribute-value">viewport</a>" <span class="attribute-name">content</span>="<a class="attribute-value">width=device-width, initial-scale=1.0</a>"&gt;</span><span>
</span></span><span id="line6"><span></span><span>&lt;<span class="start-tag">title</span>&gt;</span><span>ESP32 BLE OTA</span><span>&lt;/<span class="end-tag">title</span>&gt;</span><span>
</span></span><span id="line7"><span></span><span>&lt;<span class="start-tag">link</span> <span class="attribute-name">rel</span>="<a class="attribute-value">preconnect</a>" <span class="attribute-name">href</span>="<a class="attribute-value" href="view-source:https://fonts.googleapis.com/">https://fonts.googleapis.com</a>"&gt;</span><span>
</span></span><span id="line8"><span></span><span>&lt;<span class="start-tag">link</span> <span class="attribute-name">href</span>="<a class="attribute-value" href="view-source:https://fonts.googleapis.com/css2?family=IBM+Plex+Mono:wght@400;500&amp;family=IBM+Plex+Sans:wght@400;500;600&amp;display=swap">https://fonts.googleapis.com/css2?family=IBM+Plex+Mono:wght@400;500<span><span>&amp;</span>fa</span>mily=IBM+Plex+Sans:wght@400;500;600<span><span>&amp;</span>dis</span>play=swap</a>" <span class="attribute-name">rel</span>="<a class="attribute-value">stylesheet</a>"&gt;</span><span>
</span></span><span id="line9"><span></span><span>&lt;<span class="start-tag">style</span>&gt;</span><span>
</span></span><span id="line10"><span>  /* ── Tokens: Light (default) ── */
</span></span><span id="line11"><span>  :root {
</span></span><span id="line12"><span>    --bg:        #f5f7fa;
</span></span><span id="line13"><span>    --surface:   #ffffff;
</span></span><span id="line14"><span>    --surface2:  #f0f2f5;
</span></span><span id="line15"><span>    --border:    #dde2ea;
</span></span><span id="line16"><span>    --border2:   #c8d0dc;
</span></span><span id="line17"><span>    --blue:      #2563eb;
</span></span><span id="line18"><span>    --blue-dark: #1d4ed8;
</span></span><span id="line19"><span>    --blue-light:#eff6ff;
</span></span><span id="line20"><span>    --blue-muted:#bfdbfe;
</span></span><span id="line21"><span>    --green:     #16a34a;
</span></span><span id="line22"><span>    --green-bg:  #f0fdf4;
</span></span><span id="line23"><span>    --green-bd:  #bbf7d0;
</span></span><span id="line24"><span>    --red:       #dc2626;
</span></span><span id="line25"><span>    --red-bg:    #fef2f2;
</span></span><span id="line26"><span>    --red-bd:    #fecaca;
</span></span><span id="line27"><span>    --orange:    #d97706;
</span></span><span id="line28"><span>    --orange-bg: #fffbeb;
</span></span><span id="line29"><span>    --orange-bd: #fde68a;
</span></span><span id="line30"><span>    --text:      #111827;
</span></span><span id="line31"><span>    --text2:     #374151;
</span></span><span id="line32"><span>    --text3:     #6b7280;
</span></span><span id="line33"><span>    --text4:     #9ca3af;
</span></span><span id="line34"><span>    --log-bg:    #f8f9fb;
</span></span><span id="line35"><span>    --mono:      'IBM Plex Mono', monospace;
</span></span><span id="line36"><span>    --sans:      'IBM Plex Sans', sans-serif;
</span></span><span id="line37"><span>    --radius:    8px;
</span></span><span id="line38"><span>    --radius-lg: 12px;
</span></span><span id="line39"><span>    --shadow:    0 1px 3px rgba(0,0,0,.08), 0 1px 2px rgba(0,0,0,.04);
</span></span><span id="line40"><span>    --transition: background .2s, border-color .2s, color .2s;
</span></span><span id="line41"><span>  }
</span></span><span id="line42"><span>
</span></span><span id="line43"><span>  /* ── Tokens: Dark ── */
</span></span><span id="line44"><span>  [data-theme="dark"] {
</span></span><span id="line45"><span>    --bg:        #0f1117;
</span></span><span id="line46"><span>    --surface:   #181c27;
</span></span><span id="line47"><span>    --surface2:  #1e2435;
</span></span><span id="line48"><span>    --border:    #2a3145;
</span></span><span id="line49"><span>    --border2:   #374160;
</span></span><span id="line50"><span>    --blue:      #3b82f6;
</span></span><span id="line51"><span>    --blue-dark: #2563eb;
</span></span><span id="line52"><span>    --blue-light:#1e3a5f;
</span></span><span id="line53"><span>    --blue-muted:#1e40af;
</span></span><span id="line54"><span>    --green:     #22c55e;
</span></span><span id="line55"><span>    --green-bg:  #052e16;
</span></span><span id="line56"><span>    --green-bd:  #14532d;
</span></span><span id="line57"><span>    --red:       #f87171;
</span></span><span id="line58"><span>    --red-bg:    #2d0d0d;
</span></span><span id="line59"><span>    --red-bd:    #7f1d1d;
</span></span><span id="line60"><span>    --orange:    #fbbf24;
</span></span><span id="line61"><span>    --orange-bg: #271a00;
</span></span><span id="line62"><span>    --orange-bd: #78350f;
</span></span><span id="line63"><span>    --text:      #f1f5f9;
</span></span><span id="line64"><span>    --text2:     #cbd5e1;
</span></span><span id="line65"><span>    --text3:     #94a3b8;
</span></span><span id="line66"><span>    --text4:     #64748b;
</span></span><span id="line67"><span>    --log-bg:    #0a0d14;
</span></span><span id="line68"><span>    --shadow:    0 1px 4px rgba(0,0,0,.4), 0 1px 2px rgba(0,0,0,.3);
</span></span><span id="line69"><span>  }
</span></span><span id="line70"><span>
</span></span><span id="line71"><span>  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
</span></span><span id="line72"><span>
</span></span><span id="line73"><span>  body {
</span></span><span id="line74"><span>    font-family: var(--sans);
</span></span><span id="line75"><span>    background: var(--bg);
</span></span><span id="line76"><span>    color: var(--text);
</span></span><span id="line77"><span>    min-height: 100vh;
</span></span><span id="line78"><span>    font-size: 14px;
</span></span><span id="line79"><span>    line-height: 1.5;
</span></span><span id="line80"><span>    -webkit-font-smoothing: antialiased;
</span></span><span id="line81"><span>    transition: var(--transition);
</span></span><span id="line82"><span>  }
</span></span><span id="line83"><span>
</span></span><span id="line84"><span>  .page {
</span></span><span id="line85"><span>    max-width: 1200px;
</span></span><span id="line86"><span>    margin: 0 auto;
</span></span><span id="line87"><span>    padding: 24px 20px 56px;
</span></span><span id="line88"><span>  }
</span></span><span id="line89"><span>
</span></span><span id="line90"><span>  /* ── Responsive layout grid ── */
</span></span><span id="line91"><span>  .layout {
</span></span><span id="line92"><span>    display: grid;
</span></span><span id="line93"><span>    grid-template-columns: 1fr;
</span></span><span id="line94"><span>    gap: 12px;
</span></span><span id="line95"><span>  }
</span></span><span id="line96"><span>  .col-left  { display: flex; flex-direction: column; gap: 12px; }
</span></span><span id="line97"><span>  .col-right { display: flex; flex-direction: column; gap: 12px; }
</span></span><span id="line98"><span>
</span></span><span id="line99"><span>  /* ── Header ── */
</span></span><span id="line100"><span>  .header {
</span></span><span id="line101"><span>    display: flex;
</span></span><span id="line102"><span>    align-items: center;
</span></span><span id="line103"><span>    gap: 12px;
</span></span><span id="line104"><span>    margin-bottom: 24px;
</span></span><span id="line105"><span>  }
</span></span><span id="line106"><span>
</span></span><span id="line107"><span>  .header-icon {
</span></span><span id="line108"><span>    width: 40px; height: 40px;
</span></span><span id="line109"><span>    background: var(--blue);
</span></span><span id="line110"><span>    border-radius: 10px;
</span></span><span id="line111"><span>    display: flex; align-items: center; justify-content: center;
</span></span><span id="line112"><span>    flex-shrink: 0;
</span></span><span id="line113"><span>    transition: background .2s;
</span></span><span id="line114"><span>  }
</span></span><span id="line115"><span>  .header-icon svg { width: 22px; height: 22px; fill: white; }
</span></span><span id="line116"><span>
</span></span><span id="line117"><span>  .header-title { font-size: 18px; font-weight: 600; color: var(--text); letter-spacing: -.01em; }
</span></span><span id="line118"><span>  .header-sub   { font-size: 11px; color: var(--text3); font-family: var(--mono); margin-top: 1px; }
</span></span><span id="line119"><span>
</span></span><span id="line120"><span>  .header-controls {
</span></span><span id="line121"><span>    margin-left: auto;
</span></span><span id="line122"><span>    display: flex;
</span></span><span id="line123"><span>    align-items: center;
</span></span><span id="line124"><span>    gap: 6px;
</span></span><span id="line125"><span>  }
</span></span><span id="line126"><span>
</span></span><span id="line127"><span>  /* ── Icon button (theme / lang) ── */
</span></span><span id="line128"><span>  .icon-btn {
</span></span><span id="line129"><span>    width: 32px; height: 32px;
</span></span><span id="line130"><span>    border-radius: var(--radius);
</span></span><span id="line131"><span>    border: 1px solid var(--border);
</span></span><span id="line132"><span>    background: var(--surface);
</span></span><span id="line133"><span>    color: var(--text3);
</span></span><span id="line134"><span>    cursor: pointer;
</span></span><span id="line135"><span>    display: flex; align-items: center; justify-content: center;
</span></span><span id="line136"><span>    transition: background .15s, border-color .15s, color .15s;
</span></span><span id="line137"><span>    flex-shrink: 0;
</span></span><span id="line138"><span>  }
</span></span><span id="line139"><span>  .icon-btn:hover { background: var(--surface2); color: var(--text2); border-color: var(--border2); }
</span></span><span id="line140"><span>  .icon-btn svg { width: 15px; height: 15px; }
</span></span><span id="line141"><span>
</span></span><span id="line142"><span>  /* ── Lang dropdown ── */
</span></span><span id="line143"><span>  .lang-wrap { position: relative; }
</span></span><span id="line144"><span>
</span></span><span id="line145"><span>  .lang-menu {
</span></span><span id="line146"><span>    display: none;
</span></span><span id="line147"><span>    position: absolute;
</span></span><span id="line148"><span>    top: calc(100% + 6px);
</span></span><span id="line149"><span>    right: 0;
</span></span><span id="line150"><span>    background: var(--surface);
</span></span><span id="line151"><span>    border: 1px solid var(--border);
</span></span><span id="line152"><span>    border-radius: var(--radius);
</span></span><span id="line153"><span>    box-shadow: var(--shadow);
</span></span><span id="line154"><span>    min-width: 130px;
</span></span><span id="line155"><span>    z-index: 100;
</span></span><span id="line156"><span>    overflow: hidden;
</span></span><span id="line157"><span>  }
</span></span><span id="line158"><span>  .lang-menu.open { display: block; }
</span></span><span id="line159"><span>
</span></span><span id="line160"><span>  .lang-item {
</span></span><span id="line161"><span>    display: flex;
</span></span><span id="line162"><span>    align-items: center;
</span></span><span id="line163"><span>    gap: 8px;
</span></span><span id="line164"><span>    padding: 8px 12px;
</span></span><span id="line165"><span>    font-size: 12px;
</span></span><span id="line166"><span>    font-weight: 500;
</span></span><span id="line167"><span>    color: var(--text2);
</span></span><span id="line168"><span>    cursor: pointer;
</span></span><span id="line169"><span>    transition: background .12s;
</span></span><span id="line170"><span>    white-space: nowrap;
</span></span><span id="line171"><span>  }
</span></span><span id="line172"><span>  .lang-item:hover { background: var(--surface2); }
</span></span><span id="line173"><span>  .lang-item.active { color: var(--blue); font-weight: 600; }
</span></span><span id="line174"><span>  .lang-flag { font-size: 14px; line-height: 1; }
</span></span><span id="line175"><span>  .lang-current { font-size: 11px; font-weight: 600; font-family: var(--mono); }
</span></span><span id="line176"><span>
</span></span><span id="line177"><span>  /* ── Status pill ── */
</span></span><span id="line178"><span>  .status-pill {
</span></span><span id="line179"><span>    display: flex;
</span></span><span id="line180"><span>    align-items: center;
</span></span><span id="line181"><span>    gap: 6px;
</span></span><span id="line182"><span>    padding: 6px 12px;
</span></span><span id="line183"><span>    border-radius: 10px;
</span></span><span id="line184"><span>    font-size: 12px;
</span></span><span id="line185"><span>    font-family: var(--mono);
</span></span><span id="line186"><span>    background: var(--surface);
</span></span><span id="line187"><span>    border: 1px solid var(--border);
</span></span><span id="line188"><span>    width: 100%;
</span></span><span id="line189"><span>    margin-bottom: 14px;
</span></span><span id="line190"><span>    box-shadow: var(--shadow);
</span></span><span id="line191"><span>    transition: background .2s, border-color .2s, color .2s;
</span></span><span id="line192"><span>    flex-wrap: wrap;
</span></span><span id="line193"><span>  }
</span></span><span id="line194"><span>
</span></span><span id="line195"><span>  /* Error state: red tinted pill so the message stands out */
</span></span><span id="line196"><span>  .status-pill.has-error {
</span></span><span id="line197"><span>    background: var(--red-bg);
</span></span><span id="line198"><span>    border-color: var(--red-bd);
</span></span><span id="line199"><span>  }
</span></span><span id="line200"><span>  .status-pill.has-error .status-text {
</span></span><span id="line201"><span>    color: var(--red);
</span></span><span id="line202"><span>    white-space: normal;
</span></span><span id="line203"><span>    word-break: break-word;
</span></span><span id="line204"><span>  }
</span></span><span id="line205"><span>
</span></span><span id="line206"><span>  .dot {
</span></span><span id="line207"><span>    width: 7px; height: 7px;
</span></span><span id="line208"><span>    border-radius: 50%;
</span></span><span id="line209"><span>    background: var(--border2);
</span></span><span id="line210"><span>    flex-shrink: 0;
</span></span><span id="line211"><span>    transition: background .2s;
</span></span><span id="line212"><span>  }
</span></span><span id="line213"><span>  .dot.scanning  { background: var(--orange); animation: blink .8s infinite; }
</span></span><span id="line214"><span>  .dot.connected { background: var(--green); }
</span></span><span id="line215"><span>  .dot.uploading { background: var(--blue);  animation: blink .5s infinite; }
</span></span><span id="line216"><span>  .dot.error     { background: var(--red); }
</span></span><span id="line217"><span>
</span></span><span id="line218"><span>  @keyframes blink { 0%,100%{opacity:1} 50%{opacity:.3} }
</span></span><span id="line219"><span>
</span></span><span id="line220"><span>  .status-text { flex: 1; color: var(--text2); }
</span></span><span id="line221"><span>  .status-time { color: var(--text4); font-size: 11px; }
</span></span><span id="line222"><span>
</span></span><span id="line223"><span>  /* ── Card ── */
</span></span><span id="line224"><span>  .card {
</span></span><span id="line225"><span>    background: var(--surface);
</span></span><span id="line226"><span>    border: 1px solid var(--border);
</span></span><span id="line227"><span>    border-radius: var(--radius-lg);
</span></span><span id="line228"><span>    padding: 20px;
</span></span><span id="line229"><span>    margin-bottom: 12px;
</span></span><span id="line230"><span>    box-shadow: var(--shadow);
</span></span><span id="line231"><span>    transition: var(--transition);
</span></span><span id="line232"><span>  }
</span></span><span id="line233"><span>
</span></span><span id="line234"><span>  .card-label {
</span></span><span id="line235"><span>    font-size: 11px; font-weight: 600;
</span></span><span id="line236"><span>    text-transform: uppercase; letter-spacing: .06em;
</span></span><span id="line237"><span>    color: var(--text3);
</span></span><span id="line238"><span>    margin-bottom: 14px;
</span></span><span id="line239"><span>    display: flex; align-items: center; gap: 6px;
</span></span><span id="line240"><span>  }
</span></span><span id="line241"><span>  .card-label svg { width: 13px; height: 13px; }
</span></span><span id="line242"><span>
</span></span><span id="line243"><span>  /* ── Device grid ── */
</span></span><span id="line244"><span>  .dev-grid {
</span></span><span id="line245"><span>    display: grid;
</span></span><span id="line246"><span>    grid-template-columns: 1fr 1fr;
</span></span><span id="line247"><span>    gap: 8px;
</span></span><span id="line248"><span>    margin-bottom: 16px;
</span></span><span id="line249"><span>  }
</span></span><span id="line250"><span>  .dev-cell {
</span></span><span id="line251"><span>    background: var(--bg);
</span></span><span id="line252"><span>    border: 1px solid var(--border);
</span></span><span id="line253"><span>    border-radius: var(--radius);
</span></span><span id="line254"><span>    padding: 10px 12px;
</span></span><span id="line255"><span>    transition: var(--transition);
</span></span><span id="line256"><span>  }
</span></span><span id="line257"><span>  .dev-cell-label { font-size: 10px; font-weight: 600; text-transform: uppercase; letter-spacing: .06em; color: var(--text4); margin-bottom: 2px; }
</span></span><span id="line258"><span>  .dev-cell-value { font-family: var(--mono); font-size: 12px; color: var(--text2); white-space: nowrap; overflow: hidden; text-overflow: ellipsis; }
</span></span><span id="line259"><span>  .dev-cell-value.name { color: var(--blue); font-weight: 500; }
</span></span><span id="line260"><span>
</span></span><span id="line261"><span>  /* ── Buttons ── */
</span></span><span id="line262"><span>  .btn {
</span></span><span id="line263"><span>    display: inline-flex; align-items: center; gap: 6px;
</span></span><span id="line264"><span>    padding: 8px 16px;
</span></span><span id="line265"><span>    border-radius: var(--radius);
</span></span><span id="line266"><span>    font-family: var(--sans); font-size: 13px; font-weight: 500;
</span></span><span id="line267"><span>    border: 1px solid transparent;
</span></span><span id="line268"><span>    cursor: pointer;
</span></span><span id="line269"><span>    transition: background .15s, border-color .15s, opacity .15s;
</span></span><span id="line270"><span>    white-space: nowrap; user-select: none;
</span></span><span id="line271"><span>  }
</span></span><span id="line272"><span>  .btn:disabled { opacity: .4; pointer-events: none; }
</span></span><span id="line273"><span>  .btn svg { width: 14px; height: 14px; flex-shrink: 0; }
</span></span><span id="line274"><span>
</span></span><span id="line275"><span>  .btn-primary { background: var(--blue); color: white; border-color: var(--blue); }
</span></span><span id="line276"><span>  .btn-primary:hover { background: var(--blue-dark); border-color: var(--blue-dark); }
</span></span><span id="line277"><span>
</span></span><span id="line278"><span>  .btn-ghost { background: transparent; color: var(--text2); border-color: var(--border); }
</span></span><span id="line279"><span>  .btn-ghost:hover { background: var(--surface2); border-color: var(--border2); }
</span></span><span id="line280"><span>
</span></span><span id="line281"><span>  .btn-danger { background: transparent; color: var(--red); border-color: var(--red-bd); }
</span></span><span id="line282"><span>  .btn-danger:hover { background: var(--red-bg); }
</span></span><span id="line283"><span>
</span></span><span id="line284"><span>  .btn-row { display: flex; gap: 8px; flex-wrap: wrap; }
</span></span><span id="line285"><span>
</span></span><span id="line286"><span>  /* ── Segment ── */
</span></span><span id="line287"><span>  .seg {
</span></span><span id="line288"><span>    display: flex;
</span></span><span id="line289"><span>    background: var(--bg);
</span></span><span id="line290"><span>    border: 1px solid var(--border);
</span></span><span id="line291"><span>    border-radius: var(--radius);
</span></span><span id="line292"><span>    padding: 3px; gap: 3px;
</span></span><span id="line293"><span>    margin-bottom: 16px;
</span></span><span id="line294"><span>    transition: var(--transition);
</span></span><span id="line295"><span>  }
</span></span><span id="line296"><span>  .seg-btn {
</span></span><span id="line297"><span>    flex: 1; padding: 7px 12px;
</span></span><span id="line298"><span>    border: none; border-radius: 5px;
</span></span><span id="line299"><span>    background: transparent; color: var(--text3);
</span></span><span id="line300"><span>    font-family: var(--sans); font-size: 12px; font-weight: 500;
</span></span><span id="line301"><span>    cursor: pointer; transition: all .15s;
</span></span><span id="line302"><span>    display: flex; align-items: center; justify-content: center; gap: 5px;
</span></span><span id="line303"><span>  }
</span></span><span id="line304"><span>  .seg-btn svg { width: 13px; height: 13px; }
</span></span><span id="line305"><span>  .seg-btn.active { background: var(--surface); color: var(--blue); box-shadow: 0 1px 3px rgba(0,0,0,.12); font-weight: 600; }
</span></span><span id="line306"><span>
</span></span><span id="line307"><span>  /* ── Drop zone ── */
</span></span><span id="line308"><span>  .dropzone {
</span></span><span id="line309"><span>    border: 2px dashed var(--border2);
</span></span><span id="line310"><span>    border-radius: var(--radius);
</span></span><span id="line311"><span>    padding: 28px 20px; text-align: center;
</span></span><span id="line312"><span>    cursor: pointer; position: relative; background: var(--bg);
</span></span><span id="line313"><span>    transition: border-color .15s, background .15s;
</span></span><span id="line314"><span>  }
</span></span><span id="line315"><span>  .dropzone:hover, .dropzone.over { border-color: var(--blue); background: var(--blue-light); }
</span></span><span id="line316"><span>  .dropzone input { position: absolute; inset: 0; opacity: 0; cursor: pointer; width: 100%; height: 100%; }
</span></span><span id="line317"><span>  .dz-icon { margin-bottom: 8px; color: var(--text4); }
</span></span><span id="line318"><span>  .dz-icon svg { width: 28px; height: 28px; }
</span></span><span id="line319"><span>  .dz-title { font-size: 13px; font-weight: 500; color: var(--text2); margin-bottom: 2px; }
</span></span><span id="line320"><span>  .dz-sub   { font-size: 11px; color: var(--text4); font-family: var(--mono); }
</span></span><span id="line321"><span>
</span></span><span id="line322"><span>  /* ── File badge ── */
</span></span><span id="line323"><span>  .file-badge {
</span></span><span id="line324"><span>    display: flex; align-items: center; gap: 10px;
</span></span><span id="line325"><span>    padding: 10px 12px;
</span></span><span id="line326"><span>    background: var(--green-bg); border: 1px solid var(--green-bd);
</span></span><span id="line327"><span>    border-radius: var(--radius); margin-top: 10px;
</span></span><span id="line328"><span>    transition: var(--transition);
</span></span><span id="line329"><span>  }
</span></span><span id="line330"><span>  .file-badge svg { width: 15px; height: 15px; color: var(--green); flex-shrink: 0; }
</span></span><span id="line331"><span>  .file-badge-name { font-family: var(--mono); font-size: 12px; color: var(--green); flex: 1; overflow: hidden; text-overflow: ellipsis; white-space: nowrap; }
</span></span><span id="line332"><span>  .file-badge-size { font-family: var(--mono); font-size: 11px; color: var(--text4); white-space: nowrap; }
</span></span><span id="line333"><span>
</span></span><span id="line334"><span>  /* ── Alert ── */
</span></span><span id="line335"><span>  .alert { display: flex; gap: 8px; align-items: flex-start; padding: 10px 12px; border-radius: var(--radius); font-size: 12px; line-height: 1.5; margin-bottom: 12px; }
</span></span><span id="line336"><span>  .alert svg { width: 14px; height: 14px; flex-shrink: 0; margin-top: 1px; }
</span></span><span id="line337"><span>  .alert-warn  { background: var(--orange-bg); border: 1px solid var(--orange-bd); color: var(--orange); }
</span></span><span id="line338"><span>  .alert-error { background: var(--red-bg);    border: 1px solid var(--red-bd);    color: var(--red); }
</span></span><span id="line339"><span>
</span></span><span id="line340"><span>  .alert-body { display: flex; flex-direction: column; gap: 4px; }
</span></span><span id="line341"><span>  .alert-title { font-weight: 600; font-size: 12px; }
</span></span><span id="line342"><span>  .alert-desc  { font-size: 11.5px; opacity: .85; line-height: 1.5; }
</span></span><span id="line343"><span>  .alert-desc a { color: inherit; font-weight: 600; }
</span></span><span id="line344"><span>  .alert-desc code {
</span></span><span id="line345"><span>    font-family: var(--mono);
</span></span><span id="line346"><span>    font-size: 10.5px;
</span></span><span id="line347"><span>    background: rgba(0,0,0,.08);
</span></span><span id="line348"><span>    padding: 1px 5px;
</span></span><span id="line349"><span>    border-radius: 4px;
</span></span><span id="line350"><span>  }
</span></span><span id="line351"><span>  [data-theme="dark"] .alert-desc code { background: rgba(255,255,255,.1); }
</span></span><span id="line352"><span>
</span></span><span id="line353"><span>  hr { border: none; border-top: 1px solid var(--border); margin: 16px 0; }
</span></span><span id="line354"><span>
</span></span><span id="line355"><span>  /* ── Progress ── */
</span></span><span id="line356"><span>  .prog-header { display: flex; justify-content: space-between; align-items: baseline; margin-bottom: 6px; }
</span></span><span id="line357"><span>  .prog-label  { font-size: 12px; font-weight: 500; color: var(--text2); }
</span></span><span id="line358"><span>  .prog-pct    { font-family: var(--mono); font-size: 12px; color: var(--blue); font-weight: 500; }
</span></span><span id="line359"><span>
</span></span><span id="line360"><span>  .prog-track { height: 6px; background: var(--bg); border: 1px solid var(--border); border-radius: 999px; overflow: hidden; }
</span></span><span id="line361"><span>  .prog-fill  { height: 100%; background: var(--blue); border-radius: 999px; transition: width .3s ease; position: relative; overflow: hidden; }
</span></span><span id="line362"><span>  .prog-fill::after { content:''; position:absolute; inset:0; background: linear-gradient(90deg,transparent,rgba(255,255,255,.35),transparent); animation: shim 1.4s infinite; }
</span></span><span id="line363"><span>  @keyframes shim { from{transform:translateX(-100%)} to{transform:translateX(200%)} }
</span></span><span id="line364"><span>
</span></span><span id="line365"><span>  .prog-stats { display: flex; gap: 16px; margin-top: 10px; flex-wrap: wrap; }
</span></span><span id="line366"><span>  .stat { display: flex; flex-direction: column; gap: 1px; }
</span></span><span id="line367"><span>  .stat-k { font-size: 10px; text-transform: uppercase; letter-spacing: .05em; color: var(--text4); font-weight: 600; }
</span></span><span id="line368"><span>  .stat-v { font-family: var(--mono); font-size: 12px; color: var(--text2); }
</span></span><span id="line369"><span>
</span></span><span id="line370"><span>  /* ── Success ── */
</span></span><span id="line371"><span>  .success-box { display:none; flex-direction:column; align-items:center; padding:24px 16px; text-align:center; }
</span></span><span id="line372"><span>  .success-box.show { display:flex; }
</span></span><span id="line373"><span>  .success-ring { width:52px; height:52px; border-radius:50%; border:2px solid var(--green); background:var(--green-bg); display:flex; align-items:center; justify-content:center; margin-bottom:12px; animation:pop .35s cubic-bezier(.34,1.56,.64,1); }
</span></span><span id="line374"><span>  .success-ring svg { width:24px; height:24px; color:var(--green); }
</span></span><span id="line375"><span>  @keyframes pop { from{transform:scale(0);opacity:0} to{transform:scale(1);opacity:1} }
</span></span><span id="line376"><span>  .success-title { font-size:15px; font-weight:600; color:var(--green); margin-bottom:3px; }
</span></span><span id="line377"><span>  .success-sub   { font-size:12px; color:var(--text3); }
</span></span><span id="line378"><span>
</span></span><span id="line379"><span>  /* ── Log ── */
</span></span><span id="line380"><span>  .log-wrap {
</span></span><span id="line381"><span>    background: var(--log-bg);
</span></span><span id="line382"><span>    border: 1px solid var(--border);
</span></span><span id="line383"><span>    border-radius: var(--radius);
</span></span><span id="line384"><span>    height: 220px;
</span></span><span id="line385"><span>    max-height: 220px;
</span></span><span id="line386"><span>    overflow-y: auto;
</span></span><span id="line387"><span>    overflow-x: hidden;
</span></span><span id="line388"><span>    padding: 10px 12px;
</span></span><span id="line389"><span>    font-family: var(--mono); font-size: 11.5px; line-height: 1.7;
</span></span><span id="line390"><span>    transition: background .2s, border-color .2s;
</span></span><span id="line391"><span>    /* Never let flex or grid stretch this box */
</span></span><span id="line392"><span>    flex-shrink: 0;
</span></span><span id="line393"><span>    flex-grow: 0;
</span></span><span id="line394"><span>  }
</span></span><span id="line395"><span>  .log-wrap::-webkit-scrollbar { width: 4px; }
</span></span><span id="line396"><span>  .log-wrap::-webkit-scrollbar-thumb { background: var(--border2); border-radius: 2px; }
</span></span><span id="line397"><span>
</span></span><span id="line398"><span>  /* ── Log toggle switch ── */
</span></span><span id="line399"><span>  .log-toggle-btn {
</span></span><span id="line400"><span>    margin-left: auto;
</span></span><span id="line401"><span>    display: flex;
</span></span><span id="line402"><span>    align-items: center;
</span></span><span id="line403"><span>    gap: 6px;
</span></span><span id="line404"><span>    background: none;
</span></span><span id="line405"><span>    border: none;
</span></span><span id="line406"><span>    cursor: pointer;
</span></span><span id="line407"><span>    padding: 2px 4px;
</span></span><span id="line408"><span>    border-radius: 4px;
</span></span><span id="line409"><span>    transition: background .15s;
</span></span><span id="line410"><span>  }
</span></span><span id="line411"><span>  .log-toggle-btn:hover { background: var(--surface2); }
</span></span><span id="line412"><span>
</span></span><span id="line413"><span>  .log-toggle-track {
</span></span><span id="line414"><span>    position: relative;
</span></span><span id="line415"><span>    width: 28px; height: 16px;
</span></span><span id="line416"><span>    background: var(--border2);
</span></span><span id="line417"><span>    border-radius: 999px;
</span></span><span id="line418"><span>    transition: background .2s;
</span></span><span id="line419"><span>    flex-shrink: 0;
</span></span><span id="line420"><span>  }
</span></span><span id="line421"><span>  .log-toggle-track.on { background: var(--blue); }
</span></span><span id="line422"><span>
</span></span><span id="line423"><span>  .log-toggle-thumb {
</span></span><span id="line424"><span>    position: absolute;
</span></span><span id="line425"><span>    top: 2px; left: 2px;
</span></span><span id="line426"><span>    width: 12px; height: 12px;
</span></span><span id="line427"><span>    background: white;
</span></span><span id="line428"><span>    border-radius: 50%;
</span></span><span id="line429"><span>    transition: transform .2s;
</span></span><span id="line430"><span>    box-shadow: 0 1px 2px rgba(0,0,0,.2);
</span></span><span id="line431"><span>  }
</span></span><span id="line432"><span>  .log-toggle-track.on .log-toggle-thumb { transform: translateX(12px); }
</span></span><span id="line433"><span>
</span></span><span id="line434"><span>  .log-toggle-label {
</span></span><span id="line435"><span>    font-size: 10px;
</span></span><span id="line436"><span>    font-weight: 600;
</span></span><span id="line437"><span>    text-transform: uppercase;
</span></span><span id="line438"><span>    letter-spacing: .05em;
</span></span><span id="line439"><span>    color: var(--text4);
</span></span><span id="line440"><span>    font-family: var(--mono);
</span></span><span id="line441"><span>    white-space: nowrap;
</span></span><span id="line442"><span>  }
</span></span><span id="line443"><span>  .log-toggle-track.on + .log-toggle-label { color: var(--blue); }
</span></span><span id="line444"><span>
</span></span><span id="line445"><span>  /* ── Log disabled overlay ── */
</span></span><span id="line446"><span>  .log-disabled {
</span></span><span id="line447"><span>    display: flex;
</span></span><span id="line448"><span>    flex-direction: column;
</span></span><span id="line449"><span>    align-items: center;
</span></span><span id="line450"><span>    justify-content: center;
</span></span><span id="line451"><span>    gap: 8px;
</span></span><span id="line452"><span>    padding: 32px 16px;
</span></span><span id="line453"><span>    color: var(--text4);
</span></span><span id="line454"><span>    font-size: 12px;
</span></span><span id="line455"><span>    text-align: center;
</span></span><span id="line456"><span>    height: 220px;
</span></span><span id="line457"><span>    flex-shrink: 0;
</span></span><span id="line458"><span>  }
</span></span><span id="line459"><span>  .log-disabled svg { width: 28px; height: 28px; opacity: .4; }
</span></span><span id="line460"><span>  .log-disabled.hidden { display: none !important; }
</span></span><span id="line461"><span>
</span></span><span id="line462"><span>  .le { display:flex; gap:8px; }
</span></span><span id="line463"><span>  .lt { color: var(--text4); flex-shrink: 0; }
</span></span><span id="line464"><span>  .lm.info    { color: var(--text3); }
</span></span><span id="line465"><span>  .lm.accent  { color: var(--blue); }
</span></span><span id="line466"><span>  .lm.success { color: var(--green); }
</span></span><span id="line467"><span>  .lm.error   { color: var(--red); }
</span></span><span id="line468"><span>  .lm.warn    { color: var(--orange); }
</span></span><span id="line469"><span>
</span></span><span id="line470"><span>  footer { text-align:center; margin-top:32px; font-size:11px; color:var(--text4); font-family:var(--mono); }
</span></span><span id="line471"><span>  footer a { color:var(--blue); text-decoration:none; }
</span></span><span id="line472"><span>
</span></span><span id="line473"><span>  .hidden { display:none !important; }
</span></span><span id="line474"><span>
</span></span><span id="line475"><span>  /* ════ BREAKPOINTS ════ */
</span></span><span id="line476"><span>
</span></span><span id="line477"><span>  /* ── Mobile: ≤ 639px ── */
</span></span><span id="line478"><span>  @media (max-width:639px) {
</span></span><span id="line479"><span>
</span></span><span id="line480"><span>    /* Base font bigger on mobile */
</span></span><span id="line481"><span>    body { font-size: 16px; }
</span></span><span id="line482"><span>
</span></span><span id="line483"><span>    .page { padding: 16px 14px 56px; }
</span></span><span id="line484"><span>
</span></span><span id="line485"><span>    /* Header */
</span></span><span id="line486"><span>    .header { flex-wrap: wrap; gap: 8px; margin-bottom: 20px; }
</span></span><span id="line487"><span>    .header-icon { width: 44px; height: 44px; }
</span></span><span id="line488"><span>    .header-icon svg { width: 24px; height: 24px; }
</span></span><span id="line489"><span>    .header-title { font-size: 20px; }
</span></span><span id="line490"><span>    .header-sub   { font-size: 12px; }
</span></span><span id="line491"><span>    .header-controls { margin-left: auto; }
</span></span><span id="line492"><span>
</span></span><span id="line493"><span>    /* Status pill */
</span></span><span id="line494"><span>    .status-pill { font-size: 13px; padding: 8px 14px; border-radius: 12px; margin-bottom: 16px; }
</span></span><span id="line495"><span>    .dot { width: 9px; height: 9px; }
</span></span><span id="line496"><span>
</span></span><span id="line497"><span>    /* Cards */
</span></span><span id="line498"><span>    .card { padding: 18px 16px; border-radius: 14px; margin-bottom: 14px; }
</span></span><span id="line499"><span>    .card-label { font-size: 13px; margin-bottom: 16px; }
</span></span><span id="line500"><span>    .card-label svg { width: 15px; height: 15px; }
</span></span><span id="line501"><span>
</span></span><span id="line502"><span>    /* Device grid: 2 colonne */
</span></span><span id="line503"><span>    .dev-grid { grid-template-columns: 1fr 1fr; gap: 8px; margin-bottom: 18px; }
</span></span><span id="line504"><span>    .dev-cell { padding: 12px 14px; border-radius: 10px; }
</span></span><span id="line505"><span>    .dev-cell-label { font-size: 11px; margin-bottom: 3px; }
</span></span><span id="line506"><span>    .dev-cell-value { font-size: 14px; }
</span></span><span id="line507"><span>
</span></span><span id="line508"><span>    /* Buttons — grandi e touch-friendly */
</span></span><span id="line509"><span>    .btn { padding: 13px 20px; font-size: 15px; border-radius: 10px; }
</span></span><span id="line510"><span>    .btn svg { width: 18px; height: 18px; }
</span></span><span id="line511"><span>    .btn-row { flex-direction: column; gap: 10px; }
</span></span><span id="line512"><span>    .btn-row .btn { width: 100%; justify-content: center; }
</span></span><span id="line513"><span>
</span></span><span id="line514"><span>    /* Icon buttons (theme/lang) */
</span></span><span id="line515"><span>    .icon-btn { width: 40px; height: 40px; border-radius: 10px; }
</span></span><span id="line516"><span>    .icon-btn svg { width: 18px; height: 18px; }
</span></span><span id="line517"><span>    .lang-current { font-size: 12px; }
</span></span><span id="line518"><span>
</span></span><span id="line519"><span>    /* Segment */
</span></span><span id="line520"><span>    .seg { gap: 4px; padding: 4px; }
</span></span><span id="line521"><span>    .seg-btn { font-size: 14px; padding: 10px 14px; border-radius: 8px; }
</span></span><span id="line522"><span>    .seg-btn svg { width: 16px; height: 16px; }
</span></span><span id="line523"><span>
</span></span><span id="line524"><span>    /* Drop zone */
</span></span><span id="line525"><span>    .dropzone { padding: 28px 20px; border-radius: 12px; }
</span></span><span id="line526"><span>    .dz-icon svg { width: 36px; height: 36px; }
</span></span><span id="line527"><span>    .dz-title { font-size: 15px; }
</span></span><span id="line528"><span>    .dz-sub   { font-size: 13px; }
</span></span><span id="line529"><span>
</span></span><span id="line530"><span>    /* File badge */
</span></span><span id="line531"><span>    .file-badge { padding: 14px 16px; border-radius: 10px; margin-top: 12px; }
</span></span><span id="line532"><span>    .file-badge svg { width: 20px; height: 20px; }
</span></span><span id="line533"><span>    .file-badge-name { font-size: 14px; }
</span></span><span id="line534"><span>    .file-badge-size { font-size: 13px; }
</span></span><span id="line535"><span>
</span></span><span id="line536"><span>    /* Progress */
</span></span><span id="line537"><span>    .prog-header { margin-bottom: 10px; }
</span></span><span id="line538"><span>    .prog-label  { font-size: 14px; }
</span></span><span id="line539"><span>    .prog-pct    { font-size: 14px; }
</span></span><span id="line540"><span>    .prog-track  { height: 8px; }
</span></span><span id="line541"><span>    .prog-stats  { display: grid; grid-template-columns: 1fr 1fr; gap: 10px; margin-top: 14px; }
</span></span><span id="line542"><span>    .stat-k { font-size: 11px; }
</span></span><span id="line543"><span>    .stat-v { font-size: 14px; }
</span></span><span id="line544"><span>
</span></span><span id="line545"><span>    /* Success */
</span></span><span id="line546"><span>    .success-ring { width: 64px; height: 64px; }
</span></span><span id="line547"><span>    .success-ring svg { width: 32px; height: 32px; }
</span></span><span id="line548"><span>    .success-title { font-size: 17px; }
</span></span><span id="line549"><span>    .success-sub   { font-size: 14px; }
</span></span><span id="line550"><span>
</span></span><span id="line551"><span>    /* Log */
</span></span><span id="line552"><span>    .log-wrap      { height: 200px; font-size: 12.5px; line-height: 1.8; }
</span></span><span id="line553"><span>    .log-disabled  { height: 200px; font-size: 14px; }
</span></span><span id="line554"><span>    .log-toggle-label { font-size: 12px; }
</span></span><span id="line555"><span>    .log-toggle-track { width: 34px; height: 20px; }
</span></span><span id="line556"><span>    .log-toggle-thumb { width: 16px; height: 16px; }
</span></span><span id="line557"><span>    .log-toggle-track.on .log-toggle-thumb { transform: translateX(14px); }
</span></span><span id="line558"><span>
</span></span><span id="line559"><span>    /* Alerts */
</span></span><span id="line560"><span>    .alert { font-size: 13px; padding: 14px 16px; border-radius: 10px; }
</span></span><span id="line561"><span>    .alert-title { font-size: 14px; }
</span></span><span id="line562"><span>    .alert-desc  { font-size: 13px; }
</span></span><span id="line563"><span>
</span></span><span id="line564"><span>    /* HR */
</span></span><span id="line565"><span>    hr { margin: 18px 0; }
</span></span><span id="line566"><span>  }
</span></span><span id="line567"><span>
</span></span><span id="line568"><span>  /* ── Very small phones: ≤ 380px ── */
</span></span><span id="line569"><span>  @media (max-width:380px) {
</span></span><span id="line570"><span>    body { font-size: 15px; }
</span></span><span id="line571"><span>    .header-sub { display: none; }
</span></span><span id="line572"><span>    .dev-grid   { grid-template-columns: 1fr; }
</span></span><span id="line573"><span>    .page       { padding: 14px 12px 48px; }
</span></span><span id="line574"><span>  }
</span></span><span id="line575"><span>
</span></span><span id="line576"><span>  /* ── Tablet: 640–1023px ── */
</span></span><span id="line577"><span>  @media (min-width:640px) and (max-width:1023px) {
</span></span><span id="line578"><span>    body { font-size: 15px; }
</span></span><span id="line579"><span>    .page { padding: 24px 24px 64px; }
</span></span><span id="line580"><span>    .dev-grid { grid-template-columns: repeat(3, 1fr); }
</span></span><span id="line581"><span>    .log-wrap     { height: 240px; }
</span></span><span id="line582"><span>    .log-disabled { height: 240px; }
</span></span><span id="line583"><span>    .card { padding: 22px; }
</span></span><span id="line584"><span>    .btn  { padding: 11px 20px; font-size: 14px; }
</span></span><span id="line585"><span>  }
</span></span><span id="line586"><span>
</span></span><span id="line587"><span>  /* Desktop: 1024px+ — two-column layout, heights managed by JS syncLogHeight() */
</span></span><span id="line588"><span>  @media (min-width:1024px) {
</span></span><span id="line589"><span>    .page { padding: 36px 40px 72px; }
</span></span><span id="line590"><span>    .layout {
</span></span><span id="line591"><span>      grid-template-columns: 1fr 1fr;
</span></span><span id="line592"><span>      gap: 16px;
</span></span><span id="line593"><span>      align-items: start;
</span></span><span id="line594"><span>    }
</span></span><span id="line595"><span>    .col-left  { gap: 16px; }
</span></span><span id="line596"><span>    .col-right { display: flex; flex-direction: column; overflow: hidden; }
</span></span><span id="line597"><span>    .col-right .card {
</span></span><span id="line598"><span>      display: flex; flex-direction: column;
</span></span><span id="line599"><span>      overflow: hidden; box-sizing: border-box;
</span></span><span id="line600"><span>    }
</span></span><span id="line601"><span>    .col-right .log-wrap     { flex-shrink: 0; }
</span></span><span id="line602"><span>    .col-right .log-disabled { flex-shrink: 0; }
</span></span><span id="line603"><span>    .dev-grid { grid-template-columns: 1fr 1fr; }
</span></span><span id="line604"><span>    .header-title { font-size: 20px; }
</span></span><span id="line605"><span>  }
</span></span><span id="line606"><span>
</span></span><span id="line607"><span>  /* Wide: 1280px+ */
</span></span><span id="line608"><span>  @media (min-width:1280px) {
</span></span><span id="line609"><span>    .page { padding: 40px 48px 80px; }
</span></span><span id="line610"><span>    .layout { gap: 20px; }
</span></span><span id="line611"><span>    .card { padding: 28px; }
</span></span><span id="line612"><span>  }
</span></span><span id="line613"><span>
</span></span><span id="line614"><span>  /* Ultra-wide: 1440px+ */
</span></span><span id="line615"><span>  @media (min-width:1440px) {
</span></span><span id="line616"><span>    .layout { grid-template-columns: 5fr 4fr; }
</span></span><span id="line617"><span>  }
</span></span><span id="line618"><span></span><span>&lt;/<span class="end-tag">style</span>&gt;</span><span>
</span></span><span id="line619"><span></span><span>&lt;/<span class="end-tag">head</span>&gt;</span><span>
</span></span><span id="line620"><span></span><span>&lt;<span class="start-tag">body</span>&gt;</span><span>
</span></span><span id="line621"><span></span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">page</a>"&gt;</span><span>
</span></span><span id="line622"><span>
</span></span><span id="line623"><span>  </span><span class="comment">&lt;!-- Header --&gt;</span><span>
</span></span><span id="line624"><span>  </span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">header</a>"&gt;</span><span>
</span></span><span id="line625"><span>    </span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">header-icon</a>"&gt;</span><span>
</span></span><span id="line626"><span>      </span><span>&lt;<span class="start-tag">svg</span> <span class="attribute-name">viewBox</span>="<a class="attribute-value">0 0 24 24</a>"&gt;</span><span></span><span>&lt;<span class="start-tag">path</span> <span class="attribute-name">d</span>="<a class="attribute-value">M14.5 2.5L10 7l4.5 4.5L10 16l1.5 1.5 6-6-6-6zM7 2.5L2.5 7 7 11.5 2.5 16 4 17.5l6-6-6-6z</a>"<span>/</span>&gt;</span><span></span><span>&lt;/<span class="end-tag">svg</span>&gt;</span><span>
</span></span><span id="line627"><span>    </span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span>
</span></span><span id="line628"><span>    </span><span>&lt;<span class="start-tag">div</span>&gt;</span><span>
</span></span><span id="line629"><span>      </span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">header-title</a>"&gt;</span><span>ESP32 BLE OTA</span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span>
</span></span><span id="line630"><span>      </span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">header-sub</a>" <span class="attribute-name">data-i18n</span>="<a class="attribute-value">subtitle</a>"&gt;</span><span>Firmware updater · Web Bluetooth</span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span>
</span></span><span id="line631"><span>    </span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span>
</span></span><span id="line632"><span>    </span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">header-controls</a>"&gt;</span><span>
</span></span><span id="line633"><span>      </span><span class="comment">&lt;!-- Theme toggle --&gt;</span><span>
</span></span><span id="line634"><span>      </span><span>&lt;<span class="start-tag">button</span> <span class="attribute-name">class</span>="<a class="attribute-value">icon-btn</a>" <span class="attribute-name">id</span>="<a class="attribute-value">themeBtn</a>" <span class="attribute-name">onclick</span>="<a class="attribute-value">toggleTheme()</a>" <span class="attribute-name">title</span>="<a class="attribute-value">Toggle theme</a>"&gt;</span><span>
</span></span><span id="line635"><span>        </span><span>&lt;<span class="start-tag">svg</span> <span class="attribute-name">id</span>="<a class="attribute-value">themeIcon</a>" <span class="attribute-name">viewBox</span>="<a class="attribute-value">0 0 24 24</a>" <span class="attribute-name">fill</span>="<a class="attribute-value">none</a>" <span class="attribute-name">stroke</span>="<a class="attribute-value">currentColor</a>" <span class="attribute-name">stroke-width</span>="<a class="attribute-value">2</a>"&gt;</span><span>
</span></span><span id="line636"><span>          </span><span>&lt;<span class="start-tag">path</span> <span class="attribute-name">d</span>="<a class="attribute-value">M21 12.79A9 9 0 1 1 11.21 3 7 7 0 0 0 21 12.79z</a>"<span>/</span>&gt;</span><span>
</span></span><span id="line637"><span>        </span><span>&lt;/<span class="end-tag">svg</span>&gt;</span><span>
</span></span><span id="line638"><span>      </span><span>&lt;/<span class="end-tag">button</span>&gt;</span><span>
</span></span><span id="line639"><span>      </span><span class="comment">&lt;!-- Language dropdown --&gt;</span><span>
</span></span><span id="line640"><span>      </span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">lang-wrap</a>"&gt;</span><span>
</span></span><span id="line641"><span>        </span><span>&lt;<span class="start-tag">button</span> <span class="attribute-name">class</span>="<a class="attribute-value">icon-btn</a>" <span class="attribute-name">id</span>="<a class="attribute-value">langBtn</a>" <span class="attribute-name">onclick</span>="<a class="attribute-value">toggleLangMenu()</a>" <span class="attribute-name">style</span>="<a class="attribute-value">width:auto;padding:0 8px;gap:4px;min-width:52px</a>"&gt;</span><span>
</span></span><span id="line642"><span>          </span><span>&lt;<span class="start-tag">span</span> <span class="attribute-name">class</span>="<a class="attribute-value">lang-flag</a>" <span class="attribute-name">id</span>="<a class="attribute-value">langFlag</a>"&gt;</span><span>🇮🇹</span><span>&lt;/<span class="end-tag">span</span>&gt;</span><span>
</span></span><span id="line643"><span>          </span><span>&lt;<span class="start-tag">span</span> <span class="attribute-name">class</span>="<a class="attribute-value">lang-current</a>" <span class="attribute-name">id</span>="<a class="attribute-value">langCode</a>"&gt;</span><span>IT</span><span>&lt;/<span class="end-tag">span</span>&gt;</span><span>
</span></span><span id="line644"><span>        </span><span>&lt;/<span class="end-tag">button</span>&gt;</span><span>
</span></span><span id="line645"><span>        </span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">lang-menu</a>" <span class="attribute-name">id</span>="<a class="attribute-value">langMenu</a>"&gt;</span><span>
</span></span><span id="line646"><span>          </span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">lang-item</a>" <span class="attribute-name">onclick</span>="<a class="attribute-value">setLang('it')</a>"&gt;</span><span></span><span>&lt;<span class="start-tag">span</span> <span class="attribute-name">class</span>="<a class="attribute-value">lang-flag</a>"&gt;</span><span>🇮🇹</span><span>&lt;/<span class="end-tag">span</span>&gt;</span><span> Italiano</span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span>
</span></span><span id="line647"><span>          </span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">lang-item</a>" <span class="attribute-name">onclick</span>="<a class="attribute-value">setLang('en')</a>"&gt;</span><span></span><span>&lt;<span class="start-tag">span</span> <span class="attribute-name">class</span>="<a class="attribute-value">lang-flag</a>"&gt;</span><span>🇬🇧</span><span>&lt;/<span class="end-tag">span</span>&gt;</span><span> English</span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span>
</span></span><span id="line648"><span>          </span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">lang-item</a>" <span class="attribute-name">onclick</span>="<a class="attribute-value">setLang('de')</a>"&gt;</span><span></span><span>&lt;<span class="start-tag">span</span> <span class="attribute-name">class</span>="<a class="attribute-value">lang-flag</a>"&gt;</span><span>🇩🇪</span><span>&lt;/<span class="end-tag">span</span>&gt;</span><span> Deutsch</span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span>
</span></span><span id="line649"><span>          </span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">lang-item</a>" <span class="attribute-name">onclick</span>="<a class="attribute-value">setLang('fr')</a>"&gt;</span><span></span><span>&lt;<span class="start-tag">span</span> <span class="attribute-name">class</span>="<a class="attribute-value">lang-flag</a>"&gt;</span><span>🇫🇷</span><span>&lt;/<span class="end-tag">span</span>&gt;</span><span> Français</span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span>
</span></span><span id="line650"><span>          </span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">lang-item</a>" <span class="attribute-name">onclick</span>="<a class="attribute-value">setLang('es')</a>"&gt;</span><span></span><span>&lt;<span class="start-tag">span</span> <span class="attribute-name">class</span>="<a class="attribute-value">lang-flag</a>"&gt;</span><span>🇪🇸</span><span>&lt;/<span class="end-tag">span</span>&gt;</span><span> Español</span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span>
</span></span><span id="line651"><span>          </span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">lang-item</a>" <span class="attribute-name">onclick</span>="<a class="attribute-value">setLang('zh')</a>"&gt;</span><span></span><span>&lt;<span class="start-tag">span</span> <span class="attribute-name">class</span>="<a class="attribute-value">lang-flag</a>"&gt;</span><span>🇨🇳</span><span>&lt;/<span class="end-tag">span</span>&gt;</span><span> 中文</span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span>
</span></span><span id="line652"><span>          </span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">lang-item</a>" <span class="attribute-name">onclick</span>="<a class="attribute-value">setLang('ru')</a>"&gt;</span><span></span><span>&lt;<span class="start-tag">span</span> <span class="attribute-name">class</span>="<a class="attribute-value">lang-flag</a>"&gt;</span><span>🇷🇺</span><span>&lt;/<span class="end-tag">span</span>&gt;</span><span> Русский</span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span>
</span></span><span id="line653"><span>        </span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span>
</span></span><span id="line654"><span>      </span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span>
</span></span><span id="line655"><span>    </span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span>
</span></span><span id="line656"><span>  </span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span>
</span></span><span id="line657"><span>
</span></span><span id="line658"><span>  </span><span class="comment">&lt;!-- HTTP (no secure context) alert --&gt;</span><span>
</span></span><span id="line659"><span>  </span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">alert alert-error hidden</a>" <span class="attribute-name">id</span>="<a class="attribute-value">httpAlert</a>"&gt;</span><span>
</span></span><span id="line660"><span>    </span><span>&lt;<span class="start-tag">svg</span> <span class="attribute-name">viewBox</span>="<a class="attribute-value">0 0 24 24</a>" <span class="attribute-name">fill</span>="<a class="attribute-value">none</a>" <span class="attribute-name">stroke</span>="<a class="attribute-value">currentColor</a>" <span class="attribute-name">stroke-width</span>="<a class="attribute-value">2</a>" <span class="attribute-name">style</span>="<a class="attribute-value">flex-shrink:0;margin-top:2px</a>"&gt;</span><span></span><span>&lt;<span class="start-tag">path</span> <span class="attribute-name">d</span>="<a class="attribute-value">M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z</a>"<span>/</span>&gt;</span><span></span><span>&lt;<span class="start-tag">line</span> <span class="attribute-name">x1</span>="<a class="attribute-value">12</a>" <span class="attribute-name">y1</span>="<a class="attribute-value">8</a>" <span class="attribute-name">x2</span>="<a class="attribute-value">12</a>" <span class="attribute-name">y2</span>="<a class="attribute-value">12</a>"<span>/</span>&gt;</span><span></span><span>&lt;<span class="start-tag">line</span> <span class="attribute-name">x1</span>="<a class="attribute-value">12</a>" <span class="attribute-name">y1</span>="<a class="attribute-value">16</a>" <span class="attribute-name">x2</span>="<a class="attribute-value">12.01</a>" <span class="attribute-name">y2</span>="<a class="attribute-value">16</a>"<span>/</span>&gt;</span><span></span><span>&lt;/<span class="end-tag">svg</span>&gt;</span><span>
</span></span><span id="line661"><span>    </span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">alert-body</a>"&gt;</span><span>
</span></span><span id="line662"><span>      </span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">alert-title</a>" <span class="attribute-name">data-i18n</span>="<a class="attribute-value">httpTitle</a>"&gt;</span><span></span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span>
</span></span><span id="line663"><span>      </span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">alert-desc</a>" <span class="attribute-name">id</span>="<a class="attribute-value">httpDesc</a>"&gt;</span><span></span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span>
</span></span><span id="line664"><span>    </span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span>
</span></span><span id="line665"><span>  </span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span>
</span></span><span id="line666"><span>
</span></span><span id="line667"><span>  </span><span class="comment">&lt;!-- Browser doesn't support Web Bluetooth at all --&gt;</span><span>
</span></span><span id="line668"><span>  </span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">alert alert-warn hidden</a>" <span class="attribute-name">id</span>="<a class="attribute-value">noBleAlert</a>"&gt;</span><span>
</span></span><span id="line669"><span>    </span><span>&lt;<span class="start-tag">svg</span> <span class="attribute-name">viewBox</span>="<a class="attribute-value">0 0 24 24</a>" <span class="attribute-name">fill</span>="<a class="attribute-value">none</a>" <span class="attribute-name">stroke</span>="<a class="attribute-value">currentColor</a>" <span class="attribute-name">stroke-width</span>="<a class="attribute-value">2</a>"&gt;</span><span></span><span>&lt;<span class="start-tag">circle</span> <span class="attribute-name">cx</span>="<a class="attribute-value">12</a>" <span class="attribute-name">cy</span>="<a class="attribute-value">12</a>" <span class="attribute-name">r</span>="<a class="attribute-value">10</a>"<span>/</span>&gt;</span><span></span><span>&lt;<span class="start-tag">line</span> <span class="attribute-name">x1</span>="<a class="attribute-value">12</a>" <span class="attribute-name">y1</span>="<a class="attribute-value">8</a>" <span class="attribute-name">x2</span>="<a class="attribute-value">12</a>" <span class="attribute-name">y2</span>="<a class="attribute-value">12</a>"<span>/</span>&gt;</span><span></span><span>&lt;<span class="start-tag">line</span> <span class="attribute-name">x1</span>="<a class="attribute-value">12</a>" <span class="attribute-name">y1</span>="<a class="attribute-value">16</a>" <span class="attribute-name">x2</span>="<a class="attribute-value">12.01</a>" <span class="attribute-name">y2</span>="<a class="attribute-value">16</a>"<span>/</span>&gt;</span><span></span><span>&lt;/<span class="end-tag">svg</span>&gt;</span><span>
</span></span><span id="line670"><span>    </span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">alert-body</a>"&gt;</span><span>
</span></span><span id="line671"><span>      </span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">alert-title</a>" <span class="attribute-name">data-i18n</span>="<a class="attribute-value">noBTTitle</a>"&gt;</span><span></span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span>
</span></span><span id="line672"><span>      </span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">alert-desc</a>" <span class="attribute-name">data-i18n</span>="<a class="attribute-value">noBTDesc</a>"&gt;</span><span></span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span>
</span></span><span id="line673"><span>    </span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span>
</span></span><span id="line674"><span>  </span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span>
</span></span><span id="line675"><span>
</span></span><span id="line676"><span>  </span><span class="comment">&lt;!-- Status --&gt;</span><span>
</span></span><span id="line677"><span>  </span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">status-pill</a>"&gt;</span><span>
</span></span><span id="line678"><span>    </span><span>&lt;<span class="start-tag">span</span> <span class="attribute-name">class</span>="<a class="attribute-value">dot</a>" <span class="attribute-name">id</span>="<a class="attribute-value">dot</a>"&gt;</span><span></span><span>&lt;/<span class="end-tag">span</span>&gt;</span><span>
</span></span><span id="line679"><span>    </span><span>&lt;<span class="start-tag">span</span> <span class="attribute-name">class</span>="<a class="attribute-value">status-text</a>" <span class="attribute-name">id</span>="<a class="attribute-value">stText</a>"&gt;</span><span></span><span>&lt;/<span class="end-tag">span</span>&gt;</span><span>
</span></span><span id="line680"><span>    </span><span>&lt;<span class="start-tag">span</span> <span class="attribute-name">class</span>="<a class="attribute-value">status-time</a>" <span class="attribute-name">id</span>="<a class="attribute-value">stTime</a>"&gt;</span><span></span><span>&lt;/<span class="end-tag">span</span>&gt;</span><span>
</span></span><span id="line681"><span>  </span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span>
</span></span><span id="line682"><span>
</span></span><span id="line683"><span>  </span><span class="comment">&lt;!-- Responsive two-column grid --&gt;</span><span>
</span></span><span id="line684"><span>  </span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">layout</a>"&gt;</span><span>
</span></span><span id="line685"><span>
</span></span><span id="line686"><span>    </span><span class="comment">&lt;!-- LEFT: Device + OTA --&gt;</span><span>
</span></span><span id="line687"><span>    </span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">col-left</a>" <span class="attribute-name">id</span>="<a class="attribute-value">colLeft</a>"&gt;</span><span>
</span></span><span id="line688"><span>
</span></span><span id="line689"><span>      </span><span class="comment">&lt;!-- Device card --&gt;</span><span>
</span></span><span id="line690"><span>      </span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">card</a>"&gt;</span><span>
</span></span><span id="line691"><span>        </span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">card-label</a>"&gt;</span><span>
</span></span><span id="line692"><span>          </span><span>&lt;<span class="start-tag">svg</span> <span class="attribute-name">viewBox</span>="<a class="attribute-value">0 0 24 24</a>" <span class="attribute-name">fill</span>="<a class="attribute-value">none</a>" <span class="attribute-name">stroke</span>="<a class="attribute-value">currentColor</a>" <span class="attribute-name">stroke-width</span>="<a class="attribute-value">2</a>"&gt;</span><span></span><span>&lt;<span class="start-tag">path</span> <span class="attribute-name">d</span>="<a class="attribute-value">M12 2L8.5 5.5 12 9l3.5-3.5L12 2z</a>"<span>/</span>&gt;</span><span></span><span>&lt;<span class="start-tag">path</span> <span class="attribute-name">d</span>="<a class="attribute-value">M12 15l-3.5 3.5L12 22l3.5-3.5L12 15z</a>"<span>/</span>&gt;</span><span></span><span>&lt;<span class="start-tag">path</span> <span class="attribute-name">d</span>="<a class="attribute-value">M12 9v6</a>"<span>/</span>&gt;</span><span></span><span>&lt;/<span class="end-tag">svg</span>&gt;</span><span>
</span></span><span id="line693"><span>          </span><span>&lt;<span class="start-tag">span</span> <span class="attribute-name">data-i18n</span>="<a class="attribute-value">deviceLabel</a>"&gt;</span><span></span><span>&lt;/<span class="end-tag">span</span>&gt;</span><span>
</span></span><span id="line694"><span>        </span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span>
</span></span><span id="line695"><span>        </span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">dev-grid hidden</a>" <span class="attribute-name">id</span>="<a class="attribute-value">devGrid</a>"&gt;</span><span>
</span></span><span id="line696"><span>          </span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">dev-cell</a>"&gt;</span><span></span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">dev-cell-label</a>" <span class="attribute-name">data-i18n</span>="<a class="attribute-value">devName</a>"&gt;</span><span></span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span></span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">dev-cell-value name</a>" <span class="attribute-name">id</span>="<a class="attribute-value">dName</a>"&gt;</span><span>—</span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span></span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span>
</span></span><span id="line697"><span>          </span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">dev-cell</a>"&gt;</span><span></span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">dev-cell-label</a>" <span class="attribute-name">data-i18n</span>="<a class="attribute-value">devModel</a>"&gt;</span><span></span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span></span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">dev-cell-value</a>" <span class="attribute-name">id</span>="<a class="attribute-value">dModel</a>"&gt;</span><span>—</span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span></span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span>
</span></span><span id="line698"><span>          </span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">dev-cell</a>"&gt;</span><span></span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">dev-cell-label</a>" <span class="attribute-name">data-i18n</span>="<a class="attribute-value">devFW</a>"&gt;</span><span></span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span></span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">dev-cell-value</a>" <span class="attribute-name">id</span>="<a class="attribute-value">dFW</a>"&gt;</span><span>—</span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span></span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span>
</span></span><span id="line699"><span>          </span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">dev-cell</a>"&gt;</span><span></span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">dev-cell-label</a>" <span class="attribute-name">data-i18n</span>="<a class="attribute-value">devHW</a>"&gt;</span><span></span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span></span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">dev-cell-value</a>" <span class="attribute-name">id</span>="<a class="attribute-value">dHW</a>"&gt;</span><span>—</span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span></span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span>
</span></span><span id="line700"><span>          </span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">dev-cell</a>"&gt;</span><span></span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">dev-cell-label</a>" <span class="attribute-name">data-i18n</span>="<a class="attribute-value">devMfr</a>"&gt;</span><span></span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span></span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">dev-cell-value</a>" <span class="attribute-name">id</span>="<a class="attribute-value">dMfr</a>"&gt;</span><span>—</span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span></span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span>
</span></span><span id="line701"><span>          </span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">dev-cell</a>"&gt;</span><span></span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">dev-cell-label</a>" <span class="attribute-name">data-i18n</span>="<a class="attribute-value">devSerial</a>"&gt;</span><span></span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span></span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">dev-cell-value</a>" <span class="attribute-name">id</span>="<a class="attribute-value">dSerial</a>"&gt;</span><span>—</span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span></span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span>
</span></span><span id="line702"><span>        </span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span>
</span></span><span id="line703"><span>        </span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">btn-row</a>"&gt;</span><span>
</span></span><span id="line704"><span>          </span><span>&lt;<span class="start-tag">button</span> <span class="attribute-name">class</span>="<a class="attribute-value">btn btn-primary</a>" <span class="attribute-name">id</span>="<a class="attribute-value">btnConnect</a>" <span class="attribute-name">onclick</span>="<a class="attribute-value">connectBLE()</a>"&gt;</span><span>
</span></span><span id="line705"><span>            </span><span>&lt;<span class="start-tag">svg</span> <span class="attribute-name">viewBox</span>="<a class="attribute-value">0 0 24 24</a>" <span class="attribute-name">fill</span>="<a class="attribute-value">none</a>" <span class="attribute-name">stroke</span>="<a class="attribute-value">currentColor</a>" <span class="attribute-name">stroke-width</span>="<a class="attribute-value">2</a>"&gt;</span><span></span><span>&lt;<span class="start-tag">path</span> <span class="attribute-name">d</span>="<a class="attribute-value">M12 2L8.5 5.5 12 9l3.5-3.5L12 2z</a>"<span>/</span>&gt;</span><span></span><span>&lt;<span class="start-tag">path</span> <span class="attribute-name">d</span>="<a class="attribute-value">M12 15l-3.5 3.5L12 22l3.5-3.5L12 15z</a>"<span>/</span>&gt;</span><span></span><span>&lt;<span class="start-tag">path</span> <span class="attribute-name">d</span>="<a class="attribute-value">M12 9v6</a>"<span>/</span>&gt;</span><span></span><span>&lt;/<span class="end-tag">svg</span>&gt;</span><span>
</span></span><span id="line706"><span>            </span><span>&lt;<span class="start-tag">span</span> <span class="attribute-name">data-i18n</span>="<a class="attribute-value">connect</a>"&gt;</span><span></span><span>&lt;/<span class="end-tag">span</span>&gt;</span><span>
</span></span><span id="line707"><span>          </span><span>&lt;/<span class="end-tag">button</span>&gt;</span><span>
</span></span><span id="line708"><span>          </span><span>&lt;<span class="start-tag">button</span> <span class="attribute-name">class</span>="<a class="attribute-value">btn btn-danger hidden</a>" <span class="attribute-name">id</span>="<a class="attribute-value">btnDisconnect</a>" <span class="attribute-name">onclick</span>="<a class="attribute-value">disconnectBLE()</a>"&gt;</span><span>
</span></span><span id="line709"><span>            </span><span>&lt;<span class="start-tag">svg</span> <span class="attribute-name">viewBox</span>="<a class="attribute-value">0 0 24 24</a>" <span class="attribute-name">fill</span>="<a class="attribute-value">none</a>" <span class="attribute-name">stroke</span>="<a class="attribute-value">currentColor</a>" <span class="attribute-name">stroke-width</span>="<a class="attribute-value">2</a>"&gt;</span><span></span><span>&lt;<span class="start-tag">line</span> <span class="attribute-name">x1</span>="<a class="attribute-value">18</a>" <span class="attribute-name">y1</span>="<a class="attribute-value">6</a>" <span class="attribute-name">x2</span>="<a class="attribute-value">6</a>" <span class="attribute-name">y2</span>="<a class="attribute-value">18</a>"<span>/</span>&gt;</span><span></span><span>&lt;<span class="start-tag">line</span> <span class="attribute-name">x1</span>="<a class="attribute-value">6</a>" <span class="attribute-name">y1</span>="<a class="attribute-value">6</a>" <span class="attribute-name">x2</span>="<a class="attribute-value">18</a>" <span class="attribute-name">y2</span>="<a class="attribute-value">18</a>"<span>/</span>&gt;</span><span></span><span>&lt;/<span class="end-tag">svg</span>&gt;</span><span>
</span></span><span id="line710"><span>            </span><span>&lt;<span class="start-tag">span</span> <span class="attribute-name">data-i18n</span>="<a class="attribute-value">disconnect</a>"&gt;</span><span></span><span>&lt;/<span class="end-tag">span</span>&gt;</span><span>
</span></span><span id="line711"><span>          </span><span>&lt;/<span class="end-tag">button</span>&gt;</span><span>
</span></span><span id="line712"><span>        </span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span>
</span></span><span id="line713"><span>      </span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span>
</span></span><span id="line714"><span>
</span></span><span id="line715"><span>      </span><span class="comment">&lt;!-- OTA card --&gt;</span><span>
</span></span><span id="line716"><span>      </span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">card</a>"&gt;</span><span>
</span></span><span id="line717"><span>        </span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">card-label</a>"&gt;</span><span>
</span></span><span id="line718"><span>          </span><span>&lt;<span class="start-tag">svg</span> <span class="attribute-name">viewBox</span>="<a class="attribute-value">0 0 24 24</a>" <span class="attribute-name">fill</span>="<a class="attribute-value">none</a>" <span class="attribute-name">stroke</span>="<a class="attribute-value">currentColor</a>" <span class="attribute-name">stroke-width</span>="<a class="attribute-value">2</a>"&gt;</span><span></span><span>&lt;<span class="start-tag">polyline</span> <span class="attribute-name">points</span>="<a class="attribute-value">16 16 12 12 8 16</a>"<span>/</span>&gt;</span><span></span><span>&lt;<span class="start-tag">line</span> <span class="attribute-name">x1</span>="<a class="attribute-value">12</a>" <span class="attribute-name">y1</span>="<a class="attribute-value">12</a>" <span class="attribute-name">x2</span>="<a class="attribute-value">12</a>" <span class="attribute-name">y2</span>="<a class="attribute-value">21</a>"<span>/</span>&gt;</span><span></span><span>&lt;<span class="start-tag">path</span> <span class="attribute-name">d</span>="<a class="attribute-value">M20.39 18.39A5 5 0 0 0 18 9h-1.26A8 8 0 1 0 3 16.3</a>"<span>/</span>&gt;</span><span></span><span>&lt;/<span class="end-tag">svg</span>&gt;</span><span>
</span></span><span id="line719"><span>          </span><span>&lt;<span class="start-tag">span</span> <span class="attribute-name">data-i18n</span>="<a class="attribute-value">otaLabel</a>"&gt;</span><span></span><span>&lt;/<span class="end-tag">span</span>&gt;</span><span>
</span></span><span id="line720"><span>        </span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span>
</span></span><span id="line721"><span>        </span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">seg</a>"&gt;</span><span>
</span></span><span id="line722"><span>          </span><span>&lt;<span class="start-tag">button</span> <span class="attribute-name">class</span>="<a class="attribute-value">seg-btn active</a>" <span class="attribute-name">id</span>="<a class="attribute-value">btnFlash</a>" <span class="attribute-name">onclick</span>="<a class="attribute-value">setOtaType('flash')</a>"&gt;</span><span>
</span></span><span id="line723"><span>            </span><span>&lt;<span class="start-tag">svg</span> <span class="attribute-name">viewBox</span>="<a class="attribute-value">0 0 24 24</a>" <span class="attribute-name">fill</span>="<a class="attribute-value">none</a>" <span class="attribute-name">stroke</span>="<a class="attribute-value">currentColor</a>" <span class="attribute-name">stroke-width</span>="<a class="attribute-value">2</a>"&gt;</span><span></span><span>&lt;<span class="start-tag">rect</span> <span class="attribute-name">x</span>="<a class="attribute-value">2</a>" <span class="attribute-name">y</span>="<a class="attribute-value">3</a>" <span class="attribute-name">width</span>="<a class="attribute-value">20</a>" <span class="attribute-name">height</span>="<a class="attribute-value">14</a>" <span class="attribute-name">rx</span>="<a class="attribute-value">2</a>"<span>/</span>&gt;</span><span></span><span>&lt;<span class="start-tag">line</span> <span class="attribute-name">x1</span>="<a class="attribute-value">12</a>" <span class="attribute-name">y1</span>="<a class="attribute-value">17</a>" <span class="attribute-name">x2</span>="<a class="attribute-value">12</a>" <span class="attribute-name">y2</span>="<a class="attribute-value">21</a>"<span>/</span>&gt;</span><span></span><span>&lt;<span class="start-tag">line</span> <span class="attribute-name">x1</span>="<a class="attribute-value">8</a>" <span class="attribute-name">y1</span>="<a class="attribute-value">21</a>" <span class="attribute-name">x2</span>="<a class="attribute-value">16</a>" <span class="attribute-name">y2</span>="<a class="attribute-value">21</a>"<span>/</span>&gt;</span><span></span><span>&lt;/<span class="end-tag">svg</span>&gt;</span><span>
</span></span><span id="line724"><span>            </span><span>&lt;<span class="start-tag">span</span> <span class="attribute-name">data-i18n</span>="<a class="attribute-value">otaFlash</a>"&gt;</span><span></span><span>&lt;/<span class="end-tag">span</span>&gt;</span><span>
</span></span><span id="line725"><span>          </span><span>&lt;/<span class="end-tag">button</span>&gt;</span><span>
</span></span><span id="line726"><span>          </span><span>&lt;<span class="start-tag">button</span> <span class="attribute-name">class</span>="<a class="attribute-value">seg-btn</a>" <span class="attribute-name">id</span>="<a class="attribute-value">btnSpiffs</a>" <span class="attribute-name">onclick</span>="<a class="attribute-value">setOtaType('spiffs')</a>"&gt;</span><span>
</span></span><span id="line727"><span>            </span><span>&lt;<span class="start-tag">svg</span> <span class="attribute-name">viewBox</span>="<a class="attribute-value">0 0 24 24</a>" <span class="attribute-name">fill</span>="<a class="attribute-value">none</a>" <span class="attribute-name">stroke</span>="<a class="attribute-value">currentColor</a>" <span class="attribute-name">stroke-width</span>="<a class="attribute-value">2</a>"&gt;</span><span></span><span>&lt;<span class="start-tag">path</span> <span class="attribute-name">d</span>="<a class="attribute-value">M22 19a2 2 0 0 1-2 2H4a2 2 0 0 1-2-2V5a2 2 0 0 1 2-2h5l2 3h9a2 2 0 0 1 2 2z</a>"<span>/</span>&gt;</span><span></span><span>&lt;/<span class="end-tag">svg</span>&gt;</span><span>
</span></span><span id="line728"><span>            </span><span>&lt;<span class="start-tag">span</span> <span class="attribute-name">data-i18n</span>="<a class="attribute-value">otaSpiffs</a>"&gt;</span><span></span><span>&lt;/<span class="end-tag">span</span>&gt;</span><span>
</span></span><span id="line729"><span>          </span><span>&lt;/<span class="end-tag">button</span>&gt;</span><span>
</span></span><span id="line730"><span>        </span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span>
</span></span><span id="line731"><span>
</span></span><span id="line732"><span>        </span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">dropzone</a>" <span class="attribute-name">id</span>="<a class="attribute-value">dropzone</a>"&gt;</span><span>
</span></span><span id="line733"><span>          </span><span>&lt;<span class="start-tag">input</span> <span class="attribute-name">type</span>="<a class="attribute-value">file</a>" <span class="attribute-name">id</span>="<a class="attribute-value">fileInput</a>" <span class="attribute-name">accept</span>="<a class="attribute-value">.bin</a>" <span class="attribute-name">onchange</span>="<a class="attribute-value">onFilePick(event)</a>"&gt;</span><span>
</span></span><span id="line734"><span>          </span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">dz-icon</a>"&gt;</span><span></span><span>&lt;<span class="start-tag">svg</span> <span class="attribute-name">viewBox</span>="<a class="attribute-value">0 0 24 24</a>" <span class="attribute-name">fill</span>="<a class="attribute-value">none</a>" <span class="attribute-name">stroke</span>="<a class="attribute-value">currentColor</a>" <span class="attribute-name">stroke-width</span>="<a class="attribute-value">1.5</a>"&gt;</span><span></span><span>&lt;<span class="start-tag">polyline</span> <span class="attribute-name">points</span>="<a class="attribute-value">16 16 12 12 8 16</a>"<span>/</span>&gt;</span><span></span><span>&lt;<span class="start-tag">line</span> <span class="attribute-name">x1</span>="<a class="attribute-value">12</a>" <span class="attribute-name">y1</span>="<a class="attribute-value">12</a>" <span class="attribute-name">x2</span>="<a class="attribute-value">12</a>" <span class="attribute-name">y2</span>="<a class="attribute-value">21</a>"<span>/</span>&gt;</span><span></span><span>&lt;<span class="start-tag">path</span> <span class="attribute-name">d</span>="<a class="attribute-value">M20.39 18.39A5 5 0 0 0 18 9h-1.26A8 8 0 1 0 3 16.3</a>"<span>/</span>&gt;</span><span></span><span>&lt;/<span class="end-tag">svg</span>&gt;</span><span></span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span>
</span></span><span id="line735"><span>          </span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">dz-title</a>" <span class="attribute-name">data-i18n</span>="<a class="attribute-value">dropTitle</a>"&gt;</span><span></span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span>
</span></span><span id="line736"><span>          </span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">dz-sub</a>"   <span class="attribute-name">data-i18n</span>="<a class="attribute-value">dropSub</a>"&gt;</span><span></span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span>
</span></span><span id="line737"><span>        </span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span>
</span></span><span id="line738"><span>
</span></span><span id="line739"><span>        </span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">file-badge hidden</a>" <span class="attribute-name">id</span>="<a class="attribute-value">fileBadge</a>"&gt;</span><span>
</span></span><span id="line740"><span>          </span><span>&lt;<span class="start-tag">svg</span> <span class="attribute-name">viewBox</span>="<a class="attribute-value">0 0 24 24</a>" <span class="attribute-name">fill</span>="<a class="attribute-value">none</a>" <span class="attribute-name">stroke</span>="<a class="attribute-value">currentColor</a>" <span class="attribute-name">stroke-width</span>="<a class="attribute-value">2</a>"&gt;</span><span></span><span>&lt;<span class="start-tag">polyline</span> <span class="attribute-name">points</span>="<a class="attribute-value">20 6 9 17 4 12</a>"<span>/</span>&gt;</span><span></span><span>&lt;/<span class="end-tag">svg</span>&gt;</span><span>
</span></span><span id="line741"><span>          </span><span>&lt;<span class="start-tag">span</span> <span class="attribute-name">class</span>="<a class="attribute-value">file-badge-name</a>" <span class="attribute-name">id</span>="<a class="attribute-value">fileName</a>"&gt;</span><span>—</span><span>&lt;/<span class="end-tag">span</span>&gt;</span><span>
</span></span><span id="line742"><span>          </span><span>&lt;<span class="start-tag">span</span> <span class="attribute-name">class</span>="<a class="attribute-value">file-badge-size</a>" <span class="attribute-name">id</span>="<a class="attribute-value">fileSize</a>"&gt;</span><span>—</span><span>&lt;/<span class="end-tag">span</span>&gt;</span><span>
</span></span><span id="line743"><span>        </span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span>
</span></span><span id="line744"><span>
</span></span><span id="line745"><span>        </span><span>&lt;<span class="start-tag">hr</span>&gt;</span><span>
</span></span><span id="line746"><span>
</span></span><span id="line747"><span>        </span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">id</span>="<a class="attribute-value">progSection</a>" <span class="attribute-name">class</span>="<a class="attribute-value">hidden</a>"&gt;</span><span>
</span></span><span id="line748"><span>          </span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">prog-header</a>"&gt;</span><span>
</span></span><span id="line749"><span>            </span><span>&lt;<span class="start-tag">span</span> <span class="attribute-name">class</span>="<a class="attribute-value">prog-label</a>" <span class="attribute-name">id</span>="<a class="attribute-value">progLabel</a>"&gt;</span><span></span><span>&lt;/<span class="end-tag">span</span>&gt;</span><span>
</span></span><span id="line750"><span>            </span><span>&lt;<span class="start-tag">span</span> <span class="attribute-name">class</span>="<a class="attribute-value">prog-pct</a>"   <span class="attribute-name">id</span>="<a class="attribute-value">progPct</a>"&gt;</span><span>0%</span><span>&lt;/<span class="end-tag">span</span>&gt;</span><span>
</span></span><span id="line751"><span>          </span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span>
</span></span><span id="line752"><span>          </span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">prog-track</a>"&gt;</span><span></span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">prog-fill</a>" <span class="attribute-name">id</span>="<a class="attribute-value">progFill</a>" <span class="attribute-name">style</span>="<a class="attribute-value">width:0%</a>"&gt;</span><span></span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span></span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span>
</span></span><span id="line753"><span>          </span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">prog-stats</a>"&gt;</span><span>
</span></span><span id="line754"><span>            </span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">stat</a>"&gt;</span><span></span><span>&lt;<span class="start-tag">span</span> <span class="attribute-name">class</span>="<a class="attribute-value">stat-k</a>" <span class="attribute-name">data-i18n</span>="<a class="attribute-value">statSent</a>"&gt;</span><span></span><span>&lt;/<span class="end-tag">span</span>&gt;</span><span></span><span>&lt;<span class="start-tag">span</span> <span class="attribute-name">class</span>="<a class="attribute-value">stat-v</a>" <span class="attribute-name">id</span>="<a class="attribute-value">sSent</a>"&gt;</span><span>0 B</span><span>&lt;/<span class="end-tag">span</span>&gt;</span><span></span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span>
</span></span><span id="line755"><span>            </span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">stat</a>"&gt;</span><span></span><span>&lt;<span class="start-tag">span</span> <span class="attribute-name">class</span>="<a class="attribute-value">stat-k</a>" <span class="attribute-name">data-i18n</span>="<a class="attribute-value">statTotal</a>"&gt;</span><span></span><span>&lt;/<span class="end-tag">span</span>&gt;</span><span></span><span>&lt;<span class="start-tag">span</span> <span class="attribute-name">class</span>="<a class="attribute-value">stat-v</a>" <span class="attribute-name">id</span>="<a class="attribute-value">sTotal</a>"&gt;</span><span>0 B</span><span>&lt;/<span class="end-tag">span</span>&gt;</span><span></span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span>
</span></span><span id="line756"><span>            </span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">stat</a>"&gt;</span><span></span><span>&lt;<span class="start-tag">span</span> <span class="attribute-name">class</span>="<a class="attribute-value">stat-k</a>" <span class="attribute-name">data-i18n</span>="<a class="attribute-value">statSector</a>"&gt;</span><span></span><span>&lt;/<span class="end-tag">span</span>&gt;</span><span></span><span>&lt;<span class="start-tag">span</span> <span class="attribute-name">class</span>="<a class="attribute-value">stat-v</a>" <span class="attribute-name">id</span>="<a class="attribute-value">sSector</a>"&gt;</span><span>0</span><span>&lt;/<span class="end-tag">span</span>&gt;</span><span></span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span>
</span></span><span id="line757"><span>            </span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">stat</a>"&gt;</span><span></span><span>&lt;<span class="start-tag">span</span> <span class="attribute-name">class</span>="<a class="attribute-value">stat-k</a>" <span class="attribute-name">data-i18n</span>="<a class="attribute-value">statSpeed</a>"&gt;</span><span></span><span>&lt;/<span class="end-tag">span</span>&gt;</span><span></span><span>&lt;<span class="start-tag">span</span> <span class="attribute-name">class</span>="<a class="attribute-value">stat-v</a>" <span class="attribute-name">id</span>="<a class="attribute-value">sSpeed</a>"&gt;</span><span>—</span><span>&lt;/<span class="end-tag">span</span>&gt;</span><span></span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span>
</span></span><span id="line758"><span>            </span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">stat</a>"&gt;</span><span></span><span>&lt;<span class="start-tag">span</span> <span class="attribute-name">class</span>="<a class="attribute-value">stat-k</a>" <span class="attribute-name">data-i18n</span>="<a class="attribute-value">statETA</a>"&gt;</span><span></span><span>&lt;/<span class="end-tag">span</span>&gt;</span><span></span><span>&lt;<span class="start-tag">span</span> <span class="attribute-name">class</span>="<a class="attribute-value">stat-v</a>" <span class="attribute-name">id</span>="<a class="attribute-value">sETA</a>"&gt;</span><span>—</span><span>&lt;/<span class="end-tag">span</span>&gt;</span><span></span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span>
</span></span><span id="line759"><span>          </span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span>
</span></span><span id="line760"><span>        </span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span>
</span></span><span id="line761"><span>
</span></span><span id="line762"><span>        </span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">success-box</a>" <span class="attribute-name">id</span>="<a class="attribute-value">successBox</a>"&gt;</span><span>
</span></span><span id="line763"><span>          </span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">success-ring</a>"&gt;</span><span></span><span>&lt;<span class="start-tag">svg</span> <span class="attribute-name">viewBox</span>="<a class="attribute-value">0 0 24 24</a>" <span class="attribute-name">fill</span>="<a class="attribute-value">none</a>" <span class="attribute-name">stroke</span>="<a class="attribute-value">currentColor</a>" <span class="attribute-name">stroke-width</span>="<a class="attribute-value">2.5</a>"&gt;</span><span></span><span>&lt;<span class="start-tag">polyline</span> <span class="attribute-name">points</span>="<a class="attribute-value">20 6 9 17 4 12</a>"<span>/</span>&gt;</span><span></span><span>&lt;/<span class="end-tag">svg</span>&gt;</span><span></span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span>
</span></span><span id="line764"><span>          </span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">success-title</a>" <span class="attribute-name">data-i18n</span>="<a class="attribute-value">successTitle</a>"&gt;</span><span></span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span>
</span></span><span id="line765"><span>          </span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">success-sub</a>"   <span class="attribute-name">data-i18n</span>="<a class="attribute-value">successSub</a>"&gt;</span><span></span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span>
</span></span><span id="line766"><span>        </span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span>
</span></span><span id="line767"><span>
</span></span><span id="line768"><span>        </span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">btn-row</a>" <span class="attribute-name">style</span>="<a class="attribute-value">margin-top:4px</a>"&gt;</span><span>
</span></span><span id="line769"><span>          </span><span>&lt;<span class="start-tag">button</span> <span class="attribute-name">class</span>="<a class="attribute-value">btn btn-primary</a>" <span class="attribute-name">id</span>="<a class="attribute-value">btnStart</a>" <span class="attribute-name">onclick</span>="<a class="attribute-value">startOTA()</a>" <span class="attribute-name">disabled</span>&gt;</span><span>
</span></span><span id="line770"><span>            </span><span>&lt;<span class="start-tag">svg</span> <span class="attribute-name">viewBox</span>="<a class="attribute-value">0 0 24 24</a>" <span class="attribute-name">fill</span>="<a class="attribute-value">none</a>" <span class="attribute-name">stroke</span>="<a class="attribute-value">currentColor</a>" <span class="attribute-name">stroke-width</span>="<a class="attribute-value">2</a>"&gt;</span><span></span><span>&lt;<span class="start-tag">polygon</span> <span class="attribute-name">points</span>="<a class="attribute-value">5 3 19 12 5 21 5 3</a>"<span>/</span>&gt;</span><span></span><span>&lt;/<span class="end-tag">svg</span>&gt;</span><span>
</span></span><span id="line771"><span>            </span><span>&lt;<span class="start-tag">span</span> <span class="attribute-name">data-i18n</span>="<a class="attribute-value">startOTA</a>"&gt;</span><span></span><span>&lt;/<span class="end-tag">span</span>&gt;</span><span>
</span></span><span id="line772"><span>          </span><span>&lt;/<span class="end-tag">button</span>&gt;</span><span>
</span></span><span id="line773"><span>          </span><span>&lt;<span class="start-tag">button</span> <span class="attribute-name">class</span>="<a class="attribute-value">btn btn-danger hidden</a>" <span class="attribute-name">id</span>="<a class="attribute-value">btnAbort</a>" <span class="attribute-name">onclick</span>="<a class="attribute-value">abortOTA()</a>"&gt;</span><span>
</span></span><span id="line774"><span>            </span><span>&lt;<span class="start-tag">svg</span> <span class="attribute-name">viewBox</span>="<a class="attribute-value">0 0 24 24</a>" <span class="attribute-name">fill</span>="<a class="attribute-value">none</a>" <span class="attribute-name">stroke</span>="<a class="attribute-value">currentColor</a>" <span class="attribute-name">stroke-width</span>="<a class="attribute-value">2</a>"&gt;</span><span></span><span>&lt;<span class="start-tag">rect</span> <span class="attribute-name">x</span>="<a class="attribute-value">3</a>" <span class="attribute-name">y</span>="<a class="attribute-value">3</a>" <span class="attribute-name">width</span>="<a class="attribute-value">18</a>" <span class="attribute-name">height</span>="<a class="attribute-value">18</a>" <span class="attribute-name">rx</span>="<a class="attribute-value">2</a>"<span>/</span>&gt;</span><span></span><span>&lt;/<span class="end-tag">svg</span>&gt;</span><span>
</span></span><span id="line775"><span>            </span><span>&lt;<span class="start-tag">span</span> <span class="attribute-name">data-i18n</span>="<a class="attribute-value">abort</a>"&gt;</span><span></span><span>&lt;/<span class="end-tag">span</span>&gt;</span><span>
</span></span><span id="line776"><span>          </span><span>&lt;/<span class="end-tag">button</span>&gt;</span><span>
</span></span><span id="line777"><span>        </span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span>
</span></span><span id="line778"><span>      </span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span>
</span></span><span id="line779"><span>
</span></span><span id="line780"><span>    </span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span></span><span class="comment">&lt;!-- /col-left --&gt;</span><span>
</span></span><span id="line781"><span>
</span></span><span id="line782"><span>    </span><span class="comment">&lt;!-- RIGHT: Log --&gt;</span><span>
</span></span><span id="line783"><span>    </span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">col-right</a>" <span class="attribute-name">id</span>="<a class="attribute-value">colRight</a>"&gt;</span><span>
</span></span><span id="line784"><span>      </span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">card</a>" <span class="attribute-name">id</span>="<a class="attribute-value">logCard</a>"&gt;</span><span>
</span></span><span id="line785"><span>        </span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">card-label</a>" <span class="attribute-name">style</span>="<a class="attribute-value">margin-bottom:10px</a>"&gt;</span><span>
</span></span><span id="line786"><span>          </span><span>&lt;<span class="start-tag">svg</span> <span class="attribute-name">viewBox</span>="<a class="attribute-value">0 0 24 24</a>" <span class="attribute-name">fill</span>="<a class="attribute-value">none</a>" <span class="attribute-name">stroke</span>="<a class="attribute-value">currentColor</a>" <span class="attribute-name">stroke-width</span>="<a class="attribute-value">2</a>"&gt;</span><span></span><span>&lt;<span class="start-tag">path</span> <span class="attribute-name">d</span>="<a class="attribute-value">M14 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V8z</a>"<span>/</span>&gt;</span><span></span><span>&lt;<span class="start-tag">polyline</span> <span class="attribute-name">points</span>="<a class="attribute-value">14 2 14 8 20 8</a>"<span>/</span>&gt;</span><span></span><span>&lt;<span class="start-tag">line</span> <span class="attribute-name">x1</span>="<a class="attribute-value">16</a>" <span class="attribute-name">y1</span>="<a class="attribute-value">13</a>" <span class="attribute-name">x2</span>="<a class="attribute-value">8</a>" <span class="attribute-name">y2</span>="<a class="attribute-value">13</a>"<span>/</span>&gt;</span><span></span><span>&lt;<span class="start-tag">line</span> <span class="attribute-name">x1</span>="<a class="attribute-value">16</a>" <span class="attribute-name">y1</span>="<a class="attribute-value">17</a>" <span class="attribute-name">x2</span>="<a class="attribute-value">8</a>" <span class="attribute-name">y2</span>="<a class="attribute-value">17</a>"<span>/</span>&gt;</span><span></span><span>&lt;/<span class="end-tag">svg</span>&gt;</span><span>
</span></span><span id="line787"><span>          </span><span>&lt;<span class="start-tag">span</span> <span class="attribute-name">data-i18n</span>="<a class="attribute-value">logLabel</a>"&gt;</span><span></span><span>&lt;/<span class="end-tag">span</span>&gt;</span><span>
</span></span><span id="line788"><span>          </span><span class="comment">&lt;!-- Enable/disable toggle --&gt;</span><span>
</span></span><span id="line789"><span>          </span><span>&lt;<span class="start-tag">button</span> <span class="attribute-name">class</span>="<a class="attribute-value">log-toggle-btn</a>" <span class="attribute-name">id</span>="<a class="attribute-value">logToggleBtn</a>" <span class="attribute-name">onclick</span>="<a class="attribute-value">toggleLog()</a>" <span class="attribute-name">title</span>="<a class="attribute-value"></a>"&gt;</span><span>
</span></span><span id="line790"><span>            </span><span>&lt;<span class="start-tag">span</span> <span class="attribute-name">class</span>="<a class="attribute-value">log-toggle-track</a>" <span class="attribute-name">id</span>="<a class="attribute-value">logToggleTrack</a>"&gt;</span><span>
</span></span><span id="line791"><span>              </span><span>&lt;<span class="start-tag">span</span> <span class="attribute-name">class</span>="<a class="attribute-value">log-toggle-thumb</a>" <span class="attribute-name">id</span>="<a class="attribute-value">logToggleThumb</a>"&gt;</span><span></span><span>&lt;/<span class="end-tag">span</span>&gt;</span><span>
</span></span><span id="line792"><span>            </span><span>&lt;/<span class="end-tag">span</span>&gt;</span><span>
</span></span><span id="line793"><span>            </span><span>&lt;<span class="start-tag">span</span> <span class="attribute-name">class</span>="<a class="attribute-value">log-toggle-label</a>" <span class="attribute-name">id</span>="<a class="attribute-value">logToggleLabel</a>" <span class="attribute-name">data-i18n</span>="<a class="attribute-value">logEnable</a>"&gt;</span><span></span><span>&lt;/<span class="end-tag">span</span>&gt;</span><span>
</span></span><span id="line794"><span>          </span><span>&lt;/<span class="end-tag">button</span>&gt;</span><span>
</span></span><span id="line795"><span>          </span><span>&lt;<span class="start-tag">button</span> <span class="attribute-name">class</span>="<a class="attribute-value">btn btn-ghost</a>" <span class="attribute-name">id</span>="<a class="attribute-value">logClearBtn</a>" <span class="attribute-name">style</span>="<a class="attribute-value">padding:3px 10px;font-size:11px</a>" <span class="attribute-name">onclick</span>="<a class="attribute-value">clearLog()</a>" <span class="attribute-name">data-i18n</span>="<a class="attribute-value">clearLog</a>"&gt;</span><span></span><span>&lt;/<span class="end-tag">button</span>&gt;</span><span>
</span></span><span id="line796"><span>        </span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span>
</span></span><span id="line797"><span>        </span><span class="comment">&lt;!-- Disabled overlay --&gt;</span><span>
</span></span><span id="line798"><span>        </span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">log-disabled</a>" <span class="attribute-name">id</span>="<a class="attribute-value">logDisabled</a>"&gt;</span><span>
</span></span><span id="line799"><span>          </span><span>&lt;<span class="start-tag">svg</span> <span class="attribute-name">viewBox</span>="<a class="attribute-value">0 0 24 24</a>" <span class="attribute-name">fill</span>="<a class="attribute-value">none</a>" <span class="attribute-name">stroke</span>="<a class="attribute-value">currentColor</a>" <span class="attribute-name">stroke-width</span>="<a class="attribute-value">1.5</a>"&gt;</span><span></span><span>&lt;<span class="start-tag">path</span> <span class="attribute-name">d</span>="<a class="attribute-value">M14 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V8z</a>"<span>/</span>&gt;</span><span></span><span>&lt;<span class="start-tag">polyline</span> <span class="attribute-name">points</span>="<a class="attribute-value">14 2 14 8 20 8</a>"<span>/</span>&gt;</span><span></span><span>&lt;/<span class="end-tag">svg</span>&gt;</span><span>
</span></span><span id="line800"><span>          </span><span>&lt;<span class="start-tag">span</span> <span class="attribute-name">data-i18n</span>="<a class="attribute-value">logDisabledMsg</a>"&gt;</span><span></span><span>&lt;/<span class="end-tag">span</span>&gt;</span><span>
</span></span><span id="line801"><span>        </span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span>
</span></span><span id="line802"><span>        </span><span>&lt;<span class="start-tag">div</span> <span class="attribute-name">class</span>="<a class="attribute-value">log-wrap</a>" <span class="attribute-name">id</span>="<a class="attribute-value">logEl</a>"&gt;</span><span></span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span>
</span></span><span id="line803"><span>      </span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span>
</span></span><span id="line804"><span>    </span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span></span><span class="comment">&lt;!-- /col-right --&gt;</span><span>
</span></span><span id="line805"><span>
</span></span><span id="line806"><span>  </span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span></span><span class="comment">&lt;!-- /layout --&gt;</span><span>
</span></span><span id="line807"><span>
</span></span><span id="line808"><span>  </span><span>&lt;<span class="start-tag">footer</span>&gt;</span><span>
</span></span><span id="line809"><span>    </span><span>&lt;<span class="start-tag">a</span> <span class="attribute-name">href</span>="<a class="attribute-value" href="view-source:https://github.com/gb88/BLEOTA">https://github.com/gb88/BLEOTA</a>" <span class="attribute-name">target</span>="<a class="attribute-value">_blank</a>"&gt;</span><span>gb88/BLEOTA</span><span>&lt;/<span class="end-tag">a</span>&gt;</span><span> — ESP32 BLE OTA Library
</span></span><span id="line810"><span>  </span><span>&lt;/<span class="end-tag">footer</span>&gt;</span><span>
</span></span><span id="line811"><span></span><span>&lt;/<span class="end-tag">div</span>&gt;</span><span>
</span></span><span id="line812"><span>
</span></span><span id="line813"><span></span><span>&lt;<span class="start-tag">script</span>&gt;</span><span>
</span></span><span id="line814"><span>// ════════════════════════════════════════════════
</span></span><span id="line815"><span>// i18n
</span></span><span id="line816"><span>// ════════════════════════════════════════════════
</span></span><span id="line817"><span>const LANGS = {
</span></span><span id="line818"><span>  it: {
</span></span><span id="line819"><span>    flag:'🇮🇹', code:'IT',
</span></span><span id="line820"><span>    subtitle: 'Aggiornamento firmware · Web Bluetooth',
</span></span><span id="line821"><span>    noBT: 'Web Bluetooth non supportato. Usa Chrome o Edge su desktop/Android.',
</span></span><span id="line822"><span>    deviceLabel: 'Dispositivo BLE',
</span></span><span id="line823"><span>    devName: 'Nome', devModel: 'Modello', devFW: 'Firmware',
</span></span><span id="line824"><span>    devHW: 'Hardware', devMfr: 'Produttore', devSerial: 'Seriale',
</span></span><span id="line825"><span>    connect: 'Connetti', disconnect: 'Disconnetti',
</span></span><span id="line826"><span>    httpTitle: 'Connessione non sicura (HTTP)',
</span></span><span id="line827"><span>    httpDesc: 'Web Bluetooth richiede </span><span>&lt;s</span><span>trong&gt;HTTPS</span><span>&lt;/<span>s</span>t</span><span>rong&gt;. Apri questa pagina tramite </span><span>&lt;c</span><span>ode&gt;https://</span><span>&lt;/<span></span>c</span><span>ode&gt; oppure servila da </span><span>&lt;c</span><span>ode&gt;localhost</span><span>&lt;/<span></span>c</span><span>ode&gt;.',
</span></span><span id="line828"><span>    noBTTitle: 'Web Bluetooth non supportato',
</span></span><span id="line829"><span>    noBTDesc: 'Usa Chrome o Edge su desktop o Android. Safari e Firefox non supportano Web Bluetooth.',
</span></span><span id="line830"><span>    otaLabel: 'Aggiornamento OTA',
</span></span><span id="line831"><span>    otaFlash: 'Firmware', otaSpiffs: 'SPIFFS / LittleFS',
</span></span><span id="line832"><span>    dropTitle: 'Trascina il file .bin qui',
</span></span><span id="line833"><span>    dropSub: 'oppure clicca per selezionare',
</span></span><span id="line834"><span>    startOTA: 'Avvia aggiornamento', abort: 'Interrompi',
</span></span><span id="line835"><span>    statSent: 'Inviato', statTotal: 'Totale', statSector: 'Settore',
</span></span><span id="line836"><span>    statSpeed: 'Velocità', statETA: 'Rimasto',
</span></span><span id="line837"><span>    successTitle: 'Aggiornamento completato',
</span></span><span id="line838"><span>    successSub: 'Il dispositivo si sta riavviando…',
</span></span><span id="line839"><span>    logLabel: 'Log', clearLog: 'Pulisci',
</span></span><span id="line840"><span>    logEnable: 'Log', logDisabledMsg: 'Log disabilitato',
</span></span><span id="line841"><span>    // dynamic
</span></span><span id="line842"><span>    stDisconnected: 'Disconnesso',
</span></span><span id="line843"><span>    stScanning: 'Scansione…',
</span></span><span id="line844"><span>    stConnecting: 'Connessione…',
</span></span><span id="line845"><span>    stConnected: 'Connesso',
</span></span><span id="line846"><span>    stUploading: 'Aggiornamento in corso…',
</span></span><span id="line847"><span>    stCompleted: 'Completato',
</span></span><span id="line848"><span>    stAborted: 'Interrotto',
</span></span><span id="line849"><span>    stError: 'Errore',
</span></span><span id="line850"><span>    stConnFailed: 'Connessione fallita',
</span></span><span id="line851"><span>    progTransferring: 'Trasferimento in corso…',
</span></span><span id="line852"><span>    progDone: 'Completato',
</span></span><span id="line853"><span>    logBTReady: 'Web Bluetooth API pronta',
</span></span><span id="line854"><span>    logBTNo: 'Web Bluetooth non disponibile',
</span></span><span id="line855"><span>    logScanning: 'Avvio scansione BLE…',
</span></span><span id="line856"><span>    logFound: 'Connesso a',
</span></span><span id="line857"><span>    logDISNo: 'DIS service non presente',
</span></span><span id="line858"><span>    logDisconn: 'Dispositivo disconnesso',
</span></span><span id="line859"><span>    logDisconnMan: 'Disconnesso manualmente',
</span></span><span id="line860"><span>    logOtaType: 'Tipo OTA',
</span></span><span id="line861"><span>    logFileInvalid: 'File non valido (serve .bin)',
</span></span><span id="line862"><span>    logCmdAck: 'CMD_ACK resp',
</span></span><span id="line863"><span>    logStartOTA: 'START',
</span></span><span id="line864"><span>    logOtaAccepted: 'OTA accettato, trasferimento…',
</span></span><span id="line865"><span>    logSectorOK: 'Settore OK',
</span></span><span id="line866"><span>    logOtaDone: 'OTA completato!',
</span></span><span id="line867"><span>    errSignature: 'Errore firma: firmware rifiutato dal dispositivo',
</span></span><span id="line868"><span>    errNack: 'Comando rifiutato dal dispositivo',
</span></span><span id="line869"><span>    errCmdTimeout: 'Timeout risposta comando',
</span></span><span id="line870"><span>    errStartFailed: 'Avvio OTA fallito',
</span></span><span id="line871"><span>    errStopFailed: 'Verifica firmware fallita',
</span></span><span id="line872"><span>    logAbort: 'Interruzione…',
</span></span><span id="line873"><span>    logAborted: 'OTA interrotto',
</span></span><span id="line874"><span>    logError: 'Errore',
</span></span><span id="line875"><span>  },
</span></span><span id="line876"><span>  en: {
</span></span><span id="line877"><span>    flag:'🇬🇧', code:'EN',
</span></span><span id="line878"><span>    subtitle: 'Firmware updater · Web Bluetooth',
</span></span><span id="line879"><span>    noBT: 'Web Bluetooth is not supported. Use Chrome or Edge on desktop/Android.',
</span></span><span id="line880"><span>    deviceLabel: 'BLE Device',
</span></span><span id="line881"><span>    devName: 'Name', devModel: 'Model', devFW: 'Firmware',
</span></span><span id="line882"><span>    devHW: 'Hardware', devMfr: 'Manufacturer', devSerial: 'Serial',
</span></span><span id="line883"><span>    connect: 'Connect', disconnect: 'Disconnect',
</span></span><span id="line884"><span>    httpTitle: 'Insecure connection (HTTP)',
</span></span><span id="line885"><span>    httpDesc: 'Web Bluetooth requires </span><span>&lt;s</span><span>trong&gt;HTTPS</span><span>&lt;/<span>s</span>t</span><span>rong&gt;. Open this page via </span><span>&lt;c</span><span>ode&gt;https://</span><span>&lt;/<span></span>c</span><span>ode&gt; or serve it from </span><span>&lt;c</span><span>ode&gt;localhost</span><span>&lt;/<span></span>c</span><span>ode&gt;.',
</span></span><span id="line886"><span>    noBTTitle: 'Web Bluetooth not supported',
</span></span><span id="line887"><span>    noBTDesc: 'Use Chrome or Edge on desktop or Android. Safari and Firefox do not support Web Bluetooth.',
</span></span><span id="line888"><span>    otaLabel: 'OTA Update',
</span></span><span id="line889"><span>    otaFlash: 'Firmware', otaSpiffs: 'SPIFFS / LittleFS',
</span></span><span id="line890"><span>    dropTitle: 'Drop .bin file here',
</span></span><span id="line891"><span>    dropSub: 'or click to select',
</span></span><span id="line892"><span>    startOTA: 'Start update', abort: 'Abort',
</span></span><span id="line893"><span>    statSent: 'Sent', statTotal: 'Total', statSector: 'Sector',
</span></span><span id="line894"><span>    statSpeed: 'Speed', statETA: 'Remaining',
</span></span><span id="line895"><span>    successTitle: 'Update complete',
</span></span><span id="line896"><span>    successSub: 'Device is rebooting…',
</span></span><span id="line897"><span>    logLabel: 'Log', clearLog: 'Clear',
</span></span><span id="line898"><span>    logEnable: 'Log', logDisabledMsg: 'Log disabled',
</span></span><span id="line899"><span>    stDisconnected: 'Disconnected',
</span></span><span id="line900"><span>    stScanning: 'Scanning…',
</span></span><span id="line901"><span>    stConnecting: 'Connecting…',
</span></span><span id="line902"><span>    stConnected: 'Connected',
</span></span><span id="line903"><span>    stUploading: 'Updating…',
</span></span><span id="line904"><span>    stCompleted: 'Completed',
</span></span><span id="line905"><span>    stAborted: 'Aborted',
</span></span><span id="line906"><span>    stError: 'Error',
</span></span><span id="line907"><span>    stConnFailed: 'Connection failed',
</span></span><span id="line908"><span>    progTransferring: 'Transferring…',
</span></span><span id="line909"><span>    progDone: 'Done',
</span></span><span id="line910"><span>    logBTReady: 'Web Bluetooth API ready',
</span></span><span id="line911"><span>    logBTNo: 'Web Bluetooth not available',
</span></span><span id="line912"><span>    logScanning: 'Starting BLE scan…',
</span></span><span id="line913"><span>    logFound: 'Connected to',
</span></span><span id="line914"><span>    logDISNo: 'DIS service not available',
</span></span><span id="line915"><span>    logDisconn: 'Device disconnected',
</span></span><span id="line916"><span>    logDisconnMan: 'Manually disconnected',
</span></span><span id="line917"><span>    logOtaType: 'OTA type',
</span></span><span id="line918"><span>    logFileInvalid: 'Invalid file (need .bin)',
</span></span><span id="line919"><span>    logCmdAck: 'CMD_ACK resp',
</span></span><span id="line920"><span>    logStartOTA: 'START',
</span></span><span id="line921"><span>    logOtaAccepted: 'OTA accepted, transferring…',
</span></span><span id="line922"><span>    logSectorOK: 'Sector OK',
</span></span><span id="line923"><span>    logOtaDone: 'OTA completed!',
</span></span><span id="line924"><span>    errSignature: 'Signature error: firmware rejected by device',
</span></span><span id="line925"><span>    errNack: 'Command rejected by device',
</span></span><span id="line926"><span>    errCmdTimeout: 'Command response timeout',
</span></span><span id="line927"><span>    errStartFailed: 'OTA start failed',
</span></span><span id="line928"><span>    errStopFailed: 'Firmware verification failed',
</span></span><span id="line929"><span>    logAbort: 'Aborting…',
</span></span><span id="line930"><span>    logAborted: 'OTA aborted',
</span></span><span id="line931"><span>    logError: 'Error',
</span></span><span id="line932"><span>  },
</span></span><span id="line933"><span>  de: {
</span></span><span id="line934"><span>    flag:'🇩🇪', code:'DE',
</span></span><span id="line935"><span>    subtitle: 'Firmware-Updater · Web Bluetooth',
</span></span><span id="line936"><span>    noBT: 'Web Bluetooth wird nicht unterstützt. Verwende Chrome oder Edge auf Desktop/Android.',
</span></span><span id="line937"><span>    deviceLabel: 'BLE-Gerät',
</span></span><span id="line938"><span>    devName: 'Name', devModel: 'Modell', devFW: 'Firmware',
</span></span><span id="line939"><span>    devHW: 'Hardware', devMfr: 'Hersteller', devSerial: 'Seriennr.',
</span></span><span id="line940"><span>    connect: 'Verbinden', disconnect: 'Trennen',
</span></span><span id="line941"><span>    httpTitle: 'Unsichere Verbindung (HTTP)',
</span></span><span id="line942"><span>    httpDesc: 'Web Bluetooth erfordert </span><span>&lt;s</span><span>trong&gt;HTTPS</span><span>&lt;/<span>s</span>t</span><span>rong&gt;. Öffne die Seite über </span><span>&lt;c</span><span>ode&gt;https://</span><span>&lt;/<span></span>c</span><span>ode&gt; oder von </span><span>&lt;c</span><span>ode&gt;localhost</span><span>&lt;/<span></span>c</span><span>ode&gt;.',
</span></span><span id="line943"><span>    noBTTitle: 'Web Bluetooth nicht unterstützt',
</span></span><span id="line944"><span>    noBTDesc: 'Verwende Chrome oder Edge auf Desktop oder Android. Safari und Firefox unterstützen Web Bluetooth nicht.',
</span></span><span id="line945"><span>    otaLabel: 'OTA-Update',
</span></span><span id="line946"><span>    otaFlash: 'Firmware', otaSpiffs: 'SPIFFS / LittleFS',
</span></span><span id="line947"><span>    dropTitle: '.bin-Datei hier ablegen',
</span></span><span id="line948"><span>    dropSub: 'oder klicken zum Auswählen',
</span></span><span id="line949"><span>    startOTA: 'Update starten', abort: 'Abbrechen',
</span></span><span id="line950"><span>    statSent: 'Gesendet', statTotal: 'Gesamt', statSector: 'Sektor',
</span></span><span id="line951"><span>    statSpeed: 'Geschw.', statETA: 'Verbleibend',
</span></span><span id="line952"><span>    successTitle: 'Update abgeschlossen',
</span></span><span id="line953"><span>    successSub: 'Gerät wird neu gestartet…',
</span></span><span id="line954"><span>    logLabel: 'Protokoll', clearLog: 'Leeren',
</span></span><span id="line955"><span>    logEnable: 'Log', logDisabledMsg: 'Protokoll deaktiviert',
</span></span><span id="line956"><span>    stDisconnected: 'Getrennt',
</span></span><span id="line957"><span>    stScanning: 'Suche…',
</span></span><span id="line958"><span>    stConnecting: 'Verbinde…',
</span></span><span id="line959"><span>    stConnected: 'Verbunden',
</span></span><span id="line960"><span>    stUploading: 'Aktualisierung…',
</span></span><span id="line961"><span>    stCompleted: 'Abgeschlossen',
</span></span><span id="line962"><span>    stAborted: 'Abgebrochen',
</span></span><span id="line963"><span>    stError: 'Fehler',
</span></span><span id="line964"><span>    stConnFailed: 'Verbindung fehlgeschlagen',
</span></span><span id="line965"><span>    progTransferring: 'Übertragung läuft…',
</span></span><span id="line966"><span>    progDone: 'Fertig',
</span></span><span id="line967"><span>    logBTReady: 'Web Bluetooth API bereit',
</span></span><span id="line968"><span>    logBTNo: 'Web Bluetooth nicht verfügbar',
</span></span><span id="line969"><span>    logScanning: 'BLE-Scan gestartet…',
</span></span><span id="line970"><span>    logFound: 'Verbunden mit',
</span></span><span id="line971"><span>    logDISNo: 'DIS-Service nicht vorhanden',
</span></span><span id="line972"><span>    logDisconn: 'Gerät getrennt',
</span></span><span id="line973"><span>    logDisconnMan: 'Manuell getrennt',
</span></span><span id="line974"><span>    logOtaType: 'OTA-Typ',
</span></span><span id="line975"><span>    logFileInvalid: 'Ungültige Datei (.bin erforderlich)',
</span></span><span id="line976"><span>    logCmdAck: 'CMD_ACK resp',
</span></span><span id="line977"><span>    logStartOTA: 'START',
</span></span><span id="line978"><span>    logOtaAccepted: 'OTA akzeptiert, übertrage…',
</span></span><span id="line979"><span>    logSectorOK: 'Sektor OK',
</span></span><span id="line980"><span>    logOtaDone: 'OTA abgeschlossen!',
</span></span><span id="line981"><span>    errSignature: 'Signaturfehler: Firmware vom Gerät abgelehnt',
</span></span><span id="line982"><span>    errNack: 'Befehl vom Gerät abgelehnt',
</span></span><span id="line983"><span>    errCmdTimeout: 'Timeout Befehlsantwort',
</span></span><span id="line984"><span>    errStartFailed: 'OTA-Start fehlgeschlagen',
</span></span><span id="line985"><span>    errStopFailed: 'Firmware-Überprüfung fehlgeschlagen',
</span></span><span id="line986"><span>    logAbort: 'Wird abgebrochen…',
</span></span><span id="line987"><span>    logAborted: 'OTA abgebrochen',
</span></span><span id="line988"><span>    logError: 'Fehler',
</span></span><span id="line989"><span>  },
</span></span><span id="line990"><span>  fr: {
</span></span><span id="line991"><span>    flag:'🇫🇷', code:'FR',
</span></span><span id="line992"><span>    subtitle: 'Mise à jour firmware · Web Bluetooth',
</span></span><span id="line993"><span>    noBT: 'Web Bluetooth non supporté. Utilisez Chrome ou Edge sur bureau/Android.',
</span></span><span id="line994"><span>    deviceLabel: 'Appareil BLE',
</span></span><span id="line995"><span>    devName: 'Nom', devModel: 'Modèle', devFW: 'Firmware',
</span></span><span id="line996"><span>    devHW: 'Matériel', devMfr: 'Fabricant', devSerial: 'Numéro de série',
</span></span><span id="line997"><span>    connect: 'Connecter', disconnect: 'Déconnecter',
</span></span><span id="line998"><span>    httpTitle: 'Connexion non sécurisée (HTTP)',
</span></span><span id="line999"><span>    httpDesc: 'Web Bluetooth nécessite </span><span>&lt;s</span><span>trong&gt;HTTPS</span><span>&lt;/<span>s</span>t</span><span>rong&gt;. Ouvrez cette page via </span><span>&lt;c</span><span>ode&gt;https://</span><span>&lt;/<span></span>c</span><span>ode&gt; ou depuis </span><span>&lt;c</span><span>ode&gt;localhost</span><span>&lt;/<span></span>c</span><span>ode&gt;.',
</span></span><span id="line1000"><span>    noBTTitle: 'Web Bluetooth non supporté',
</span></span><span id="line1001"><span>    noBTDesc: 'Utilisez Chrome ou Edge sur bureau ou Android. Safari et Firefox ne supportent pas Web Bluetooth.',
</span></span><span id="line1002"><span>    otaLabel: 'Mise à jour OTA',
</span></span><span id="line1003"><span>    otaFlash: 'Firmware', otaSpiffs: 'SPIFFS / LittleFS',
</span></span><span id="line1004"><span>    dropTitle: 'Déposez le fichier .bin ici',
</span></span><span id="line1005"><span>    dropSub: 'ou cliquez pour sélectionner',
</span></span><span id="line1006"><span>    startOTA: 'Lancer la mise à jour', abort: 'Annuler',
</span></span><span id="line1007"><span>    statSent: 'Envoyé', statTotal: 'Total', statSector: 'Secteur',
</span></span><span id="line1008"><span>    statSpeed: 'Vitesse', statETA: 'Restant',
</span></span><span id="line1009"><span>    successTitle: 'Mise à jour terminée',
</span></span><span id="line1010"><span>    successSub: "L'appareil redémarre…",
</span></span><span id="line1011"><span>    logLabel: 'Journal', clearLog: 'Effacer',
</span></span><span id="line1012"><span>    logEnable: 'Journal', logDisabledMsg: 'Journal désactivé',
</span></span><span id="line1013"><span>    stDisconnected: 'Déconnecté',
</span></span><span id="line1014"><span>    stScanning: 'Recherche…',
</span></span><span id="line1015"><span>    stConnecting: 'Connexion…',
</span></span><span id="line1016"><span>    stConnected: 'Connecté',
</span></span><span id="line1017"><span>    stUploading: 'Mise à jour…',
</span></span><span id="line1018"><span>    stCompleted: 'Terminé',
</span></span><span id="line1019"><span>    stAborted: 'Annulé',
</span></span><span id="line1020"><span>    stError: 'Erreur',
</span></span><span id="line1021"><span>    stConnFailed: 'Connexion échouée',
</span></span><span id="line1022"><span>    progTransferring: 'Transfert en cours…',
</span></span><span id="line1023"><span>    progDone: 'Terminé',
</span></span><span id="line1024"><span>    logBTReady: 'Web Bluetooth API prête',
</span></span><span id="line1025"><span>    logBTNo: 'Web Bluetooth non disponible',
</span></span><span id="line1026"><span>    logScanning: 'Démarrage scan BLE…',
</span></span><span id="line1027"><span>    logFound: 'Connecté à',
</span></span><span id="line1028"><span>    logDISNo: 'Service DIS non disponible',
</span></span><span id="line1029"><span>    logDisconn: 'Appareil déconnecté',
</span></span><span id="line1030"><span>    logDisconnMan: 'Déconnexion manuelle',
</span></span><span id="line1031"><span>    logOtaType: 'Type OTA',
</span></span><span id="line1032"><span>    logFileInvalid: 'Fichier invalide (besoin .bin)',
</span></span><span id="line1033"><span>    logCmdAck: 'CMD_ACK resp',
</span></span><span id="line1034"><span>    logStartOTA: 'DÉMARRAGE',
</span></span><span id="line1035"><span>    logOtaAccepted: 'OTA accepté, transfert…',
</span></span><span id="line1036"><span>    logSectorOK: 'Secteur OK',
</span></span><span id="line1037"><span>    logOtaDone: 'OTA terminé !',
</span></span><span id="line1038"><span>    errSignature: 'Erreur de signature : firmware rejeté par le dispositif',
</span></span><span id="line1039"><span>    errNack: 'Commande rejetée par le dispositif',
</span></span><span id="line1040"><span>    errCmdTimeout: 'Délai de réponse de commande expiré',
</span></span><span id="line1041"><span>    errStartFailed: 'Échec du démarrage OTA',
</span></span><span id="line1042"><span>    errStopFailed: 'Échec de la vérification du firmware',
</span></span><span id="line1043"><span>    logAbort: 'Annulation…',
</span></span><span id="line1044"><span>    logAborted: 'OTA annulé',
</span></span><span id="line1045"><span>    logError: 'Erreur',
</span></span><span id="line1046"><span>  },
</span></span><span id="line1047"><span>  es: {
</span></span><span id="line1048"><span>    flag:'🇪🇸', code:'ES',
</span></span><span id="line1049"><span>    subtitle: 'Actualizador firmware · Web Bluetooth',
</span></span><span id="line1050"><span>    noBT: 'Web Bluetooth no está disponible. Usa Chrome o Edge en escritorio/Android.',
</span></span><span id="line1051"><span>    deviceLabel: 'Dispositivo BLE',
</span></span><span id="line1052"><span>    devName: 'Nombre', devModel: 'Modelo', devFW: 'Firmware',
</span></span><span id="line1053"><span>    devHW: 'Hardware', devMfr: 'Fabricante', devSerial: 'N° serie',
</span></span><span id="line1054"><span>    connect: 'Conectar', disconnect: 'Desconectar',
</span></span><span id="line1055"><span>    httpTitle: 'Conexión no segura (HTTP)',
</span></span><span id="line1056"><span>    httpDesc: 'Web Bluetooth requiere </span><span>&lt;s</span><span>trong&gt;HTTPS</span><span>&lt;/<span>s</span>t</span><span>rong&gt;. Abre esta página desde </span><span>&lt;c</span><span>ode&gt;https://</span><span>&lt;/<span></span>c</span><span>ode&gt; o sírvela desde </span><span>&lt;c</span><span>ode&gt;localhost</span><span>&lt;/<span></span>c</span><span>ode&gt;.',
</span></span><span id="line1057"><span>    noBTTitle: 'Web Bluetooth no soportado',
</span></span><span id="line1058"><span>    noBTDesc: 'Usa Chrome o Edge en escritorio o Android. Safari y Firefox no admiten Web Bluetooth.',
</span></span><span id="line1059"><span>    otaLabel: 'Actualización OTA',
</span></span><span id="line1060"><span>    otaFlash: 'Firmware', otaSpiffs: 'SPIFFS / LittleFS',
</span></span><span id="line1061"><span>    dropTitle: 'Arrastra el archivo .bin aquí',
</span></span><span id="line1062"><span>    dropSub: 'o haz clic para seleccionar',
</span></span><span id="line1063"><span>    startOTA: 'Iniciar actualización', abort: 'Cancelar',
</span></span><span id="line1064"><span>    statSent: 'Enviado', statTotal: 'Total', statSector: 'Sector',
</span></span><span id="line1065"><span>    statSpeed: 'Velocidad', statETA: 'Restante',
</span></span><span id="line1066"><span>    successTitle: 'Actualización completada',
</span></span><span id="line1067"><span>    successSub: 'El dispositivo está reiniciando…',
</span></span><span id="line1068"><span>    logLabel: 'Registro', clearLog: 'Limpiar',
</span></span><span id="line1069"><span>    logEnable: 'Registro', logDisabledMsg: 'Registro desactivado',
</span></span><span id="line1070"><span>    stDisconnected: 'Desconectado',
</span></span><span id="line1071"><span>    stScanning: 'Buscando…',
</span></span><span id="line1072"><span>    stConnecting: 'Conectando…',
</span></span><span id="line1073"><span>    stConnected: 'Conectado',
</span></span><span id="line1074"><span>    stUploading: 'Actualizando…',
</span></span><span id="line1075"><span>    stCompleted: 'Completado',
</span></span><span id="line1076"><span>    stAborted: 'Cancelado',
</span></span><span id="line1077"><span>    stError: 'Error',
</span></span><span id="line1078"><span>    stConnFailed: 'Conexión fallida',
</span></span><span id="line1079"><span>    progTransferring: 'Transfiriendo…',
</span></span><span id="line1080"><span>    progDone: 'Listo',
</span></span><span id="line1081"><span>    logBTReady: 'Web Bluetooth API lista',
</span></span><span id="line1082"><span>    logBTNo: 'Web Bluetooth no disponible',
</span></span><span id="line1083"><span>    logScanning: 'Iniciando escaneo BLE…',
</span></span><span id="line1084"><span>    logFound: 'Conectado a',
</span></span><span id="line1085"><span>    logDISNo: 'Servicio DIS no disponible',
</span></span><span id="line1086"><span>    logDisconn: 'Dispositivo desconectado',
</span></span><span id="line1087"><span>    logDisconnMan: 'Desconectado manualmente',
</span></span><span id="line1088"><span>    logOtaType: 'Tipo OTA',
</span></span><span id="line1089"><span>    logFileInvalid: 'Archivo inválido (se requiere .bin)',
</span></span><span id="line1090"><span>    logCmdAck: 'CMD_ACK resp',
</span></span><span id="line1091"><span>    logStartOTA: 'INICIO',
</span></span><span id="line1092"><span>    logOtaAccepted: 'OTA aceptado, transfiriendo…',
</span></span><span id="line1093"><span>    logSectorOK: 'Sector OK',
</span></span><span id="line1094"><span>    logOtaDone: '¡OTA completado!',
</span></span><span id="line1095"><span>    errSignature: 'Error de firma: firmware rechazado por el dispositivo',
</span></span><span id="line1096"><span>    errNack: 'Comando rechazado por el dispositivo',
</span></span><span id="line1097"><span>    errCmdTimeout: 'Tiempo de espera de respuesta agotado',
</span></span><span id="line1098"><span>    errStartFailed: 'Fallo al iniciar OTA',
</span></span><span id="line1099"><span>    errStopFailed: 'Verificación de firmware fallida',
</span></span><span id="line1100"><span>    logAbort: 'Cancelando…',
</span></span><span id="line1101"><span>    logAborted: 'OTA cancelado',
</span></span><span id="line1102"><span>    logError: 'Error',
</span></span><span id="line1103"><span>  },
</span></span><span id="line1104"><span>  zh: {
</span></span><span id="line1105"><span>    flag:'🇨🇳', code:'中文',
</span></span><span id="line1106"><span>    subtitle: '固件更新 · Web 蓝牙',
</span></span><span id="line1107"><span>    noBT: '此浏览器不支持 Web 蓝牙。请在桌面或 Android 上使用 Chrome 或 Edge。',
</span></span><span id="line1108"><span>    deviceLabel: 'BLE 设备',
</span></span><span id="line1109"><span>    devName: '名称', devModel: '型号', devFW: '固件版本',
</span></span><span id="line1110"><span>    devHW: '硬件版本', devMfr: '制造商', devSerial: '序列号',
</span></span><span id="line1111"><span>    connect: '连接', disconnect: '断开',
</span></span><span id="line1112"><span>    httpTitle: '不安全的连接 (HTTP)',
</span></span><span id="line1113"><span>    httpDesc: 'Web 蓝牙需要 </span><span>&lt;s</span><span>trong&gt;HTTPS</span><span>&lt;/<span>s</span>t</span><span>rong&gt;。请通过 </span><span>&lt;c</span><span>ode&gt;https://</span><span>&lt;/<span></span>c</span><span>ode&gt; 访问本页面，或从 </span><span>&lt;c</span><span>ode&gt;localhost</span><span>&lt;/<span></span>c</span><span>ode&gt; 提供服务。',
</span></span><span id="line1114"><span>    noBTTitle: '不支持 Web 蓝牙',
</span></span><span id="line1115"><span>    noBTDesc: '请在桌面或 Android 上使用 Chrome 或 Edge。Safari 和 Firefox 不支持 Web 蓝牙。',
</span></span><span id="line1116"><span>    otaLabel: 'OTA 更新',
</span></span><span id="line1117"><span>    otaFlash: '固件', otaSpiffs: 'SPIFFS / LittleFS',
</span></span><span id="line1118"><span>    dropTitle: '将 .bin 文件拖放到此处',
</span></span><span id="line1119"><span>    dropSub: '或点击选择文件',
</span></span><span id="line1120"><span>    startOTA: '开始更新', abort: '中止',
</span></span><span id="line1121"><span>    statSent: '已发送', statTotal: '总计', statSector: '扇区',
</span></span><span id="line1122"><span>    statSpeed: '速度', statETA: '剩余时间',
</span></span><span id="line1123"><span>    successTitle: '更新完成',
</span></span><span id="line1124"><span>    successSub: '设备正在重启…',
</span></span><span id="line1125"><span>    logLabel: '日志', clearLog: '清空',
</span></span><span id="line1126"><span>    logEnable: '日志', logDisabledMsg: '日志已禁用',
</span></span><span id="line1127"><span>    stDisconnected: '已断开',
</span></span><span id="line1128"><span>    stScanning: '扫描中…',
</span></span><span id="line1129"><span>    stConnecting: '连接中…',
</span></span><span id="line1130"><span>    stConnected: '已连接',
</span></span><span id="line1131"><span>    stUploading: '更新中…',
</span></span><span id="line1132"><span>    stCompleted: '已完成',
</span></span><span id="line1133"><span>    stAborted: '已中止',
</span></span><span id="line1134"><span>    stError: '错误',
</span></span><span id="line1135"><span>    stConnFailed: '连接失败',
</span></span><span id="line1136"><span>    progTransferring: '传输中…',
</span></span><span id="line1137"><span>    progDone: '完成',
</span></span><span id="line1138"><span>    logBTReady: 'Web 蓝牙 API 就绪',
</span></span><span id="line1139"><span>    logBTNo: 'Web 蓝牙不可用',
</span></span><span id="line1140"><span>    logScanning: '正在启动 BLE 扫描…',
</span></span><span id="line1141"><span>    logFound: '已连接至',
</span></span><span id="line1142"><span>    logDISNo: 'DIS 服务不可用',
</span></span><span id="line1143"><span>    logDisconn: '设备已断开',
</span></span><span id="line1144"><span>    logDisconnMan: '手动断开连接',
</span></span><span id="line1145"><span>    logOtaType: 'OTA 类型',
</span></span><span id="line1146"><span>    logFileInvalid: '无效文件（需要 .bin 文件）',
</span></span><span id="line1147"><span>    logCmdAck: 'CMD_ACK resp',
</span></span><span id="line1148"><span>    logStartOTA: '开始',
</span></span><span id="line1149"><span>    logOtaAccepted: 'OTA 已接受，正在传输…',
</span></span><span id="line1150"><span>    logSectorOK: '扇区 OK',
</span></span><span id="line1151"><span>    logOtaDone: 'OTA 完成！',
</span></span><span id="line1152"><span>    errSignature: '签名错误：固件被设备拒绝',
</span></span><span id="line1153"><span>    errNack: '设备拒绝了命令',
</span></span><span id="line1154"><span>    errCmdTimeout: '命令响应超时',
</span></span><span id="line1155"><span>    errStartFailed: 'OTA 启动失败',
</span></span><span id="line1156"><span>    errStopFailed: '固件验证失败',
</span></span><span id="line1157"><span>    logAbort: '正在中止…',
</span></span><span id="line1158"><span>    logAborted: 'OTA 已中止',
</span></span><span id="line1159"><span>    logError: '错误',
</span></span><span id="line1160"><span>  },
</span></span><span id="line1161"><span>  ru: {
</span></span><span id="line1162"><span>    flag:'🇷🇺', code:'RU',
</span></span><span id="line1163"><span>    subtitle: 'Обновление прошивки · Web Bluetooth',
</span></span><span id="line1164"><span>    noBT: 'Web Bluetooth не поддерживается. Используйте Chrome или Edge на ПК/Android.',
</span></span><span id="line1165"><span>    deviceLabel: 'BLE Устройство',
</span></span><span id="line1166"><span>    devName: 'Имя', devModel: 'Модель', devFW: 'Прошивка',
</span></span><span id="line1167"><span>    devHW: 'Железо', devMfr: 'Производитель', devSerial: 'Серийный №',
</span></span><span id="line1168"><span>    connect: 'Подключить', disconnect: 'Отключить',
</span></span><span id="line1169"><span>    httpTitle: 'Небезопасное соединение (HTTP)',
</span></span><span id="line1170"><span>    httpDesc: 'Web Bluetooth требует </span><span>&lt;s</span><span>trong&gt;HTTPS</span><span>&lt;/<span>s</span>t</span><span>rong&gt;. Откройте страницу через </span><span>&lt;c</span><span>ode&gt;https://</span><span>&lt;/<span></span>c</span><span>ode&gt; или с </span><span>&lt;c</span><span>ode&gt;localhost</span><span>&lt;/<span></span>c</span><span>ode&gt;.',
</span></span><span id="line1171"><span>    noBTTitle: 'Web Bluetooth не поддерживается',
</span></span><span id="line1172"><span>    noBTDesc: 'Используйте Chrome или Edge на ПК или Android. Safari и Firefox не поддерживают Web Bluetooth.',
</span></span><span id="line1173"><span>    otaLabel: 'OTA Обновление',
</span></span><span id="line1174"><span>    otaFlash: 'Прошивка', otaSpiffs: 'SPIFFS / LittleFS',
</span></span><span id="line1175"><span>    dropTitle: 'Перетащите файл .bin сюда',
</span></span><span id="line1176"><span>    dropSub: 'или нажмите для выбора',
</span></span><span id="line1177"><span>    startOTA: 'Начать обновление', abort: 'Прервать',
</span></span><span id="line1178"><span>    statSent: 'Отправлено', statTotal: 'Всего', statSector: 'Сектор',
</span></span><span id="line1179"><span>    statSpeed: 'Скорость', statETA: 'Осталось',
</span></span><span id="line1180"><span>    successTitle: 'Обновление завершено',
</span></span><span id="line1181"><span>    successSub: 'Устройство перезагружается…',
</span></span><span id="line1182"><span>    logLabel: 'Журнал', clearLog: 'Очистить',
</span></span><span id="line1183"><span>    logEnable: 'Журнал', logDisabledMsg: 'Журнал отключён',
</span></span><span id="line1184"><span>    stDisconnected: 'Отключено',
</span></span><span id="line1185"><span>    stScanning: 'Поиск…',
</span></span><span id="line1186"><span>    stConnecting: 'Подключение…',
</span></span><span id="line1187"><span>    stConnected: 'Подключено',
</span></span><span id="line1188"><span>    stUploading: 'Обновление…',
</span></span><span id="line1189"><span>    stCompleted: 'Завершено',
</span></span><span id="line1190"><span>    stAborted: 'Прервано',
</span></span><span id="line1191"><span>    stError: 'Ошибка',
</span></span><span id="line1192"><span>    stConnFailed: 'Ошибка подключения',
</span></span><span id="line1193"><span>    progTransferring: 'Передача…',
</span></span><span id="line1194"><span>    progDone: 'Готово',
</span></span><span id="line1195"><span>    logBTReady: 'Web Bluetooth API готов',
</span></span><span id="line1196"><span>    logBTNo: 'Web Bluetooth недоступен',
</span></span><span id="line1197"><span>    logScanning: 'Запуск BLE сканирования…',
</span></span><span id="line1198"><span>    logFound: 'Подключено к',
</span></span><span id="line1199"><span>    logDISNo: 'Служба DIS недоступна',
</span></span><span id="line1200"><span>    logDisconn: 'Устройство отключено',
</span></span><span id="line1201"><span>    logDisconnMan: 'Отключено вручную',
</span></span><span id="line1202"><span>    logOtaType: 'Тип OTA',
</span></span><span id="line1203"><span>    logFileInvalid: 'Неверный файл (нужен .bin)',
</span></span><span id="line1204"><span>    logCmdAck: 'CMD_ACK resp',
</span></span><span id="line1205"><span>    logStartOTA: 'СТАРТ',
</span></span><span id="line1206"><span>    logOtaAccepted: 'OTA принято, передача…',
</span></span><span id="line1207"><span>    logSectorOK: 'Сектор OK',
</span></span><span id="line1208"><span>    logOtaDone: 'OTA завершено!',
</span></span><span id="line1209"><span>    errSignature: 'Ошибка подписи: прошивка отклонена устройством',
</span></span><span id="line1210"><span>    errNack: 'Команда отклонена устройством',
</span></span><span id="line1211"><span>    errCmdTimeout: 'Таймаут ответа на команду',
</span></span><span id="line1212"><span>    errStartFailed: 'Ошибка запуска OTA',
</span></span><span id="line1213"><span>    errStopFailed: 'Проверка прошивки не пройдена',
</span></span><span id="line1214"><span>    logAbort: 'Прерывание…',
</span></span><span id="line1215"><span>    logAborted: 'OTA прервано',
</span></span><span id="line1216"><span>    logError: 'Ошибка',
</span></span><span id="line1217"><span>  }
</span></span><span id="line1218"><span>};
</span></span><span id="line1219"><span>
</span></span><span id="line1220"><span>let currentLang = localStorage.getItem('bleLang') || 'it';
</span></span><span id="line1221"><span>
</span></span><span id="line1222"><span>function t(key) { return LANGS[currentLang]?.[key] ?? LANGS.en[key] ?? key; }
</span></span><span id="line1223"><span>
</span></span><span id="line1224"><span>function applyLang() {
</span></span><span id="line1225"><span>  document.querySelectorAll('[data-i18n]').forEach(el =&gt; {
</span></span><span id="line1226"><span>    const key = el.getAttribute('data-i18n');
</span></span><span id="line1227"><span>    el.textContent = t(key);
</span></span><span id="line1228"><span>  });
</span></span><span id="line1229"><span>  // httpDesc contains HTML tags — use innerHTML
</span></span><span id="line1230"><span>  if ($('httpDesc')) $('httpDesc').innerHTML = t('httpDesc');
</span></span><span id="line1231"><span>  const l = LANGS[currentLang];
</span></span><span id="line1232"><span>  $('langFlag').textContent = l.flag;
</span></span><span id="line1233"><span>  $('langCode').textContent = l.code;
</span></span><span id="line1234"><span>  document.documentElement.lang = currentLang;
</span></span><span id="line1235"><span>  // Update active item
</span></span><span id="line1236"><span>  document.querySelectorAll('.lang-item').forEach(el =&gt; {
</span></span><span id="line1237"><span>    el.classList.toggle('active', el.textContent.trim().startsWith(l.flag));
</span></span><span id="line1238"><span>  });
</span></span><span id="line1239"><span>  // Refresh dynamic status
</span></span><span id="line1240"><span>  if (!device?.gatt?.connected &amp;&amp; !uploading) setStatus(t('stDisconnected'), '');
</span></span><span id="line1241"><span>}
</span></span><span id="line1242"><span>
</span></span><span id="line1243"><span>function setLang(lang) {
</span></span><span id="line1244"><span>  currentLang = lang;
</span></span><span id="line1245"><span>  localStorage.setItem('bleLang', lang);
</span></span><span id="line1246"><span>  applyLang();
</span></span><span id="line1247"><span>  toggleLangMenu(false);
</span></span><span id="line1248"><span>  log(`${t('logOtaType')}: ${lang.toUpperCase()}`, 'info');
</span></span><span id="line1249"><span>}
</span></span><span id="line1250"><span>
</span></span><span id="line1251"><span>function toggleLangMenu(force) {
</span></span><span id="line1252"><span>  const m = $('langMenu');
</span></span><span id="line1253"><span>  const isOpen = m.classList.contains('open');
</span></span><span id="line1254"><span>  m.classList.toggle('open', force !== undefined ? force : !isOpen);
</span></span><span id="line1255"><span>}
</span></span><span id="line1256"><span>
</span></span><span id="line1257"><span>// Close menu on outside click
</span></span><span id="line1258"><span>document.addEventListener('click', e =&gt; {
</span></span><span id="line1259"><span>  if (!e.target.closest('.lang-wrap')) toggleLangMenu(false);
</span></span><span id="line1260"><span>});
</span></span><span id="line1261"><span>
</span></span><span id="line1262"><span>// ════════════════════════════════════════════════
</span></span><span id="line1263"><span>// Theme
</span></span><span id="line1264"><span>// ════════════════════════════════════════════════
</span></span><span id="line1265"><span>let isDark = localStorage.getItem('bleTheme') === 'dark';
</span></span><span id="line1266"><span>
</span></span><span id="line1267"><span>function applyTheme() {
</span></span><span id="line1268"><span>  document.documentElement.setAttribute('data-theme', isDark ? 'dark' : 'light');
</span></span><span id="line1269"><span>  const icon = $('themeIcon');
</span></span><span id="line1270"><span>  if (isDark) {
</span></span><span id="line1271"><span>    icon.innerHTML = '</span><span>&lt;c</span><span>ircle cx="12" cy="12" r="5"/&gt;</span><span>&lt;l</span><span>ine x1="12" y1="1" x2="12" y2="3"/&gt;</span><span>&lt;l</span><span>ine x1="12" y1="21" x2="12" y2="23"/&gt;</span><span>&lt;l</span><span>ine x1="4.22" y1="4.22" x2="5.64" y2="5.64"/&gt;</span><span>&lt;l</span><span>ine x1="18.36" y1="18.36" x2="19.78" y2="19.78"/&gt;</span><span>&lt;l</span><span>ine x1="1" y1="12" x2="3" y2="12"/&gt;</span><span>&lt;l</span><span>ine x1="21" y1="12" x2="23" y2="12"/&gt;</span><span>&lt;l</span><span>ine x1="4.22" y1="19.78" x2="5.64" y2="18.36"/&gt;</span><span>&lt;l</span><span>ine x1="18.36" y1="5.64" x2="19.78" y2="4.22"/&gt;';
</span></span><span id="line1272"><span>  } else {
</span></span><span id="line1273"><span>    icon.innerHTML = '</span><span>&lt;p</span><span>ath d="M21 12.79A9 9 0 1 1 11.21 3 7 7 0 0 0 21 12.79z"/&gt;';
</span></span><span id="line1274"><span>  }
</span></span><span id="line1275"><span>}
</span></span><span id="line1276"><span>
</span></span><span id="line1277"><span>function toggleTheme() {
</span></span><span id="line1278"><span>  isDark = !isDark;
</span></span><span id="line1279"><span>  localStorage.setItem('bleTheme', isDark ? 'dark' : 'light');
</span></span><span id="line1280"><span>  applyTheme();
</span></span><span id="line1281"><span>}
</span></span><span id="line1282"><span>
</span></span><span id="line1283"><span>// ════════════════════════════════════════════════
</span></span><span id="line1284"><span>// BLE Protocol constants
</span></span><span id="line1285"><span>// ════════════════════════════════════════════════
</span></span><span id="line1286"><span>const OTA_SVC   = '00008018-0000-1000-8000-00805f9b34fb';
</span></span><span id="line1287"><span>const RECV_CHAR = '00008020-0000-1000-8000-00805f9b34fb';
</span></span><span id="line1288"><span>const CMD_CHAR  = '00008022-0000-1000-8000-00805f9b34fb';
</span></span><span id="line1289"><span>const DIS_SVC   = '0000180a-0000-1000-8000-00805f9b34fb';
</span></span><span id="line1290"><span>const DIS_MDL   = '00002a24-0000-1000-8000-00805f9b34fb';
</span></span><span id="line1291"><span>const DIS_SRL   = '00002a25-0000-1000-8000-00805f9b34fb';
</span></span><span id="line1292"><span>const DIS_FWV   = '00002a26-0000-1000-8000-00805f9b34fb';
</span></span><span id="line1293"><span>const DIS_HWV   = '00002a27-0000-1000-8000-00805f9b34fb';
</span></span><span id="line1294"><span>const DIS_MNF   = '00002a29-0000-1000-8000-00805f9b34fb';
</span></span><span id="line1295"><span>const CMD_FLASH  = 0x0001;
</span></span><span id="line1296"><span>const CMD_STOP   = 0x0002;
</span></span><span id="line1297"><span>const CMD_ACK    = 0x0003;
</span></span><span id="line1298"><span>const CMD_SPIFFS = 0x0004;
</span></span><span id="line1299"><span>const SECTOR_SZ   = 4096;
</span></span><span id="line1300"><span>const PKT_PLOAD   = 507;  // max payload — may be reduced by MTU probe
</span></span><span id="line1301"><span>let   mtuPayload  = PKT_PLOAD; // actual payload used, set at connect time
</span></span><span id="line1302"><span>
</span></span><span id="line1303"><span>// ════════════════════════════════════════════════
</span></span><span id="line1304"><span>// App state
</span></span><span id="line1305"><span>// ════════════════════════════════════════════════
</span></span><span id="line1306"><span>let device=null, server=null, recvChar=null, cmdChar=null;
</span></span><span id="line1307"><span>let file=null, otaType='flash';
</span></span><span id="line1308"><span>let uploading=false, abortFlag=false, txStart=0;
</span></span><span id="line1309"><span>
</span></span><span id="line1310"><span>// ════════════════════════════════════════════════
</span></span><span id="line1311"><span>// Utils
</span></span><span id="line1312"><span>// ════════════════════════════════════════════════
</span></span><span id="line1313"><span>const $ = id =&gt; document.getElementById(id);
</span></span><span id="line1314"><span>const fmtBytes = b =&gt; b</span><span>&lt;1</span><span>024?`${b} B`:b</span><span>&lt;1</span><span>048576?`${(b/1024).toFixed(1)} KB`:`${(b/1048576).toFixed(2)} MB`;
</span></span><span id="line1315"><span>const fmtTime  = s =&gt; s</span><span>&lt;6</span><span>0?`${Math.round(s)}s`:`${Math.floor(s/60)}m ${Math.round(s%60)}s`;
</span></span><span id="line1316"><span>
</span></span><span id="line1317"><span>function log(msg, cls='info') {
</span></span><span id="line1318"><span>  if (!logEnabled) return;
</span></span><span id="line1319"><span>  const el=$('logEl');
</span></span><span id="line1320"><span>  const ts=new Date().toTimeString().slice(0,8);
</span></span><span id="line1321"><span>  el.innerHTML+=`</span><span>&lt;d</span><span>iv class="le"&gt;</span><span>&lt;s</span><span>pan class="lt"&gt;[${ts}]</span><span>&lt;/<span>s</span>p</span><span>an&gt;</span><span>&lt;s</span><span>pan class="lm ${cls}"&gt;${msg}</span><span>&lt;/<span>s</span>p</span><span>an&gt;</span><span>&lt;/<span></span>d</span><span>iv&gt;`;
</span></span><span id="line1322"><span>  el.scrollTop=el.scrollHeight;
</span></span><span id="line1323"><span>}
</span></span><span id="line1324"><span>
</span></span><span id="line1325"><span>// Always-visible log — used for errors/warnings regardless of log toggle.
</span></span><span id="line1326"><span>// Does NOT touch the status bar — only the final catch block does that.
</span></span><span id="line1327"><span>function logForce(msg, cls='info') {
</span></span><span id="line1328"><span>  const was = logEnabled;
</span></span><span id="line1329"><span>  // Auto-open log panel for errors/warnings
</span></span><span id="line1330"><span>  if (!was &amp;&amp; (cls === 'error' || cls === 'warn')) {
</span></span><span id="line1331"><span>    logEnabled = true;
</span></span><span id="line1332"><span>    $('logToggleTrack').classList.add('on');
</span></span><span id="line1333"><span>    $('logEl').classList.remove('hidden');
</span></span><span id="line1334"><span>    $('logDisabled').classList.add('hidden');
</span></span><span id="line1335"><span>    $('logClearBtn').classList.remove('hidden');
</span></span><span id="line1336"><span>  }
</span></span><span id="line1337"><span>  log(msg, cls);
</span></span><span id="line1338"><span>  // Keep log open after first error (user needs to read it)
</span></span><span id="line1339"><span>  if (cls === 'error' || cls === 'warn') logEnabled = true;
</span></span><span id="line1340"><span>  else logEnabled = was;
</span></span><span id="line1341"><span>}
</span></span><span id="line1342"><span>let logEnabled_saved = false;
</span></span><span id="line1343"><span>const clearLog=()=&gt;{ $('logEl').innerHTML=''; };
</span></span><span id="line1344"><span>
</span></span><span id="line1345"><span>// ── Log enable/disable ──
</span></span><span id="line1346"><span>let logEnabled = localStorage.getItem('bleLog') === 'true'; // default OFF
</span></span><span id="line1347"><span>
</span></span><span id="line1348"><span>function applyLogState() {
</span></span><span id="line1349"><span>  const track   = $('logToggleTrack');
</span></span><span id="line1350"><span>  const logEl   = $('logEl');
</span></span><span id="line1351"><span>  const disabled= $('logDisabled');
</span></span><span id="line1352"><span>  const clearBtn= $('logClearBtn');
</span></span><span id="line1353"><span>
</span></span><span id="line1354"><span>  if (logEnabled) {
</span></span><span id="line1355"><span>    track.classList.add('on');
</span></span><span id="line1356"><span>    logEl.classList.remove('hidden');
</span></span><span id="line1357"><span>    disabled.classList.add('hidden');
</span></span><span id="line1358"><span>    clearBtn.classList.remove('hidden');
</span></span><span id="line1359"><span>  } else {
</span></span><span id="line1360"><span>    track.classList.remove('on');
</span></span><span id="line1361"><span>    logEl.classList.add('hidden');
</span></span><span id="line1362"><span>    disabled.classList.remove('hidden');
</span></span><span id="line1363"><span>    clearBtn.classList.add('hidden');
</span></span><span id="line1364"><span>  }
</span></span><span id="line1365"><span>}
</span></span><span id="line1366"><span>
</span></span><span id="line1367"><span>function toggleLog() {
</span></span><span id="line1368"><span>  logEnabled = !logEnabled;
</span></span><span id="line1369"><span>  localStorage.setItem('bleLog', logEnabled);
</span></span><span id="line1370"><span>  applyLogState();
</span></span><span id="line1371"><span>}
</span></span><span id="line1372"><span>
</span></span><span id="line1373"><span>
</span></span><span id="line1374"><span>function setStatus(txt, state='') {
</span></span><span id="line1375"><span>  $('stText').textContent = txt;
</span></span><span id="line1376"><span>  $('dot').className = 'dot' + (state ? ' ' + state : '');
</span></span><span id="line1377"><span>  $('stTime').textContent = new Date().toTimeString().slice(0,8);
</span></span><span id="line1378"><span>  // Toggle error styling on the pill
</span></span><span id="line1379"><span>  const pill = $('stText').closest('.status-pill');
</span></span><span id="line1380"><span>  if (pill) pill.classList.toggle('has-error', state === 'error');
</span></span><span id="line1381"><span>}
</span></span><span id="line1382"><span>
</span></span><span id="line1383"><span>function updateStartBtn() {
</span></span><span id="line1384"><span>  $('btnStart').disabled=!(device?.gatt?.connected &amp;&amp; file &amp;&amp; !uploading);
</span></span><span id="line1385"><span>}
</span></span><span id="line1386"><span>
</span></span><span id="line1387"><span>// ════════════════════════════════════════════════
</span></span><span id="line1388"><span>// BLE
</span></span><span id="line1389"><span>// ════════════════════════════════════════════════
</span></span><span id="line1390"><span>function checkBT() {
</span></span><span id="line1391"><span>  const isSecure = location.protocol === 'https:' || location.hostname === 'localhost' || location.hostname === '127.0.0.1';
</span></span><span id="line1392"><span>
</span></span><span id="line1393"><span>  if (!isSecure) {
</span></span><span id="line1394"><span>    // HTTP context — Web Bluetooth blocked by browser regardless of support
</span></span><span id="line1395"><span>    $('httpAlert').classList.remove('hidden');
</span></span><span id="line1396"><span>    $('btnConnect').disabled = true;
</span></span><span id="line1397"><span>    // httpDesc uses innerHTML because it contains </span><span>&lt;s</span><span>trong&gt; and </span><span>&lt;c</span><span>ode&gt;
</span></span><span id="line1398"><span>    $('httpDesc').innerHTML = t('httpDesc');
</span></span><span id="line1399"><span>    log(t('httpTitle'), 'error');
</span></span><span id="line1400"><span>    return;
</span></span><span id="line1401"><span>  }
</span></span><span id="line1402"><span>
</span></span><span id="line1403"><span>  if (!navigator.bluetooth) {
</span></span><span id="line1404"><span>    $('noBleAlert').classList.remove('hidden');
</span></span><span id="line1405"><span>    $('btnConnect').disabled = true;
</span></span><span id="line1406"><span>    log(t('noBTTitle'), 'error');
</span></span><span id="line1407"><span>  } else {
</span></span><span id="line1408"><span>    log(t('logBTReady'), 'accent');
</span></span><span id="line1409"><span>  }
</span></span><span id="line1410"><span>}
</span></span><span id="line1411"><span>
</span></span><span id="line1412"><span>async function connectBLE() {
</span></span><span id="line1413"><span>  try {
</span></span><span id="line1414"><span>    setStatus(t('stScanning'),'scanning');
</span></span><span id="line1415"><span>    log(t('logScanning'),'accent');
</span></span><span id="line1416"><span>
</span></span><span id="line1417"><span>    // Only declare the DIS *service* UUID in optionalServices.
</span></span><span id="line1418"><span>    // Do NOT list individual DIS characteristic UUIDs here — some (like 0x2a25)
</span></span><span id="line1419"><span>    // are in Chrome's GATT blocklist and will cause requestDevice to throw.
</span></span><span id="line1420"><span>    device = await navigator.bluetooth.requestDevice({
</span></span><span id="line1421"><span>      filters: [{ services: [OTA_SVC] }],
</span></span><span id="line1422"><span>      optionalServices: ['0000180a-0000-1000-8000-00805f9b34fb']
</span></span><span id="line1423"><span>    });
</span></span><span id="line1424"><span>
</span></span><span id="line1425"><span>    device.addEventListener('gattserverdisconnected', onDisc);
</span></span><span id="line1426"><span>    setStatus(t('stConnecting'), 'scanning');
</span></span><span id="line1427"><span>    server = await device.gatt.connect();
</span></span><span id="line1428"><span>    log(`${t('logFound')}: ${device.name || 'Unknown'}`, 'success');
</span></span><span id="line1429"><span>
</span></span><span id="line1430"><span>    const otaSvc = await server.getPrimaryService(OTA_SVC);
</span></span><span id="line1431"><span>    recvChar = await otaSvc.getCharacteristic(RECV_CHAR);
</span></span><span id="line1432"><span>    cmdChar  = await otaSvc.getCharacteristic(CMD_CHAR);
</span></span><span id="line1433"><span>    await cmdChar.startNotifications();
</span></span><span id="line1434"><span>    cmdChar.addEventListener('characteristicvaluechanged', onCmdNotify);
</span></span><span id="line1435"><span>    await recvChar.startNotifications();
</span></span><span id="line1436"><span>    recvChar.addEventListener('characteristicvaluechanged', onFwNotify);
</span></span><span id="line1437"><span>
</span></span><span id="line1438"><span>    // ── MTU probe ──
</span></span><span id="line1439"><span>    // Web Bluetooth doesn't expose the negotiated MTU, so we probe it by
</span></span><span id="line1440"><span>    // attempting writeValueWithoutResponse with decreasing sizes until it
</span></span><span id="line1441"><span>    // succeeds. This is critical on PC where BLE adapters often use small MTU.
</span></span><span id="line1442"><span>    mtuPayload = await probeMTU(recvChar);
</span></span><span id="line1443"><span>    log(`MTU probe → payload=${mtuPayload}B/packet`, 'accent');
</span></span><span id="line1444"><span>
</span></span><span id="line1445"><span>    // Read DIS — use full 128-bit UUID strings
</span></span><span id="line1446"><span>    try {
</span></span><span id="line1447"><span>      const dis = await server.getPrimaryService('0000180a-0000-1000-8000-00805f9b34fb');
</span></span><span id="line1448"><span>      await readDIS(dis);
</span></span><span id="line1449"><span>    } catch(e) {
</span></span><span id="line1450"><span>      log(`${t('logDISNo')}: ${e.message}`, 'warn');
</span></span><span id="line1451"><span>    }
</span></span><span id="line1452"><span>
</span></span><span id="line1453"><span>    $('dName').textContent = device.name || 'Unknown';
</span></span><span id="line1454"><span>    $('devGrid').classList.remove('hidden');
</span></span><span id="line1455"><span>    $('btnConnect').classList.add('hidden');
</span></span><span id="line1456"><span>    $('btnDisconnect').classList.remove('hidden');
</span></span><span id="line1457"><span>    setStatus(`${t('stConnected')} · ${device.name || 'Unknown'}`, 'connected');
</span></span><span id="line1458"><span>    updateStartBtn();
</span></span><span id="line1459"><span>  } catch(e) {
</span></span><span id="line1460"><span>    setStatus(t('stConnFailed'), 'error');
</span></span><span id="line1461"><span>    log(`${t('logError')}: ${e.message}`, 'error');
</span></span><span id="line1462"><span>    device = null;
</span></span><span id="line1463"><span>  }
</span></span><span id="line1464"><span>}
</span></span><span id="line1465"><span>
</span></span><span id="line1466"><span>async function readDIS(svc) {
</span></span><span id="line1467"><span>  // Note: 0x2a25 (Serial Number) is blocklisted by Chrome Web Bluetooth API
</span></span><span id="line1468"><span>  // for privacy reasons (fingerprinting protection) — we skip it entirely.
</span></span><span id="line1469"><span>  const map = [
</span></span><span id="line1470"><span>    ['dModel', '00002a24-0000-1000-8000-00805f9b34fb', 'Model'],
</span></span><span id="line1471"><span>    ['dFW',    '00002a26-0000-1000-8000-00805f9b34fb', 'Firmware'],
</span></span><span id="line1472"><span>    ['dHW',    '00002a27-0000-1000-8000-00805f9b34fb', 'Hardware'],
</span></span><span id="line1473"><span>    ['dMfr',   '00002a29-0000-1000-8000-00805f9b34fb', 'Manufacturer'],
</span></span><span id="line1474"><span>  ];
</span></span><span id="line1475"><span>
</span></span><span id="line1476"><span>  for (const [id, uuid, label] of map) {
</span></span><span id="line1477"><span>    try {
</span></span><span id="line1478"><span>      const char = await svc.getCharacteristic(uuid);
</span></span><span id="line1479"><span>      const raw  = await char.readValue();
</span></span><span id="line1480"><span>      const v    = new TextDecoder('utf-8')
</span></span><span id="line1481"><span>                     .decode(raw)
</span></span><span id="line1482"><span>                     .replace(/\0/g, '')
</span></span><span id="line1483"><span>                     .trim();
</span></span><span id="line1484"><span>      $(id).textContent = v || '—';
</span></span><span id="line1485"><span>      log(`DIS ${label}: "${v}"`, v ? 'success' : 'info');
</span></span><span id="line1486"><span>    } catch(e) {
</span></span><span id="line1487"><span>      // Silently skip unavailable characteristics (blocklisted or not present)
</span></span><span id="line1488"><span>      $(id).textContent = '—';
</span></span><span id="line1489"><span>    }
</span></span><span id="line1490"><span>  }
</span></span><span id="line1491"><span>
</span></span><span id="line1492"><span>  // Serial Number (0x2a25) is blocklisted by Chrome — mark as N/A
</span></span><span id="line1493"><span>  $('dSerial').textContent = 'N/A';
</span></span><span id="line1494"><span>}
</span></span><span id="line1495"><span>
</span></span><span id="line1496"><span>function onDisc() {
</span></span><span id="line1497"><span>  setStatus(t('stError'),'error');
</span></span><span id="line1498"><span>  log(t('logDisconn'),'warn');
</span></span><span id="line1499"><span>  resetUI();
</span></span><span id="line1500"><span>  if(uploading) abortFlag=true;
</span></span><span id="line1501"><span>}
</span></span><span id="line1502"><span>
</span></span><span id="line1503"><span>function disconnectBLE() {
</span></span><span id="line1504"><span>  if(device?.gatt?.connected) device.gatt.disconnect();
</span></span><span id="line1505"><span>  resetUI();
</span></span><span id="line1506"><span>  log(t('logDisconnMan'),'warn');
</span></span><span id="line1507"><span>}
</span></span><span id="line1508"><span>
</span></span><span id="line1509"><span>function resetUI() {
</span></span><span id="line1510"><span>  device=server=recvChar=cmdChar=null;
</span></span><span id="line1511"><span>  mtuPayload = PKT_PLOAD;
</span></span><span id="line1512"><span>  $('btnConnect').classList.remove('hidden');
</span></span><span id="line1513"><span>  $('btnDisconnect').classList.add('hidden');
</span></span><span id="line1514"><span>  $('devGrid').classList.add('hidden');
</span></span><span id="line1515"><span>  ['dName','dModel','dSerial','dFW','dHW','dMfr'].forEach(id=&gt;$(id).textContent='—');
</span></span><span id="line1516"><span>  setStatus(t('stDisconnected'),'');
</span></span><span id="line1517"><span>  updateStartBtn();
</span></span><span id="line1518"><span>}
</span></span><span id="line1519"><span>
</span></span><span id="line1520"><span>// ════════════════════════════════════════════════
</span></span><span id="line1521"><span>// File
</span></span><span id="line1522"><span>// ════════════════════════════════════════════════
</span></span><span id="line1523"><span>function setOtaType(tp) {
</span></span><span id="line1524"><span>  otaType=tp;
</span></span><span id="line1525"><span>  $('btnFlash').classList.toggle('active',tp==='flash');
</span></span><span id="line1526"><span>  $('btnSpiffs').classList.toggle('active',tp==='spiffs');
</span></span><span id="line1527"><span>  log(`${t('logOtaType')}: ${tp.toUpperCase()}`,'info');
</span></span><span id="line1528"><span>}
</span></span><span id="line1529"><span>
</span></span><span id="line1530"><span>function onFilePick(e) { if(e.target.files[0]) selectFile(e.target.files[0]); }
</span></span><span id="line1531"><span>
</span></span><span id="line1532"><span>function selectFile(f) {
</span></span><span id="line1533"><span>  file=f;
</span></span><span id="line1534"><span>  $('fileBadge').classList.remove('hidden');
</span></span><span id="line1535"><span>  $('fileName').textContent=f.name;
</span></span><span id="line1536"><span>  $('fileSize').textContent=fmtBytes(f.size);
</span></span><span id="line1537"><span>  log(`File: ${f.name} (${fmtBytes(f.size)})`,'success');
</span></span><span id="line1538"><span>  updateStartBtn();
</span></span><span id="line1539"><span>}
</span></span><span id="line1540"><span>
</span></span><span id="line1541"><span>const dz=$('dropzone');
</span></span><span id="line1542"><span>dz.addEventListener('dragover',e=&gt;{e.preventDefault();dz.classList.add('over');});
</span></span><span id="line1543"><span>dz.addEventListener('dragleave',()=&gt;dz.classList.remove('over'));
</span></span><span id="line1544"><span>dz.addEventListener('drop',e=&gt;{
</span></span><span id="line1545"><span>  e.preventDefault();dz.classList.remove('over');
</span></span><span id="line1546"><span>  const f=e.dataTransfer.files[0];
</span></span><span id="line1547"><span>  f?.name.endsWith('.bin')?selectFile(f):log(t('logFileInvalid'),'error');
</span></span><span id="line1548"><span>});
</span></span><span id="line1549"><span>
</span></span><span id="line1550"><span>// ════════════════════════════════════════════════
</span></span><span id="line1551"><span>// Protocol
</span></span><span id="line1552"><span>// ════════════════════════════════════════════════
</span></span><span id="line1553"><span>
</span></span><span id="line1554"><span>// CRC16 CCITT — accepts optional init value (default 0), matches React app
</span></span><span id="line1555"><span>function crc16(data, init = 0) {
</span></span><span id="line1556"><span>  let c = init;
</span></span><span id="line1557"><span>  for (let i = 0; i </span><span>&lt; </span><span>data.length; i++) {
</span></span><span id="line1558"><span>    c ^= data[i] </span><span>&lt;&lt;</span><span></span><span> </span><span>8;
</span></span><span id="line1559"><span>    for (let j = 0; j </span><span>&lt; </span><span>8; j++) {
</span></span><span id="line1560"><span>      c = (c &amp; 0x8000) ? ((c </span><span>&lt;&lt;</span><span></span><span> </span><span>1) ^ 0x1021) &amp; 0xffff : (c </span><span>&lt;&lt;</span><span></span><span> </span><span>1) &amp; 0xffff;
</span></span><span id="line1561"><span>    }
</span></span><span id="line1562"><span>  }
</span></span><span id="line1563"><span>  return c &amp; 0xffff;
</span></span><span id="line1564"><span>}
</span></span><span id="line1565"><span>
</span></span><span id="line1566"><span>// Incremental CRC — same as React: crc16(prevCrc, chunk, len)
</span></span><span id="line1567"><span>// Keeps running CRC across multiple chunks of a sector.
</span></span><span id="line1568"><span>function crc16incr(prev, chunk) {
</span></span><span id="line1569"><span>  return crc16(chunk, prev);
</span></span><span id="line1570"><span>}
</span></span><span id="line1571"><span>
</span></span><span id="line1572"><span>// ACK state — use simple flags like the React app (not Promise-based)
</span></span><span id="line1573"><span>let cmdStatus  = 0;   // 0=waiting, 1=ok, -1=nack, -2=signature error
</span></span><span id="line1574"><span>let cmdErrMsg  = '';  // human-readable reason for cmdStatus </span><span>&lt; </span><span>0
</span></span><span id="line1575"><span>let expectedCmd = 0;  // which command ID we are waiting ACK for
</span></span><span id="line1576"><span>let fwStatus   = 0;   // 0=waiting, 1=ok, -1=nack
</span></span><span id="line1577"><span>let expectedSector = 0;
</span></span><span id="line1578"><span>
</span></span><span id="line1579"><span>function onCmdNotify(e) {
</span></span><span id="line1580"><span>  const d = new DataView(e.target.value.buffer);
</span></span><span id="line1581"><span>  if (d.byteLength </span><span>&lt; </span><span>20) return;
</span></span><span id="line1582"><span>  const crcRecv = d.getUint16(18, true);
</span></span><span id="line1583"><span>  const buf = new Uint8Array(d.buffer, 0, 18);
</span></span><span id="line1584"><span>  if (crc16(buf) !== crcRecv) return;
</span></span><span id="line1585"><span>  if (d.getUint16(0, true) === CMD_ACK) {
</span></span><span id="line1586"><span>    const forCmd = d.getUint16(2, true);
</span></span><span id="line1587"><span>    const ans    = d.getUint16(4, true);
</span></span><span id="line1588"><span>
</span></span><span id="line1589"><span>    // Ignore ACKs for commands we are not currently waiting for
</span></span><span id="line1590"><span>    if (forCmd !== expectedCmd) {
</span></span><span id="line1591"><span>      log(`CMD_ACK ignored (forCmd=0x${forCmd.toString(16)} expected=0x${expectedCmd.toString(16)})`, 'info');
</span></span><span id="line1592"><span>      return;
</span></span><span id="line1593"><span>    }
</span></span><span id="line1594"><span>
</span></span><span id="line1595"><span>    if (ans === 0) {
</span></span><span id="line1596"><span>      cmdStatus = 1;
</span></span><span id="line1597"><span>      cmdErrMsg = '';
</span></span><span id="line1598"><span>      log(`CMD_ACK ok (cmd=0x${forCmd.toString(16)})`, 'success');
</span></span><span id="line1599"><span>    } else if (ans === 3) {
</span></span><span id="line1600"><span>      // Signature error — ESP32 rejected firmware after RSA verification
</span></span><span id="line1601"><span>      cmdStatus = -2;
</span></span><span id="line1602"><span>      cmdErrMsg = t('errSignature');
</span></span><span id="line1603"><span>      logForce(`CMD_ACK: ${cmdErrMsg} (cmd=0x${forCmd.toString(16)})`, 'error');
</span></span><span id="line1604"><span>    } else {
</span></span><span id="line1605"><span>      cmdStatus = -1;
</span></span><span id="line1606"><span>      cmdErrMsg = t('errNack');
</span></span><span id="line1607"><span>      logForce(`CMD_ACK NACK (cmd=0x${forCmd.toString(16)} ans=0x${ans.toString(16)})`, 'error');
</span></span><span id="line1608"><span>    }
</span></span><span id="line1609"><span>  }
</span></span><span id="line1610"><span>}
</span></span><span id="line1611"><span>
</span></span><span id="line1612"><span>function onFwNotify(e) {
</span></span><span id="line1613"><span>  const d = new DataView(e.target.value.buffer);
</span></span><span id="line1614"><span>  if (d.byteLength </span><span>&lt; </span><span>4) return;
</span></span><span id="line1615"><span>  const sector = d.getUint16(0, true);
</span></span><span id="line1616"><span>  const ack    = d.getUint16(2, true);
</span></span><span id="line1617"><span>  if (sector !== expectedSector) return;
</span></span><span id="line1618"><span>  if (ack === 0) {
</span></span><span id="line1619"><span>    fwStatus = 1;
</span></span><span id="line1620"><span>  } else {
</span></span><span id="line1621"><span>    fwStatus = -1;
</span></span><span id="line1622"><span>    const errMap = { 1: 'CRC error', 2: `Index error (want ${d.byteLength&gt;=6?d.getUint16(4,true):'?'})`, 3: 'Payload length error', 5: 'Cannot start OTA' };
</span></span><span id="line1623"><span>    logForce(`FW NACK sector ${sector}: ${errMap[ack] || `0x${ack.toString(16)}`}`, 'error');
</span></span><span id="line1624"><span>  }
</span></span><span id="line1625"><span>}
</span></span><span id="line1626"><span>
</span></span><span id="line1627"><span>// Returns a Promise that resolves on ACK ok, rejects with error message on nack/signature/timeout
</span></span><span id="line1628"><span>function waitForCmd(ms = 15000) {
</span></span><span id="line1629"><span>  return new Promise((resolve, reject) =&gt; {
</span></span><span id="line1630"><span>    if (cmdStatus === 1)  { resolve(); return; }
</span></span><span id="line1631"><span>    if (cmdStatus </span><span>&lt; </span><span>0)    { reject(new Error(cmdErrMsg)); return; }
</span></span><span id="line1632"><span>    const iv = setInterval(() =&gt; {
</span></span><span id="line1633"><span>      if (cmdStatus === 1)  { clearInterval(iv); resolve(); }
</span></span><span id="line1634"><span>      else if (cmdStatus </span><span>&lt; </span><span>0) { clearInterval(iv); reject(new Error(cmdErrMsg)); }
</span></span><span id="line1635"><span>    }, 50);
</span></span><span id="line1636"><span>    setTimeout(() =&gt; {
</span></span><span id="line1637"><span>      clearInterval(iv);
</span></span><span id="line1638"><span>      if (cmdStatus === 0) reject(new Error(t('errCmdTimeout')));
</span></span><span id="line1639"><span>    }, ms);
</span></span><span id="line1640"><span>  });
</span></span><span id="line1641"><span>}
</span></span><span id="line1642"><span>
</span></span><span id="line1643"><span>// Generous timeout for FW ACK — BLE on mobile + ESP32 flash write can be slow
</span></span><span id="line1644"><span>function waitForFw(ms = 60000) {
</span></span><span id="line1645"><span>  return new Promise((resolve) =&gt; {
</span></span><span id="line1646"><span>    if (fwStatus !== 0) { resolve(fwStatus === 1); return; }
</span></span><span id="line1647"><span>    const iv = setInterval(() =&gt; {
</span></span><span id="line1648"><span>      if (fwStatus !== 0) { clearInterval(iv); resolve(fwStatus === 1); }
</span></span><span id="line1649"><span>    }, 20);
</span></span><span id="line1650"><span>    setTimeout(() =&gt; { clearInterval(iv); resolve(false); }, ms);
</span></span><span id="line1651"><span>  });
</span></span><span id="line1652"><span>}
</span></span><span id="line1653"><span>
</span></span><span id="line1654"><span>// ── MTU probe ──
</span></span><span id="line1655"><span>// Finds the largest writeValueWithoutResponse payload that succeeds.
</span></span><span id="line1656"><span>// The OTA packet has a 3-byte header, so usable payload = probed_size - 3.
</span></span><span id="line1657"><span>async function probeMTU(char) {
</span></span><span id="line1658"><span>  return 247; const candidates = [510, 247, 185, 122, 23];
</span></span><span id="line1659"><span>  for (const size of candidates) {
</span></span><span id="line1660"><span>    try {
</span></span><span id="line1661"><span>      await char.writeValueWithoutResponse(new Uint8Array(size));
</span></span><span id="line1662"><span>      return size - 3; // subtract 3-byte OTA header → usable payload
</span></span><span id="line1663"><span>    } catch {
</span></span><span id="line1664"><span>      // BLE stack rejected this size — try smaller
</span></span><span id="line1665"><span>    }
</span></span><span id="line1666"><span>  }
</span></span><span id="line1667"><span>  return 20; // 23 - 3 header = 20 bytes absolute minimum
</span></span><span id="line1668"><span>}
</span></span><span id="line1669"><span>
</span></span><span id="line1670"><span>function buildCmd(id, payload = []) {
</span></span><span id="line1671"><span>  const b = new Uint8Array(20);
</span></span><span id="line1672"><span>  b[0] = id &amp; 0xFF; b[1] = (id &gt;&gt; 8) &amp; 0xFF;
</span></span><span id="line1673"><span>  payload.forEach((v, i) =&gt; { if (i </span><span>&lt; </span><span>16) b[2 + i] = v; });
</span></span><span id="line1674"><span>  const c = crc16(b.slice(0, 18));
</span></span><span id="line1675"><span>  b[18] = c &amp; 0xFF; b[19] = (c &gt;&gt; 8) &amp; 0xFF;
</span></span><span id="line1676"><span>  return b;
</span></span><span id="line1677"><span>}
</span></span><span id="line1678"><span>
</span></span><span id="line1679"><span>// Pre-build all BLE packets for one sector.
</span></span><span id="line1680"><span>// Returns an array of Uint8Array ready to send with writeValueWithoutResponse.
</span></span><span id="line1681"><span>function buildSectorPackets(sectorData, secIdx) {
</span></span><span id="line1682"><span>  const packets = [];
</span></span><span id="line1683"><span>  let sectorSize = 0;
</span></span><span id="line1684"><span>  let sequence   = 0;
</span></span><span id="line1685"><span>  let crc        = 0;
</span></span><span id="line1686"><span>
</span></span><span id="line1687"><span>  while (sectorSize </span><span>&lt; </span><span>sectorData.length) {
</span></span><span id="line1688"><span>    let toRead = mtuPayload;
</span></span><span id="line1689"><span>    if (sectorSize + toRead &gt; sectorData.length) toRead = sectorData.length - sectorSize;
</span></span><span id="line1690"><span>
</span></span><span id="line1691"><span>    const chunk   = sectorData.slice(sectorSize, sectorSize + toRead);
</span></span><span id="line1692"><span>    sectorSize   += toRead;
</span></span><span id="line1693"><span>    const fLast   = sectorSize &gt;= sectorData.length || sectorSize &gt;= SECTOR_SZ;
</span></span><span id="line1694"><span>
</span></span><span id="line1695"><span>    // Incremental CRC on actual bytes sent (same as React app)
</span></span><span id="line1696"><span>    crc = crc16incr(crc, chunk);
</span></span><span id="line1697"><span>
</span></span><span id="line1698"><span>    let pkt;
</span></span><span id="line1699"><span>    if (fLast) {
</span></span><span id="line1700"><span>      pkt = new Uint8Array(3 + chunk.length + 2);
</span></span><span id="line1701"><span>      pkt[0] = secIdx &amp; 0xFF;
</span></span><span id="line1702"><span>      pkt[1] = (secIdx &gt;&gt; 8) &amp; 0xFF;
</span></span><span id="line1703"><span>      pkt[2] = 0xFF; // last packet marker
</span></span><span id="line1704"><span>      pkt.set(chunk, 3);
</span></span><span id="line1705"><span>      pkt[3 + chunk.length]     = crc &amp; 0xFF;
</span></span><span id="line1706"><span>      pkt[3 + chunk.length + 1] = (crc &gt;&gt; 8) &amp; 0xFF;
</span></span><span id="line1707"><span>    } else {
</span></span><span id="line1708"><span>      pkt = new Uint8Array(3 + chunk.length);
</span></span><span id="line1709"><span>      pkt[0] = secIdx &amp; 0xFF;
</span></span><span id="line1710"><span>      pkt[1] = (secIdx &gt;&gt; 8) &amp; 0xFF;
</span></span><span id="line1711"><span>      pkt[2] = sequence &amp; 0xFF;
</span></span><span id="line1712"><span>      pkt.set(chunk, 3);
</span></span><span id="line1713"><span>    }
</span></span><span id="line1714"><span>
</span></span><span id="line1715"><span>    packets.push(pkt);
</span></span><span id="line1716"><span>    sequence++;
</span></span><span id="line1717"><span>  }
</span></span><span id="line1718"><span>
</span></span><span id="line1719"><span>  return packets;
</span></span><span id="line1720"><span>}
</span></span><span id="line1721"><span>
</span></span><span id="line1722"><span>// ════════════════════════════════════════════════
</span></span><span id="line1723"><span>// OTA — ported faithfully from working React app
</span></span><span id="line1724"><span>// ════════════════════════════════════════════════
</span></span><span id="line1725"><span>async function startOTA() {
</span></span><span id="line1726"><span>  if (!device || !file || uploading) return;
</span></span><span id="line1727"><span>  uploading = true; abortFlag = false;
</span></span><span id="line1728"><span>  $('btnStart').classList.add('hidden');
</span></span><span id="line1729"><span>  $('btnAbort').classList.remove('hidden');
</span></span><span id="line1730"><span>  $('successBox').classList.remove('show');
</span></span><span id="line1731"><span>  $('progSection').classList.remove('hidden');
</span></span><span id="line1732"><span>  setStatus(t('stUploading'), 'uploading');
</span></span><span id="line1733"><span>  updateProg(0, file.size, 0);
</span></span><span id="line1734"><span>  txStart = Date.now();
</span></span><span id="line1735"><span>
</span></span><span id="line1736"><span>  try {
</span></span><span id="line1737"><span>    const data  = new Uint8Array(await file.arrayBuffer());
</span></span><span id="line1738"><span>    const total = data.length;
</span></span><span id="line1739"><span>    const cmdId = otaType === 'flash' ? CMD_FLASH : CMD_SPIFFS;
</span></span><span id="line1740"><span>
</span></span><span id="line1741"><span>    // ── Send START command ──
</span></span><span id="line1742"><span>    const startCmd = buildCmd(cmdId, [
</span></span><span id="line1743"><span>      total &amp; 0xFF, (total &gt;&gt; 8) &amp; 0xFF,
</span></span><span id="line1744"><span>      (total &gt;&gt; 16) &amp; 0xFF, (total &gt;&gt; 24) &amp; 0xFF
</span></span><span id="line1745"><span>    ]);
</span></span><span id="line1746"><span>    cmdStatus = 0; cmdErrMsg = '';
</span></span><span id="line1747"><span>    expectedCmd = cmdId; // expect ACK for START (0x0001 or 0x0004)
</span></span><span id="line1748"><span>    await cmdChar.writeValueWithoutResponse(startCmd);
</span></span><span id="line1749"><span>    log(`${t('logStartOTA')} ${otaType.toUpperCase()} size=${total}`, 'accent');
</span></span><span id="line1750"><span>
</span></span><span id="line1751"><span>    // Wait for START ACK — abort on any failure (NACK, signature error, timeout)
</span></span><span id="line1752"><span>    try {
</span></span><span id="line1753"><span>      await waitForCmd(15000);
</span></span><span id="line1754"><span>      log(t('logOtaAccepted'), 'success');
</span></span><span id="line1755"><span>    } catch(e) {
</span></span><span id="line1756"><span>      throw new Error(`${t('errStartFailed')}: ${e.message}`);
</span></span><span id="line1757"><span>    }
</span></span><span id="line1758"><span>
</span></span><span id="line1759"><span>    // ── Send firmware sector by sector ── 
</span></span><span id="line1760"><span>    // Strategy: send all packets of a sector as fast as possible (burst),
</span></span><span id="line1761"><span>    // then wait for ACK. If CRC error or timeout → retry the sector (max 3x).
</span></span><span id="line1762"><span>    // This is fast on all platforms and self-healing on lossy BLE connections.
</span></span><span id="line1763"><span>    let writtenSize = 0;
</span></span><span id="line1764"><span>    const MAX_RETRIES = 3;
</span></span><span id="line1765"><span>
</span></span><span id="line1766"><span>    while (writtenSize </span><span>&lt; </span><span>total &amp;&amp; !abortFlag) {
</span></span><span id="line1767"><span>      const sector = data.slice(writtenSize, writtenSize + SECTOR_SZ);
</span></span><span id="line1768"><span>      if (sector.length === 0) break;
</span></span><span id="line1769"><span>
</span></span><span id="line1770"><span>      const secIdx = Math.floor(writtenSize / SECTOR_SZ);
</span></span><span id="line1771"><span>
</span></span><span id="line1772"><span>      // Pre-build all packets for this sector so we can resend quickly on retry
</span></span><span id="line1773"><span>      const packets = buildSectorPackets(sector, secIdx);
</span></span><span id="line1774"><span>
</span></span><span id="line1775"><span>      let success = false;
</span></span><span id="line1776"><span>      for (let attempt = 0; attempt </span><span>&lt; </span><span>MAX_RETRIES &amp;&amp; !abortFlag; attempt++) {
</span></span><span id="line1777"><span>        if (attempt &gt; 0) {
</span></span><span id="line1778"><span>          log(`Retry sector ${secIdx} (attempt ${attempt + 1})`, 'warn');
</span></span><span id="line1779"><span>          await new Promise(r =&gt; setTimeout(r, 200)); // small pause before retry
</span></span><span id="line1780"><span>        }
</span></span><span id="line1781"><span>
</span></span><span id="line1782"><span>        // Reset ACK state before sending last packet
</span></span><span id="line1783"><span>        fwStatus       = 0;
</span></span><span id="line1784"><span>        expectedSector = secIdx;
</span></span><span id="line1785"><span>
</span></span><span id="line1786"><span>        // Send all packets in burst — writeValueWithoutResponse is fire-and-forget
</span></span><span id="line1787"><span>        for (let i = 0; i </span><span>&lt; </span><span>packets.length; i++) {
</span></span><span id="line1788"><span>          await recvChar.writeValueWithoutResponse(packets[i]);
</span></span><span id="line1789"><span>          // Tiny yield to let the JS event loop process BLE notifications
</span></span><span id="line1790"><span>          // without adding real latency — avoids starving the notification handler
</span></span><span id="line1791"><span>          if (i % 8 === 7) await new Promise(r =&gt; setTimeout(r, 0));
</span></span><span id="line1792"><span>        }
</span></span><span id="line1793"><span>
</span></span><span id="line1794"><span>        // Wait for sector ACK
</span></span><span id="line1795"><span>        const fwOk = await waitForFw(15000);
</span></span><span id="line1796"><span>        if (fwOk) {
</span></span><span id="line1797"><span>          success = true;
</span></span><span id="line1798"><span>          break;
</span></span><span id="line1799"><span>        }
</span></span><span id="line1800"><span>        // fwStatus -1 = NACK (CRC/index error), 0 = timeout — both trigger retry
</span></span><span id="line1801"><span>      }
</span></span><span id="line1802"><span>
</span></span><span id="line1803"><span>      if (!success) {
</span></span><span id="line1804"><span>        throw new Error(`Sector ${secIdx} failed after ${MAX_RETRIES} attempts`);
</span></span><span id="line1805"><span>      }
</span></span><span id="line1806"><span>
</span></span><span id="line1807"><span>      writtenSize += sector.length;
</span></span><span id="line1808"><span>      const elapsed = (Date.now() - txStart) / 1000;
</span></span><span id="line1809"><span>      const speed   = elapsed &gt; 0 ? writtenSize / elapsed : 0;
</span></span><span id="line1810"><span>      const eta     = speed &gt; 0 ? (total - writtenSize) / speed : 0;
</span></span><span id="line1811"><span>      updateProg(writtenSize, total, secIdx + 1, speed, eta);
</span></span><span id="line1812"><span>      log(`${t('logSectorOK')} ${secIdx + 1} — ${fmtBytes(writtenSize)}/${fmtBytes(total)}`, 'success');
</span></span><span id="line1813"><span>
</span></span><span id="line1814"><span>      if (abortFlag) break;
</span></span><span id="line1815"><span>    }
</span></span><span id="line1816"><span>
</span></span><span id="line1817"><span>    if (abortFlag) {
</span></span><span id="line1818"><span>      await cmdChar.writeValueWithoutResponse(buildCmd(CMD_STOP));
</span></span><span id="line1819"><span>      log(t('logAborted'), 'warn');
</span></span><span id="line1820"><span>      setStatus(t('stAborted'), 'error');
</span></span><span id="line1821"><span>      try { device.gatt.disconnect(); } catch {}
</span></span><span id="line1822"><span>    } else {
</span></span><span id="line1823"><span>      // Send STOP — ESP32 verifies signature here (if secure OTA)
</span></span><span id="line1824"><span>      cmdStatus = 0; cmdErrMsg = '';
</span></span><span id="line1825"><span>      expectedCmd = CMD_STOP; // expect ACK for STOP (0x0002) — signature verified here
</span></span><span id="line1826"><span>      await cmdChar.writeValueWithoutResponse(buildCmd(CMD_STOP));
</span></span><span id="line1827"><span>      log('STOP inviato, attendo conferma…', 'info');
</span></span><span id="line1828"><span>
</span></span><span id="line1829"><span>      try {
</span></span><span id="line1830"><span>        await waitForCmd(15000);
</span></span><span id="line1831"><span>        // ACK ok → device reboots with new firmware
</span></span><span id="line1832"><span>        await new Promise(r =&gt; setTimeout(r, 500));
</span></span><span id="line1833"><span>        try { device.gatt.disconnect(); } catch {}
</span></span><span id="line1834"><span>        log(t('logOtaDone'), 'success');
</span></span><span id="line1835"><span>        setStatus(t('stCompleted'), 'connected');
</span></span><span id="line1836"><span>        $('progSection').classList.add('hidden');
</span></span><span id="line1837"><span>        $('successBox').classList.add('show');
</span></span><span id="line1838"><span>      } catch(e) {
</span></span><span id="line1839"><span>        // STOP rejected — most likely signature verification failed on ESP32
</span></span><span id="line1840"><span>        try { device.gatt.disconnect(); } catch {}
</span></span><span id="line1841"><span>        throw new Error(`${t('errStopFailed')}: ${e.message}`);
</span></span><span id="line1842"><span>      }
</span></span><span id="line1843"><span>    }
</span></span><span id="line1844"><span>
</span></span><span id="line1845"><span>  } catch(e) {
</span></span><span id="line1846"><span>    logForce(`${t('logError')}: ${e.message}`, 'error');
</span></span><span id="line1847"><span>    setStatus(e.message, 'error');
</span></span><span id="line1848"><span>    try { await cmdChar.writeValueWithoutResponse(buildCmd(CMD_STOP)); } catch {}
</span></span><span id="line1849"><span>    try { device.gatt.disconnect(); } catch {}
</span></span><span id="line1850"><span>  }
</span></span><span id="line1851"><span>
</span></span><span id="line1852"><span>  uploading = false; abortFlag = false;
</span></span><span id="line1853"><span>  $('btnStart').classList.remove('hidden');
</span></span><span id="line1854"><span>  $('btnAbort').classList.add('hidden');
</span></span><span id="line1855"><span>  updateStartBtn();
</span></span><span id="line1856"><span>}
</span></span><span id="line1857"><span>
</span></span><span id="line1858"><span>function abortOTA(){abortFlag=true;log(t('logAbort'),'warn');}
</span></span><span id="line1859"><span>
</span></span><span id="line1860"><span>function updateProg(sent,total,sec,speed,eta) {
</span></span><span id="line1861"><span>  const p=total&gt;0?Math.round(sent/total*100):0;
</span></span><span id="line1862"><span>  $('progFill').style.width=p+'%';
</span></span><span id="line1863"><span>  $('progPct').textContent=p+'%';
</span></span><span id="line1864"><span>  $('sSent').textContent=fmtBytes(sent);
</span></span><span id="line1865"><span>  $('sTotal').textContent=fmtBytes(total);
</span></span><span id="line1866"><span>  $('sSector').textContent=sec;
</span></span><span id="line1867"><span>  $('sSpeed').textContent=speed!=null&amp;&amp;speed&gt;0?fmtBytes(Math.round(speed))+'/s':'—';
</span></span><span id="line1868"><span>  $('sETA').textContent=eta!=null&amp;&amp;eta&gt;0?fmtTime(eta):'—';
</span></span><span id="line1869"><span>  $('progLabel').textContent=p</span><span>&lt;1</span><span>00?t('progTransferring'):t('progDone');
</span></span><span id="line1870"><span>}
</span></span><span id="line1871"><span>
</span></span><span id="line1872"><span>// ── Sync log height to left column ──
</span></span><span id="line1873"><span>// Uses ResizeObserver to automatically track col-left height changes
</span></span><span id="line1874"><span>// (device grid appearing, progress bar expanding, etc.)
</span></span><span id="line1875"><span>let _syncObserver = null;
</span></span><span id="line1876"><span>
</span></span><span id="line1877"><span>function syncLogHeight() {
</span></span><span id="line1878"><span>  if (window.innerWidth </span><span>&lt; </span><span>1024) return;
</span></span><span id="line1879"><span>
</span></span><span id="line1880"><span>  const colLeft    = $('colLeft');
</span></span><span id="line1881"><span>  const colRight   = $('colRight');
</span></span><span id="line1882"><span>  const logCard    = $('logCard');
</span></span><span id="line1883"><span>  const logWrap    = $('logEl');
</span></span><span id="line1884"><span>  const logDisabled= $('logDisabled');
</span></span><span id="line1885"><span>  if (!colLeft || !colRight || !logCard || !logWrap) return;
</span></span><span id="line1886"><span>
</span></span><span id="line1887"><span>  const leftH = colLeft.getBoundingClientRect().height;
</span></span><span id="line1888"><span>  if (leftH </span><span>&lt; </span><span>100) return;
</span></span><span id="line1889"><span>
</span></span><span id="line1890"><span>  colRight.style.height   = leftH + 'px';
</span></span><span id="line1891"><span>  logCard.style.height    = leftH + 'px';
</span></span><span id="line1892"><span>  logCard.style.boxSizing = 'border-box';
</span></span><span id="line1893"><span>
</span></span><span id="line1894"><span>  const style  = getComputedStyle(logCard);
</span></span><span id="line1895"><span>  const padTop = parseFloat(style.paddingTop);
</span></span><span id="line1896"><span>  const padBot = parseFloat(style.paddingBottom);
</span></span><span id="line1897"><span>  const labelEl= logCard.querySelector('.card-label');
</span></span><span id="line1898"><span>  const labelH = labelEl ? labelEl.getBoundingClientRect().height + 10 : 36;
</span></span><span id="line1899"><span>  const wrapH  = Math.max(80, leftH - padTop - padBot - labelH);
</span></span><span id="line1900"><span>
</span></span><span id="line1901"><span>  logWrap.style.height     = wrapH + 'px';
</span></span><span id="line1902"><span>  logWrap.style.maxHeight  = wrapH + 'px';
</span></span><span id="line1903"><span>  logWrap.style.flexShrink = '0';
</span></span><span id="line1904"><span>  logDisabled.style.height = wrapH + 'px';
</span></span><span id="line1905"><span>}
</span></span><span id="line1906"><span>
</span></span><span id="line1907"><span>function initSyncObserver() {
</span></span><span id="line1908"><span>  const colLeft = $('colLeft');
</span></span><span id="line1909"><span>  if (!colLeft) return;
</span></span><span id="line1910"><span>  if (_syncObserver) _syncObserver.disconnect();
</span></span><span id="line1911"><span>  _syncObserver = new ResizeObserver(() =&gt; {
</span></span><span id="line1912"><span>    if (window.innerWidth &gt;= 1024) syncLogHeight();
</span></span><span id="line1913"><span>  });
</span></span><span id="line1914"><span>  _syncObserver.observe(colLeft);
</span></span><span id="line1915"><span>}
</span></span><span id="line1916"><span>
</span></span><span id="line1917"><span>window.addEventListener('resize', () =&gt; {
</span></span><span id="line1918"><span>  if (window.innerWidth </span><span>&lt; </span><span>1024) {
</span></span><span id="line1919"><span>    // Reset inline styles on mobile so CSS takes over
</span></span><span id="line1920"><span>    const colRight = $('colRight');
</span></span><span id="line1921"><span>    const logCard  = $('logCard');
</span></span><span id="line1922"><span>    const logWrap  = $('logEl');
</span></span><span id="line1923"><span>    const logDis   = $('logDisabled');
</span></span><span id="line1924"><span>    if (colRight)  colRight.style.height   = '';
</span></span><span id="line1925"><span>    if (logCard)   { logCard.style.height  = ''; logCard.style.boxSizing = ''; }
</span></span><span id="line1926"><span>    if (logWrap)   { logWrap.style.height  = ''; logWrap.style.maxHeight = ''; }
</span></span><span id="line1927"><span>    if (logDis)    logDis.style.height     = '';
</span></span><span id="line1928"><span>  } else {
</span></span><span id="line1929"><span>    syncLogHeight();
</span></span><span id="line1930"><span>  }
</span></span><span id="line1931"><span>});
</span></span><span id="line1932"><span>applyTheme();
</span></span><span id="line1933"><span>applyLang();
</span></span><span id="line1934"><span>applyLogState();
</span></span><span id="line1935"><span>checkBT();
</span></span><span id="line1936"><span>setStatus(t('stDisconnected'),'');
</span></span><span id="line1937"><span>requestAnimationFrame(() =&gt; { initSyncObserver(); syncLogHeight(); });
</span></span><span id="line1938"><span></span><span>&lt;/<span class="end-tag">script</span>&gt;</span><span>
</span></span><span id="line1939"><span></span><span>&lt;/<span class="end-tag">body</span>&gt;</span><span>
</span></span><span id="line1940"><span></span><span>&lt;/<span class="end-tag">html</span>&gt;</span><span>
</span></span><span id="line1941"><span></span></span></body></html>
