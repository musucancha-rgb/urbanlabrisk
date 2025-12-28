<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DATOS | Urban Lab Risk Vol. 01</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Archivo+Black&family=Space+Grotesk:wght@500;700;800&display=swap" rel="stylesheet">
    
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    fontFamily: {
                        heading: ['Archivo Black', 'sans-serif'],
                        body: ['Space Grotesk', 'sans-serif'],
                    },
                    colors: {
                        mustard: '#FFDB58',
                        royal: '#002366',
                        street: '#1a1a1a',
                        accent: '#f43f5e',
                    },
                    boxShadow: {
                        'hard': '12px 12px 0px 0px #000000',
                        'hard-sm': '6px 6px 0px 0px #000000',
                    }
                }
            }
        }
    </script>
    
    <style>
        .comic-border { border: 4px solid #000000; }
        .halftone {
            background-image: radial-gradient(#002366 15%, transparent 15%);
            background-size: 8px 8px;
            opacity: 0.08;
        }

        /* Fixed 3D Flip System */
        .flip-card {
            perspective: 2000px;
            cursor: pointer;
            position: relative;
        }
        .flip-card-inner {
            position: relative;
            width: 100%;
            height: 100%;
            transition: transform 0.7s cubic-bezier(0.4, 0, 0.2, 1);
            transform-style: preserve-3d;
        }
        .flip-card.flipped .flip-card-inner {
            transform: rotateY(180deg);
        }
        .flip-card-front, .flip-card-back {
            position: absolute;
            width: 100%;
            height: 100%;
            -webkit-backface-visibility: hidden;
            backface-visibility: hidden;
            display: flex;
            flex-direction: column;
            border: 5px solid #000000;
            background: white;
            padding: 2rem;
        }
        .flip-card-back {
            transform: rotateY(180deg);
            z-index: 10;
        }

        /* CSS Flags (NO Borders) */
        .flag { width: 75px; height: 48px; border: none; flex-shrink: 0; position: relative; overflow: hidden; }
        .flag-eu { background: #003399; display: grid; grid-template-columns: repeat(3, 1fr); color: yellow; font-size: 11px; place-items: center; }
        .flag-it { display: flex; }
        .flag-it div { flex: 1; }
        .flag-it .g { background: #009246; }
        .flag-it .w { background: #ffffff; }
        .flag-it .r { background: #ce2b37; }
        .flag-tos { background: #ffffff; border-top: 14px solid #ce2b37; border-bottom: 14px solid #ce2b37; }
        .flag-fi { background: #ffffff; position: relative; }
        .flag-fi::after { content: "⚜"; color: #ce2b37; position: absolute; inset: 0; display: flex; justify-content: center; align-items: center; font-size: 32px; }

        /* Typography */
        h1 { font-size: clamp(4rem, 20vw, 12rem); line-height: 0.75; letter-spacing: -0.06em; }
        .card-header-text { font-size: clamp(1.8rem, 4.5vw, 2.8rem); line-height: 0.9; }
        
        .card-desc-text { font-size: 1.2rem; font-weight: 700; line-height: 1.3; }
        .card-nodes-text { font-size: 1.1rem; font-weight: 700; line-height: 1.3; }
        .data-front-hero { font-size: 4.5rem; line-height: 1; margin: 1rem 0; }

        /* Visual Mockups */
        .res-viz { height: 160px; border: 3px solid black; margin: 1.5rem 0; position: relative; overflow: hidden; }
        .wave-motion { position: absolute; bottom: 0; width: 200%; height: 60%; background: #002366; opacity: 0.15; animation: wave 4s linear infinite; }
        @keyframes wave { from { transform: translateX(0); } to { transform: translateX(-50%); } }

        .rank-chart { display: flex; align-items: flex-end; justify-content: space-around; height: 130px; padding: 10px; background: #fafafa; border: 2px solid black; }
        .rank-bar { background: #10b981; border: 2.5px solid black; width: 55px; }

        .tilt-l { transform: rotate(-1.5deg); }
        .tilt-r { transform: rotate(1.5deg); }

        .lang-btn.active {
            background-color: #000000;
            color: #FFDB58;
            box-shadow: 4px 4px 0px 0px #FFDB58;
        }
    </style>
</head>
<body class="bg-mustard font-body text-street selection:bg-royal selection:text-white">

    <!-- SELECTOR DE IDIOMAS -->
    <nav class="sticky top-0 z-[100] bg-street p-3 flex justify-center gap-5 comic-border border-t-0 border-x-0">
        <button onclick="changeLang('it')" id="btn-it" class="lang-btn px-6 py-1.5 text-[12px] font-heading text-white border-2 border-white hover:bg-white hover:text-black transition-all uppercase">Italiano</button>
        <button onclick="changeLang('es')" id="btn-es" class="lang-btn active px-6 py-1.5 text-[12px] font-heading text-white border-2 border-white hover:bg-white hover:text-black transition-all uppercase">Español</button>
        <button onclick="changeLang('en')" id="btn-en" class="lang-btn px-6 py-1.5 text-[12px] font-heading text-white border-2 border-white hover:bg-white hover:text-black transition-all uppercase">English</button>
    </nav>

    <!-- HEADER: MAGAZINE COVER -->
    <header class="m-6 bg-white comic-border shadow-hard p-12 relative overflow-hidden">
        <div class="absolute inset-0 halftone"></div>
        <div class="relative z-10">
            <div class="flex flex-wrap justify-between items-center mb-10 border-b-8 border-street pb-4">
                <p class="font-heading text-royal text-2xl uppercase tracking-tighter">Urban Lab Risk | Vol. 01</p>
                <p class="font-heading text-accent text-2xl uppercase tracking-tighter"></p>
            </div>
            <h1 id="main-title" class="font-heading uppercase italic tracking-tighter mb-8 text-royal">
                <span class="text-accent">DATOS</span>
            </h1>
            <p id="sub-title" class="text-xl md:text-5xl font-extrabold bg-royal text-white inline-block px-10 py-4 comic-border -rotate-1 uppercase tracking-tighter">
                HACKEANDO DATOS
            </p>
        </div>
    </header>

    <main class="max-w-7xl mx-auto p-4 space-y-24 pb-32">

        <!-- BLOQUE 1: LAS ESCALAS TERRITORIALES -->
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-12">
            
            <!-- UE -->
            <div class="flip-card h-[620px] tilt-l" onclick="this.classList.toggle('flipped')">
                <div class="flip-card-inner">
                    <div class="flip-card-front flex flex-col shadow-hard">
                        <div class="flex justify-between items-start mb-8">
                            <div class="flag flag-eu"><span>★</span><span>★</span><span>★</span></div>
                            <span class="text-[13px] font-black text-slate-400 uppercase tracking-widest">Scale: UE</span>
                        </div>
                        <h2 class="card-header-text font-heading text-royal uppercase italic mb-8" data-i18n="t-ue">Regulación Global</h2>
                        <p class="card-desc-text text-street mb-12" data-i18n="d-ue">Monitoreo de indicadores macroeconómicos y estabilidad financiera de los activos inmobiliarios europeos.</p>
                        <div class="flex-grow">
                            <p class="text-[15px] font-black text-slate-500 uppercase mb-4 border-b-2 border-slate-100" data-i18n="act-t">Nodos clave:</p>
                            <p class="card-nodes-text text-street">Eurostat (HPI), European Central Bank (ECB), European Environment Agency (EEA), Joint Research Centre (JRC), ENHR, Housing Europe Observatory, ESPON Network, EUKN Knowledge Network, Knight Frank Research, Savills World Research, CBRE Insights Europe ...</p>
                        </div>
                    </div>
                    <div class="flip-card-back bg-royal text-white flex flex-col justify-center text-center">
                        <div class="text-7xl font-heading text-mustard mb-4">+4.0%</div>
                        <p class="text-[14px] font-black uppercase mb-4 tracking-widest" data-i18n="bt-ue">House Price Index</p>
                        <p class="text-[16px] font-medium leading-tight mb-12" data-i18n="bd-ue">Crecimiento anual del precio de la vivienda residencial en la eurozona.</p>
                        <div class="text-[12px] font-black uppercase border-t border-white/20 pt-8">Fuente: Eurostat (2024)</div>
                    </div>
                </div>
            </div>

            <!-- ITALIA -->
            <div class="flip-card h-[620px] tilt-r" onclick="this.classList.toggle('flipped')">
                <div class="flip-card-inner">
                    <div class="flip-card-front flex flex-col shadow-hard">
                        <div class="flex justify-between items-start mb-8">
                            <div class="flag flag-it"><div class="g"></div><div class="w"></div><div class="r"></div></div>
                            <span class="text-[13px] font-black text-slate-400 uppercase tracking-widest">Scale: IT</span>
                        </div>
                        <h2 class="card-header-text font-heading text-royal uppercase italic mb-8" data-i18n="t-it">Sistema Nacional</h2>
                        <p class="card-desc-text text-street mb-12" data-i18n="d-it">Información oficial catastral, legalidad del valor inmobiliario y bases de datos transaccionales nacionales.</p>
                        <div class="flex-grow">
                            <p class="text-[15px] font-black text-slate-500 uppercase mb-4 border-b-2 border-slate-100" data-i18n="act-t">Nodos clave:</p>
                            <p class="card-nodes-text text-street">Agenzia delle Entrate (OMI), ISTAT (IPAB), Banca d'Italia, Ministero Infrastrutture (MIT), ISPRA Ambientale, Nomisma, Scenari Immobiliari, Idealista Data Research, CRIF Real Estate, Politecnico di Milano (REC), CRESME, Urban@it ...</p>
                        </div>
                    </div>
                    <div class="flip-card-back bg-street text-white flex flex-col justify-center text-center">
                        <div class="text-7xl font-heading text-mustard mb-4">1,5M</div>
                        <p class="text-[14px] font-black uppercase mb-4 tracking-widest" data-i18n="bt-it">Zonas de Control</p>
                        <p class="text-[16px] font-medium leading-tight mb-12" data-i18n="bd-it">Microzonas territoriales analizadas para la valoración fiscal del patrimonio italiano.</p>
                        <div class="text-[12px] font-black uppercase border-t border-white/20 pt-8">Fuente: Agenzia Entrate</div>
                    </div>
                </div>
            </div>

            <!-- TOSCANA -->
            <div class="flip-card h-[620px] tilt-l" onclick="this.classList.toggle('flipped')">
                <div class="flip-card-inner">
                    <div class="flip-card-front flex flex-col shadow-hard">
                        <div class="flex justify-between items-start mb-8">
                            <div class="flag flag-tos"></div>
                            <span class="text-[13px] font-black text-slate-400 uppercase tracking-widest">Scale: TOS</span>
                        </div>
                        <h2 class="card-header-text font-heading text-royal uppercase italic mb-8" data-i18n="t-to">Ámbito Regional</h2>
                        <p class="card-desc-text text-street mb-12" data-i18n="d-to">Análisis económico territorial aplicado, estrategias regionales y capitalización de valores paisajísticos.</p>
                        <div class="flex-grow">
                            <p class="text-[15px] font-black text-slate-500 uppercase mb-4 border-b-2 border-slate-100" data-i18n="act-t">Nodos clave:</p>
                            <p class="card-nodes-text text-street">IRPET Toscana, Regione Toscana (Politiche Abitative), Autorità Idrica (AIT), Osservatorio del Paesaggio, CIST Toscana, Scenari Toscana, Nomisma Regional, Tecnocasa Toscana Research, CRESME Rapporti Territoriali ...</p>
                        </div>
                    </div>
                    <div class="flip-card-back bg-mustard text-royal flex flex-col justify-center text-center">
                        <div class="text-7xl font-heading mb-4">18%</div>
                        <p class="text-[14px] font-black uppercase mb-4 tracking-widest" data-i18n="bt-to">PIB Sectorial</p>
                        <p class="text-[16px] font-medium leading-tight mb-12" data-i18n="bd-to">Peso combinado de la construcción y el sector inmobiliario en la economía regional.</p>
                        <div class="text-[12px] font-black uppercase border-t border-black/20 pt-8">Fuente: IRPET (2024)</div>
                    </div>
                </div>
            </div>

            <!-- FIRENZE -->
            <div class="flip-card h-[620px] tilt-r" onclick="this.classList.toggle('flipped')">
                <div class="flip-card-inner">
                    <div class="flip-card-front flex flex-col shadow-hard">
                        <div class="flex justify-between items-start mb-8">
                            <div class="flag flag-fi"></div>
                            <span class="text-[13px] font-black text-slate-400 uppercase tracking-widest">Scale: FI</span>
                        </div>
                        <h2 class="card-header-text font-heading text-royal uppercase italic mb-8" data-i18n="t-fi">Contexto Local</h2>
                        <p class="card-desc-text text-street mb-12" data-i18n="d-fi">Análisis de micro-mercados, planificación táctica y dinámica urbana ante el turismo global.</p>
                        <div class="flex-grow">
                            <p class="text-[15px] font-black text-slate-500 uppercase mb-4 border-b-2 border-slate-100" data-i18n="act-t">Nodos clave:</p>
                            <p class="card-nodes-text text-street">Comune di Firenze (Statistica), Città Metropolitana FI, Catastro Provinciale, Autorità di Bacino Distrettuale, UniFi DIDA, UniFi DISEI, UniFi DSPS, FIAIP Firenze, FIMAA Firenze ...</p>
                        </div>
                    </div>
                    <div class="flip-card-back bg-accent text-white flex flex-col justify-center text-center">
                        <div class="text-7xl font-heading text-mustard mb-4">-25%</div>
                        <p class="text-[14px] font-black uppercase mb-4 tracking-widest" data-i18n="bt-fi">Stock Residencial</p>
                        <p class="text-[16px] font-medium leading-tight mb-12" data-i18n="bd-fi">Reducción del mercado para residentes frente a la saturación turística UNESCO.</p>
                        <div class="text-[12px] font-black uppercase border-t border-white/20 pt-8">Fuente: Comune FI</div>
                    </div>
                </div>
            </div>
        </div>

        <!-- SECCIÓN 2: INVESTIGACIONES (ANALYSIS CARDS) -->
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 pt-10">
            
            <!-- REPORT A -->
            <div class="flip-card h-[720px]" onclick="this.classList.toggle('flipped')">
                <div class="flip-card-inner">
                    <div class="flip-card-front p-12 flex flex-col border-t-[15px] border-royal shadow-hard">
                        <div class="bg-royal text-white px-5 py-1 text-[12px] font-black mb-6 inline-block self-start uppercase">Analysis Report A</div>
                        <h2 class="font-heading text-2xl text-royal mb-6 leading-tight uppercase italic" data-i18n="rt-a">Floods do not sink prices, historical memory does</h2>
                        <p class="text-[16px] font-bold leading-snug mb-8" data-i18n="ra-1">Según la investigación de Bellaver et al. (2025), el mercado inmobiliario solo capitaliza el riesgo tras una exposición repetida.</p>
                        
                        <!-- DATA HERO FRONT -->
                        <div class="flex-grow flex flex-col justify-center items-center bg-slate-50 comic-border p-4 my-6">
                            <div class="data-front-hero font-heading text-royal">550K</div>
                            <p class="text-[14px] font-black uppercase text-accent text-center" data-i18n="ra-hero">Transacciones Analizadas (2016-2024)</p>
                        </div>

                        <div class="text-right text-[12px] font-black uppercase italic text-royal animate-pulse mt-4" data-i18n="c-rev">Gira para el análisis detallado ➜</div>
                    </div>
                    <div class="flip-card-back bg-street text-white p-12 flex flex-col justify-center text-center">
                        <div class="res-viz">
                            <div class="wave-motion"></div>
                            <div class="absolute inset-0 flex items-center justify-center font-heading text-4xl text-slate-300 opacity-20 uppercase tracking-[0.3em]">MEMORY</div>
                        </div>
                        <div class="text-[100px] font-heading text-accent leading-none mb-4 italic">-4%</div>
                        <h3 class="font-heading text-3xl uppercase italic mb-6" data-i18n="rb-a-t">Ajuste de Mercado</h3>
                        <p class="text-[18px] font-bold leading-tight max-w-sm mx-auto" data-i18n="rb-a-d">Descuento máximo en regiones como Toscana, donde la memoria del riesgo es alta y el experto negocia mejor.</p>
                        <div class="mt-10 text-[11px] font-black uppercase tracking-widest text-slate-500">Bellaver et al. (2025) • Centrale dei Rischi Dataset</div>
                    </div>
                </div>
            </div>

            <!-- REPORT B -->
            <div class="flip-card h-[720px]" onclick="this.classList.toggle('flipped')">
                <div class="flip-card-inner">
                    <div class="flip-card-front p-12 flex flex-col border-t-[15px] border-accent shadow-hard">
                        <div class="bg-accent text-white px-5 py-1 text-[12px] font-black mb-6 inline-block self-start uppercase">Analysis Report B</div>
                        <h2 class="font-heading text-2xl text-royal mb-6 leading-tight uppercase italic" data-i18n="rt-b">The Impacts in Real Estate of Landscape Values</h2>
                        <div class="space-y-6 text-[16px] font-bold leading-snug flex-grow">
                            <p data-i18n="rb-1">Según Riccioli et al. (2021), los valores estéticos del paisaje forestal inyectan una plusvalía indirecta determinante en el mercado toscano.</p>
                        </div>
                        
                        <!-- DATA HERO FRONT -->
                        <div class="flex-grow flex flex-col justify-center items-center bg-slate-50 comic-border p-4 my-6">
                            <div class="data-front-hero font-heading text-royal">+3.1%</div>
                            <p class="text-[14px] font-black uppercase text-accent text-center" data-i18n="rb-hero">Plusvalía por Paisaje Estético</p>
                        </div>

                        <div class="text-right text-[12px] font-black uppercase italic text-accent animate-pulse mt-4" data-i18n="c-rev">Gira para el análisis detallado ➜</div>
                    </div>
                    <div class="flip-card-back bg-royal text-white p-12 flex flex-col justify-center text-center">
                        <div class="rank-chart">
                            <div class="rank-bar h-full"></div>
                            <div class="rank-bar h-4/5 bg-mustard"></div>
                            <div class="rank-bar h-2/5 bg-accent"></div>
                            <div class="absolute inset-0 flex items-center justify-center font-heading text-4xl text-white opacity-10 uppercase tracking-[0.2em]">PAISAJE</div>
                        </div>
                        <div class="text-[100px] font-heading text-mustard leading-none mb-4 italic">+3.1%</div>
                        <h3 class="font-heading text-3xl uppercase italic mb-6" data-i18n="rb-b-t">Efecto Paisaje</h3>
                        <p class="text-[18px] font-bold leading-tight max-w-sm mx-auto" data-i18n="rb-b-d">Incremento promedio por proximidad extrema (< 100m) a paisajes forestales protegidos en la Toscana.</p>
                        <div class="mt-10 text-[11px] font-black uppercase tracking-widest text-white/40">Riccioli et al. (2021) • Evidence from Tuscany</div>
                    </div>
                </div>
            </div>

        </div>

        <!-- FOOTER: CONTINUARÁ -->
        <footer class="text-center py-24 space-y-12">
            <h2 class="font-heading text-4xl md:text-7xl uppercase tracking-tighter italic text-royal" data-i18n="cta-main">¿TE INTERESAN ESTOS TEMAS?</h2>
            <div class="pt-12">
                <p class="font-heading text-6xl md:text-9xl text-street uppercase tracking-tighter italic animate-pulse" data-i18n="cont-text">CONTINUARÁ...</p>
                <p class="text-slate-500 font-bold mt-4 uppercase text-lg tracking-widest">Urban Lab Risk | Vol. 01</p>
            </div>
        </footer>

    </main>

    <script>
        const translations = {
            es: {
                "main-title": "<span class='text-accent'>DATOS</span>",
                "sub-title": "HACKEANDO DATOS",
                "tag-header": "",
                "t-ue": "Regulación Global", "d-ue": "Monitoreo de indicadores macroeconómicos y estabilidad financiera de los activos inmobiliarios europeos.",
                "t-it": "Sistema Nacional", "d-it": "Información oficial catastral, legalidad del valor inmobiliario y bases de datos transaccionales nacionales.",
                "t-to": "Ámbito Regional", "d-to": "Análisis económico territorial aplicado, estrategias regionales y capitalización de valores paisajísticos.",
                "t-fi": "Contexto Local", "d-fi": "Análisis de micro-mercados, planificación táctica y dinámica urbana ante el turismo global.",
                "act-t": "Nodos clave:",
                "bt-ue": "House Price Index", "bd-ue": "Crecimiento anual del precio de la vivienda residencial en la eurozona.",
                "bt-it": "Zonas de Control", "bd-it": "Microzonas territoriales analizadas para la valoración fiscal del patrimonio italiano.",
                "bt-to": "PIB Sectorial", "bd-to": "Peso combinado de la construcción y el sector inmobiliario en la economía regional.",
                "bt-fi": "Stock Residencial", "bd-fi": "Drenaje de vivienda para residentes hacia el mercado turístico UNESCO.",
                "rt-a": "Floods do not sink prices, historical memory does",
                "ra-1": "Según la investigación de Bellaver et al. (2025), el mercado inmobiliario solo capitaliza el riesgo tras una exposición repetida.",
                "ra-hero": "Transacciones Analizadas (2016-2024)",
                "rb-a-t": "Ajuste de Mercado", "rb-a-d": "Descuento máximo en regiones como Toscana, donde la memoria del riesgo es alta.",
                "rt-b": "The Impacts in Real Estate of Landscape Values",
                "rb-1": "Según Riccioli et al. (2021), los valores estéticos del paisaje forestal inyectan una plusvalía indirecta determinante en el mercado toscano.",
                "rb-hero": "Plusvalía por Paisaje Estético",
                "rb-b-t": "Efecto Paisaje", "rb-b-d": "Incremento promedio por proximidad extrema (< 100m) a paisajes forestales protegidos.",
                "cta-main": "¿TE INTERESAN ESTOS TEMAS?", "cont-text": "CONTINUARÁ...", "c-rev": "Gira para el análisis detallado ➜"
            },
            it: {
                "main-title": "<span class='text-accent'>DATI</span>",
                "sub-title": "HACKERARE I DATI",
                "tag-header": "",
                "t-ue": "Regolazione Globale", "d-ue": "Monitoraggio degli indicatori macroeconomici e stabilità finanziaria degli asset immobiliari europei.",
                "t-it": "Sistema Nazionale", "d-it": "Informazioni catastali ufficiali, legalità del valore immobiliare e database transazionali nazionali.",
                "t-to": "Ambito Regionale", "d-to": "Analisi economica territoriale applicata, strategie regionali e capitalizzazione dei valori paesaggistici.",
                "t-fi": "Contesto Locale", "d-fi": "Analisi dei micro-mercati, pianificazione tattica e dinamiche urbane contro il turismo globale.",
                "act-t": "Nodi chiave:",
                "bt-ue": "House Price Index", "bd-ue": "Crescita annuale dei prezzi delle abitazioni residenziali nell'eurozona.",
                "bt-it": "Zone di Controllo", "bd-it": "Microzone analizzate per definire il valore fiscale italiano.",
                "bt-to": "PIL Settoriale", "bd-to": "Peso combinato delle costruzioni e del mercato immobiliare nell'economia regionale.",
                "bt-fi": "Stock Abitativo", "bd-fi": "Drenaggio di case per i residenti verso il mercato turistico UNESCO.",
                "rt-a": "Floods do not sink prices, historical memory does",
                "ra-1": "Secondo la ricerca di Bellaver et al. (2025), il mercato immobiliare capitalizza il rischio solo dopo esposizioni ripetute.",
                "ra-hero": "Transazioni Analizzate (2016-2024)",
                "rb-a-t": "Aggiustamento Mercato", "rb-a-d": "Sconto rilevato in regioni come la Toscana, dove la memoria del rischio è alta.",
                "rt-b": "The Impacts in Real Estate of Landscape Values",
                "rb-1": "Secondo Riccioli et al. (2021), i valori estetici del paesaggio forestale iniettano un plusvalore indiretto determinante nel mercato toscano.",
                "rb-hero": "Plusvalore per Paesaggio Estetico",
                "rb-b-t": "Effetto Paesaggio", "rb-b-d": "Incremento medio per estrema vicinanza (< 100m) a paesaggi forestali protetti.",
                "cta-main": "TI INTERESSANO QUESTI TEMI?", "cont-text": "CONTINUA...", "c-rev": "Gira per l'analisi dettagliata ➜"
            },
            en: {
                "main-title": "<span class='text-accent'>DATA</span>",
                "sub-title": "HACKING DATA",
                "tag-header": "",
                "t-ue": "Global Regulation", "d-ue": "Monitoring of macroeconomic indicators and financial stability of European real estate assets.",
                "t-it": "National System", "d-it": "Official cadastral info, real estate value legality and national transactional databases.",
                "t-to": "Regional Level", "d-to": "Applied territorial economic analysis, regional strategies and landscape value capitalization.",
                "t-fi": "Local Context", "d-fi": "Micro-market analysis, tactical planning and urban dynamics against global tourism.",
                "act-t": "Key nodes:",
                "bt-ue": "House Price Index", "bd-ue": "Annual growth of residential housing prices in the eurozone.",
                "bt-it": "Control Zones", "bd-it": "Territorial microzones analyzed for Italian fiscal heritage valuation.",
                "bt-to": "Sector GDP", "bd-to": "Combined weight of construction and real estate in the regional economy.",
                "bt-fi": "Housing Stock", "bd-fi": "Drain of housing for residents towards the UNESCO tourist market.",
                "rt-a": "Floods do not sink prices, historical memory does",
                "ra-1": "According to research by Bellaver et al. (2025), real estate market only capitalizes risk after repeated exposure.",
                "ra-hero": "Transactions Analyzed (2016-2024)",
                "rb-a-t": "Market Adjustment", "rb-a-d": "Maximum discount detected in regions like Tuscany, where risk memory is high.",
                "rt-b": "The Impacts in Real Estate of Landscape Values",
                "rb-1": "According to Riccioli et al. (2021), aesthetic landscape values inject an indirect premium into the Tuscan market.",
                "rb-hero": "Aesthetic Landscape Premium",
                "rb-b-t": "Landscape Effect", "rb-b-d": "Average increase for extreme proximity (< 100m) to protected forest landscapes.",
                "cta-main": "ARE YOU INTERESTED IN THESE TOPICS?", "cont-text": "TO BE CONTINUED...", "c-rev": "Flip for detailed analysis ➜"
            }
        };

        function changeLang(lang) {
            document.querySelectorAll('.lang-btn').forEach(btn => btn.classList.remove('active'));
            document.getElementById(`btn-${lang}`).classList.add('active');
            
            document.getElementById('main-title').innerHTML = translations[lang]["main-title"];
            document.getElementById('sub-title').innerHTML = translations[lang]["sub-title"];
            
            document.querySelectorAll('[data-i18n]').forEach(el => {
                const key = el.getAttribute('data-i18n');
                if (translations[lang][key]) el.innerHTML = translations[lang][key];
            });
        }
    </script>
</body>
</html>
