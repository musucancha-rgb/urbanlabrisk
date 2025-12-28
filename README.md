<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>URBAN ECONOMICS RESEARCH LAB | Housing Prices</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Archivo+Black&family=Space+Grotesk:wght@300;500;700;800&display=swap" rel="stylesheet">
    
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

        /* Sistema de Giro 3D */
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
            border: 4px solid #000000;
            background: white;
            padding: 1.5rem;
        }
        @media (min-width: 768px) {
            .flip-card-front, .flip-card-back {
                padding: 2.2rem;
            }
        }
        .flip-card-back {
            transform: rotateY(180deg);
            z-index: 10;
        }

        /* Banderas CSS (Sin bordes) */
        .flag { width: 65px; height: 42px; border: none; flex-shrink: 0; position: relative; overflow: hidden; }
        .flag-eu { background: #003399; display: grid; grid-template-columns: repeat(3, 1fr); color: yellow; font-size: 10px; place-items: center; }
        .flag-it { display: flex; }
        .flag-it div { flex: 1; }
        .flag-it .g { background: #009246; }
        .flag-it .w { background: #ffffff; }
        .flag-it .r { background: #ce2b37; }
        .flag-tos { background: #ffffff; border-top: 10px solid #ce2b37; border-bottom: 10px solid #ce2b37; }
        .flag-fi { background: #ffffff; position: relative; }
        .flag-fi::after { content: "⚜"; color: #ce2b37; position: absolute; inset: 0; display: flex; justify-content: center; align-items: center; font-size: 24px; }

        /* Tipografía Proporcional */
        .hero-title { font-size: clamp(2.2rem, 8vw, 4.8rem); line-height: 0.9; letter-spacing: -0.04em; }
        .card-header-text { font-size: clamp(1.6rem, 3.5vw, 2.2rem); line-height: 1; }
        .card-body-text { font-size: clamp(1rem, 1.1vw, 1.25rem); font-weight: 700; line-height: 1.25; }
        
        .node-link { font-size: 10px; font-weight: 800; text-transform: uppercase; color: inherit; text-decoration: underline; text-decoration-thickness: 1px; line-height: 1.6; }
        .node-link:hover { color: #f43f5e; }
        
        .stat-hero { font-size: clamp(3.5rem, 8vw, 5rem); line-height: 1; margin: 0.5rem 0; }

        /* Elementos Visuales */
        .viz-box { height: 130px; border: 3px solid black; margin: 1rem 0; position: relative; overflow: hidden; background: #fafafa; }
        .wave-layer { position: absolute; bottom: 0; width: 200%; height: 50%; background: #002366; opacity: 0.1; animation: slide 6s linear infinite; }
        @keyframes slide { from { transform: translateX(0); } to { transform: translateX(-50%); } }

        .rank-bars { display: flex; align-items: flex-end; justify-content: space-around; height: 110px; padding: 10px; gap: 8px; }
        .bar-unit { background: #10b981; border: 3px solid black; width: 45px; }

        .tilt-l { transform: rotate(-1.2deg); }
        .tilt-r { transform: rotate(1.2deg); }

        .lang-btn.active {
            background-color: #000000;
            color: #FFDB58;
            box-shadow: 4px 4px 0px 0px #FFDB58;
        }

        .signature-text { font-family: 'Space Grotesk', sans-serif; font-weight: 300; font-size: 12px; }
    </style>
</head>
<body class="bg-mustard font-body text-street selection:bg-royal selection:text-white">

    <!-- SELECTOR DE IDIOMAS -->
    <nav class="sticky top-0 z-[100] bg-street p-3 flex justify-center gap-4 comic-border border-t-0 border-x-0">
        <button onclick="changeLang('it')" id="btn-it" class="lang-btn px-5 py-1.5 text-[11px] md:text-[13px] font-heading text-white border-2 border-white hover:bg-white hover:text-black transition-all uppercase">Italiano</button>
        <button onclick="changeLang('es')" id="btn-es" class="lang-btn active px-5 py-1.5 text-[12px] md:text-[13px] font-heading text-white border-2 border-white hover:bg-white hover:text-black transition-all uppercase">Español</button>
        <button onclick="changeLang('en')" id="btn-en" class="lang-btn px-5 py-1.5 text-[12px] md:text-[13px] font-heading text-white border-2 border-white hover:bg-white hover:text-black transition-all uppercase">English</button>
    </nav>

    <!-- HEADER: PORTADA DEL LABORATORIO -->
    <header class="m-4 md:m-8 bg-white comic-border shadow-hard p-10 md:p-14 relative overflow-hidden">
        <div class="absolute inset-0 halftone"></div>
        <div class="relative z-10">
            <div class="flex flex-wrap justify-end items-center mb-8 border-b-8 border-street pb-4">
                <p class="signature-text text-royal text-right italic">
                    Prepared by Urban Lab Risk, MAMR-2025
                </p>
            </div>
            <h1 id="main-title" class="hero-title font-heading uppercase italic tracking-tighter mb-8 text-royal text-center md:text-left">
                URBAN ECONOMICS <br> RESEARCH LAB
            </h1>
            <p id="sub-title" class="text-xl md:text-5xl font-extrabold bg-royal text-white inline-block px-10 py-4 comic-border -rotate-1 uppercase tracking-tighter">
                Housing prices & climate risk
            </p>
        </div>
    </header>

    <main class="max-w-7xl mx-auto p-4 md:p-8 space-y-24 pb-32">

        <!-- BLOQUE 1: ESCALAS TERRITORIALES -->
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-10 md:gap-14">
            
            <!-- UE -->
            <div class="flip-card h-[640px] md:h-[680px] tilt-l" onclick="this.classList.toggle('flipped')">
                <div class="flip-card-inner">
                    <!-- FRENTE -->
                    <div class="flip-card-front flex flex-col shadow-hard">
                        <div class="flex justify-between items-start mb-8">
                            <div class="flag flag-eu"><span>★</span><span>★</span><span>★</span></div>
                            <span class="text-[12px] font-black text-slate-400 uppercase tracking-widest">Scale: UE</span>
                        </div>
                        <h2 class="card-header-text font-heading text-royal uppercase italic mb-6" data-i18n="t-ue">Regulación Global</h2>
                        <p class="card-body-text text-street mb-10" data-i18n="d-ue">Monitoreo de indicadores macroeconómicos y estabilidad financiera de los activos inmobiliarios europeos.</p>
                        
                        <div class="mt-auto bg-slate-50 comic-border-sm p-6 text-center">
                            <div class="text-6xl font-heading text-royal mb-2">+4.0%</div>
                            <p class="text-[13px] font-black uppercase mb-1" data-i18n="bt-ue">House Price Index</p>
                        </div>
                    </div>
                    <!-- REVERSO -->
                    <div class="flip-card-back bg-royal text-white flex flex-col">
                        <p class="text-[14px] font-black text-mustard uppercase mb-6 border-b-2 border-white/20 pb-2" data-i18n="act-t">Nodos Institucionales:</p>
                        <div class="grid grid-cols-1 gap-y-4 overflow-y-auto pr-2">
                            <a href="https://ec.europa.eu/eurostat" target="_blank" class="node-link">Eurostat (HPI)</a>
                            <a href="https://www.ecb.europa.eu" target="_blank" class="node-link">European Central Bank</a>
                            <a href="https://www.eea.europa.eu" target="_blank" class="node-link">Environment Agency (EEA)</a>
                            <a href="https://joint-research-centre.ec.europa.eu" target="_blank" class="node-link">JRC Commission</a>
                            <a href="https://www.enhr.net" target="_blank" class="node-link">ENHR Network</a>
                            <a href="https://www.housingeurope.eu" target="_blank" class="node-link">Housing Europe</a>
                            <a href="https://www.espon.eu" target="_blank" class="node-link">ESPON Network</a>
                        </div>
                        <div class="mt-auto pt-6 border-t border-white/20 text-[10px] font-black uppercase text-center opacity-40 italic">Urban Intelligence Unit</div>
                    </div>
                </div>
            </div>

            <!-- ITALIA -->
            <div class="flip-card h-[640px] md:h-[680px] tilt-r" onclick="this.classList.toggle('flipped')">
                <div class="flip-card-inner">
                    <!-- FRENTE -->
                    <div class="flip-card-front flex flex-col shadow-hard">
                        <div class="flex justify-between items-start mb-8">
                            <div class="flag flag-it"><div class="g"></div><div class="w"></div><div class="r"></div></div>
                            <span class="text-[12px] font-black text-slate-400 uppercase tracking-widest">Scale: IT</span>
                        </div>
                        <h2 class="card-header-text font-heading text-royal uppercase italic mb-6" data-i18n="t-it">Sistema Nacional</h2>
                        <p class="card-body-text text-street mb-10" data-i18n="d-it">Información oficial catastral, legalidad del valor inmobiliario y bases de datos transaccionales nacionales.</p>
                        
                        <div class="mt-auto bg-slate-50 comic-border-sm p-6 text-center">
                            <div class="text-6xl font-heading text-royal mb-2">1,5M</div>
                            <p class="text-[13px] font-black uppercase mb-1" data-i18n="bt-it">Zonas de Control</p>
                        </div>
                    </div>
                    <!-- REVERSO -->
                    <div class="flip-card-back bg-street text-white flex flex-col">
                        <p class="text-[14px] font-black text-accent uppercase mb-6 border-b-2 border-white/10 pb-2" data-i18n="act-t">Nodos Institucionales:</p>
                        <div class="grid grid-cols-1 gap-y-4 overflow-y-auto pr-2">
                            <a href="https://www.agenziaentrate.gov.it" target="_blank" class="node-link">Agenzia Entrate (OMI)</a>
                            <a href="https://www.istat.it" target="_blank" class="node-link">ISTAT (IPAB)</a>
                            <a href="https://www.bancaditalia.it" target="_blank" class="node-link">Banca d'Italia</a>
                            <a href="https://www.mit.gov.it" target="_blank" class="node-link">Ministero MIT</a>
                            <a href="https://www.isprambiente.gov.it" target="_blank" class="node-link">ISPRA</a>
                            <a href="https://www.nomisma.it" target="_blank" class="node-link">Nomisma Spa</a>
                            <a href="https://www.idealista.it/data" target="_blank" class="node-link">Idealista Data</a>
                        </div>
                        <div class="mt-auto pt-6 border-t border-white/10 text-[10px] font-black uppercase text-center opacity-40 italic">Urban Intelligence Unit</div>
                    </div>
                </div>
            </div>

            <!-- TOSCANA -->
            <div class="flip-card h-[640px] md:h-[680px] tilt-l" onclick="this.classList.toggle('flipped')">
                <div class="flip-card-inner">
                    <!-- FRENTE -->
                    <div class="flip-card-front flex flex-col shadow-hard">
                        <div class="flex justify-between items-start mb-8">
                            <div class="flag flag-tos"></div>
                            <span class="text-[12px] font-black text-slate-400 uppercase tracking-widest">Scale: TOS</span>
                        </div>
                        <h2 class="card-header-text font-heading text-royal uppercase italic mb-6" data-i18n="t-to">Ámbito Regional</h2>
                        <p class="card-body-text text-street mb-10" data-i18n="d-to">Análisis económico territorial aplicado, estrategias regionales y capitalización de valores paisajísticos.</p>
                        
                        <div class="mt-auto bg-slate-50 comic-border-sm p-6 text-center">
                            <div class="text-6xl font-heading text-royal mb-2">18%</div>
                            <p class="text-[13px] font-black uppercase mb-1" data-i18n="bt-to">PIB Sectorial</p>
                        </div>
                    </div>
                    <!-- REVERSO -->
                    <div class="flip-card-back bg-mustard text-royal flex flex-col">
                        <p class="text-[14px] font-black text-royal uppercase mb-6 border-b-2 border-black/10 pb-2" data-i18n="act-t">Nodos Institucionales:</p>
                        <div class="grid grid-cols-1 gap-y-4 overflow-y-auto pr-2">
                            <a href="https://www.irpet.it" target="_blank" class="node-link text-royal">IRPET Toscana</a>
                            <a href="https://www.regione.toscana.it" target="_blank" class="node-link text-royal">Regione Toscana</a>
                            <a href="https://www.autoritaidrica.toscana.it" target="_blank" class="node-link text-royal">Autorità Idrica (AIT)</a>
                            <a href="https://www.paesaggiotoscana.it" target="_blank" class="node-link text-royal">Osservatorio Paesaggio</a>
                            <a href="https://www.cist.unifi.it" target="_blank" class="node-link text-royal">CIST Toscana</a>
                            <a href="https://www.tecno-casa.it" target="_blank" class="node-link text-royal">Tecnocasa Research</a>
                        </div>
                        <div class="mt-auto pt-6 border-t border-black/10 text-[10px] font-black uppercase text-center opacity-40 italic">Urban Intelligence Unit</div>
                    </div>
                </div>
            </div>

            <!-- FIRENZE -->
            <div class="flip-card h-[640px] md:h-[680px] tilt-r" onclick="this.classList.toggle('flipped')">
                <div class="flip-card-inner">
                    <!-- FRENTE -->
                    <div class="flip-card-front flex flex-col shadow-hard">
                        <div class="flex justify-between items-start mb-8">
                            <div class="flag flag-fi"></div>
                            <span class="text-[12px] font-black text-slate-400 uppercase tracking-widest">Scale: FI</span>
                        </div>
                        <h2 class="card-header-text font-heading text-royal uppercase italic mb-6" data-i18n="t-fi">Contexto Local</h2>
                        <p class="card-body-text text-street mb-10" data-i18n="d-fi">Análisis de micro-mercados, planificación táctica y dinámica urbana ante el turismo global.</p>
                        
                        <div class="mt-auto bg-slate-50 comic-border-sm p-6 text-center">
                            <div class="text-6xl font-heading text-royal mb-2">-25%</div>
                            <p class="text-[13px] font-black uppercase mb-1" data-i18n="bt-fi">Stock Residencial</p>
                        </div>
                    </div>
                    <!-- REVERSO -->
                    <div class="flip-card-back bg-accent text-white flex flex-col">
                        <p class="text-[14px] font-black text-white uppercase mb-6 border-b-2 border-white/20 pb-2" data-i18n="act-t">Nodos Institucionales:</p>
                        <div class="grid grid-cols-1 gap-y-4 overflow-y-auto pr-2">
                            <a href="https://www.comune.fi.it" target="_blank" class="node-link text-white">Comune di Firenze</a>
                            <a href="https://www.dida.unifi.it" target="_blank" class="node-link text-white">UniFi DIDA (Arch.)</a>
                            <a href="https://www.disei.unifi.it" target="_blank" class="node-link text-white">UniFi DISEI (Econ.)</a>
                            <a href="https://www.autoritadibacino.it" target="_blank" class="node-link text-white">Autorità Bacino</a>
                            <a href="https://www.fiaip.it" target="_blank" class="node-link text-white">FIAIP Firenze</a>
                        </div>
                        <div class="mt-auto pt-6 border-t border-white/20 text-[10px] font-black uppercase text-center opacity-40 italic">Urban Intelligence Unit</div>
                    </div>
                </div>
            </div>
        </div>

        <!-- SECCIÓN 2: INVESTIGACIONES CIENTÍFICAS -->
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 pt-10">
            
            <!-- REPORT A -->
            <div class="flip-card h-[720px] md:h-[780px]" onclick="this.classList.toggle('flipped')">
                <div class="flip-card-inner">
                    <div class="flip-card-front p-12 flex flex-col border-t-[15px] border-royal shadow-hard">
                        <div class="bg-royal text-white px-5 py-1 text-[12px] font-black mb-6 inline-block self-start uppercase">Analysis Report A</div>
                        <h2 class="font-heading text-2xl md:text-3xl text-royal mb-6 leading-tight uppercase italic" data-i18n="rt-a">Floods do not sink prices, historical memory does</h2>
                        <p class="text-[16px] md:text-[18px] font-bold leading-snug mb-8" data-i18n="ra-1">Según la investigación de Bellaver et al. (2025), el mercado inmobiliario solo capitaliza el riesgo tras una exposición repetida.</p>
                        
                        <div class="flex-grow flex flex-col justify-center items-center bg-slate-50 comic-border p-6 my-4">
                            <div class="stat-hero font-heading text-royal">550K</div>
                            <p class="text-[14px] md:text-[16px] font-black uppercase text-accent text-center" data-i18n="ra-hero">Transacciones Hipotecarias Analizadas</p>
                        </div>

                        <div class="text-right text-[12px] font-black uppercase italic text-royal animate-pulse mt-4" data-i18n="c-rev">Gira para el análisis detallado ➜</div>
                    </div>
                    <div class="flip-card-back bg-street text-white p-12 flex flex-col justify-center text-center">
                        <div class="viz-container">
                            <div class="wave-layer"></div>
                            <div class="absolute inset-0 flex items-center justify-center font-heading text-4xl text-slate-300 opacity-20 uppercase tracking-[0.3em]">MEMORY</div>
                        </div>
                        <div class="text-[90px] md:text-[120px] font-heading text-accent leading-none mb-4 italic">-4%</div>
                        <h3 class="font-heading text-3xl uppercase italic mb-6" data-i18n="rb-a-t">Ajuste de Mercado</h3>
                        <p class="text-[16px] md:text-[19px] font-bold leading-tight max-w-sm mx-auto" data-i18n="rb-a-d">En regiones con alta recurrencia (Toscana), donde la memoria del riesgo es alta, el mercado castiga el valor.</p>
                        <div class="mt-10 text-[11px] font-black uppercase tracking-widest text-slate-500 italic">Bellaver et al. (2025) • Centrale dei Rischi Database</div>
                    </div>
                </div>
            </div>

            <!-- REPORT B -->
            <div class="flip-card h-[720px] md:h-[780px]" onclick="this.classList.toggle('flipped')">
                <div class="flip-card-inner">
                    <div class="flip-card-front p-12 flex flex-col border-t-[15px] border-accent shadow-hard">
                        <div class="bg-accent text-white px-5 py-1 text-[12px] font-black mb-6 inline-block self-start uppercase">Analysis Report B</div>
                        <h2 class="font-heading text-2xl md:text-3xl text-royal mb-6 leading-tight uppercase italic" data-i18n="rt-b">The Impacts in Real Estate of Landscape Values</h2>
                        <div class="space-y-6 text-[16px] md:text-[18px] font-bold leading-snug flex-grow">
                            <p data-i18n="rb-1">Según Riccioli et al. (2021), los valores estéticos del paisaje forestal inyectan una plusvalía indirecta determinante en el mercado toscano.</p>
                        </div>
                        
                        <div class="flex-grow flex flex-col justify-center items-center bg-slate-50 comic-border p-6 my-4">
                            <div class="stat-hero font-heading text-royal">+3.1%</div>
                            <p class="text-[14px] md:text-[16px] font-black uppercase text-accent text-center" data-i18n="rb-hero">Plusvalía por Paisaje Estético</p>
                        </div>

                        <div class="text-right text-[12px] font-black uppercase italic text-accent animate-pulse mt-4" data-i18n="c-rev">Gira para el análisis detallado ➜</div>
                    </div>
                    <div class="flip-card-back bg-royal text-white p-12 flex flex-col justify-center text-center">
                        <div class="viz-container">
                            <div class="rank-bars">
                                <div class="bar-unit h-full"></div>
                                <div class="bar-unit h-4/5 bg-mustard"></div>
                                <div class="bar-unit h-2/5 bg-accent"></div>
                            </div>
                            <div class="absolute inset-0 flex items-center justify-center font-heading text-4xl text-white opacity-10 uppercase tracking-[0.2em]">PAISAJE</div>
                        </div>
                        <div class="text-[90px] md:text-[120px] font-heading text-mustard leading-none mb-4 italic">+3.1%</div>
                        <h3 class="font-heading text-3xl uppercase italic mb-6" data-i18n="rb-b-t">Efecto Paisaje</h3>
                        <p class="text-[16px] md:text-[19px] font-bold leading-tight max-w-sm mx-auto" data-i18n="rb-b-d">Incremento promedio por proximidad extrema (< 100m) a paisajes forestales protegidos en la Toscana.</p>
                        <div class="mt-10 text-[11px] font-black uppercase tracking-widest text-white/40 italic">Riccioli et al. (2021) • Evidence from Tuscany</div>
                    </div>
                </div>
            </div>

        </div>

        <!-- FOOTER: CONTINUARÁ -->
        <footer class="text-center py-24 space-y-12">
            <h2 class="font-heading text-4xl md:text-7xl uppercase tracking-tighter italic text-royal" data-i18n="cta-main">¿TE INTERESAN ESTOS TEMAS?</h2>
            <div class="pt-12">
                <p class="font-heading text-6xl md:text-9xl text-street uppercase tracking-tighter italic animate-pulse" data-i18n="cont-text">CONTINUARÁ...</p>
                <p class="text-slate-500 font-bold mt-4 uppercase text-lg tracking-widest">Urban Economics Research Lab</p>
            </div>
        </footer>

    </main>

    <script>
        const translations = {
            es: {
                "t-ue": "Regulación Global", "d-ue": "Monitoreo de indicadores macroeconómicos y estabilidad financiera de los activos inmobiliarios europeos.",
                "t-it": "Sistema Nacional", "d-it": "Información oficial catastral, legalidad del valor inmobiliario y bases de datos transaccionales nacionales.",
                "t-to": "Ámbito Regional", "d-to": "Análisis económico territorial aplicado, estrategias regionales y capitalización de valores paisajísticos.",
                "t-fi": "Contexto Local", "d-fi": "Análisis de micro-mercados, planificación táctica y dinámica urbana ante el turismo global.",
                "act-t": "Nodos Institucionales:",
                "bt-ue": "House Price Index", "bt-it": "Zonas de Control", "bt-to": "PIB Sectorial", "bt-fi": "Stock Residencial",
                "ra-1": "Según la investigación de Bellaver et al. (2025), el mercado inmobiliario solo capitaliza el riesgo tras una exposición repetida.",
                "ra-hero": "Transacciones Analizadas (2016-2024)",
                "rb-a-t": "Ajuste de Mercado", "rb-a-d": "En regiones con alta recurrencia (Toscana), donde la memoria del riesgo es alta, el mercado castiga el valor.",
                "rb-1": "Según Riccioli et al. (2021), los valores estéticos del paisaje forestal inyectan una plusvalía indirecta determinante en el mercado toscano.",
                "rb-hero": "Plusvalía por Paisaje Estético",
                "rb-b-t": "Efecto Paisaje", "rb-b-d": "Incremento promedio por proximidad extrema (< 100m) a paisajes forestales protegidos.",
                "cta-main": "¿TE INTERESAN ESTOS TEMAS?", "cont-text": "CONTINUARÁ...", "c-rev": "Gira para el análisis detallado ➜"
            },
            it: {
                "t-ue": "Regolazione Globale", "d-ue": "Monitoraggio degli indicatori macroeconomici e stabilità finanziaria degli asset immobiliari europei.",
                "t-it": "Sistema Nazionale", "d-it": "Informazioni catastali ufficiali, legalità del valore immobiliare e database transazionali nazionali.",
                "t-to": "Ambito Regionale", "d-to": "Analisi economica territoriale applicata, strategie regionali e capitalizzazione dei valori paesaggistici.",
                "t-fi": "Contesto Locale", "d-fi": "Analisi dei micro-mercati e pianificazione tattica contro il turismo globale.",
                "act-t": "Nodi Istituzionali:",
                "bt-ue": "House Price Index", "bt-it": "Zone di Controllo", "bt-to": "PIL Settoriale", "bt-fi": "Stock Abitativo",
                "ra-1": "Secondo la ricerca di Bellaver et al. (2025), il mercato immobiliare capitalizza il rischio solo dopo esposizioni ripetute.",
                "ra-hero": "Transazioni Analizzate (2016-2024)",
                "rb-a-t": "Aggiustamento Mercato", "rb-a-d": "Nelle regioni con alta ricorrenza (Toscana), dove la memoria del rischio è alta, il mercato punisce il valore.",
                "rb-1": "Secondo Riccioli et al. (2021), i valori estetici del paesaggio forestale iniettano un plusvalore indiretto determinante nel mercato toscano.",
                "rb-hero": "Plusvalore per Paesaggio Estetico",
                "rb-b-t": "Effetto Paesaggio", "rb-b-d": "Incremento medio rilevato per proprietà situate entro un raggio estremo di paesaggi forestali.",
                "cta-main": "TI INTERESSANO QUESTI TEMI?", "cont-text": "CONTINUA...", "c-rev": "Gira per l'analisi dettagliata ➜"
            },
            en: {
                "t-ue": "Global Regulation", "d-ue": "Monitoring of macroeconomic indicators and financial stability of European real estate assets.",
                "t-it": "National System", "d-it": "Official cadastral info, real estate value legality and national transactional databases.",
                "t-to": "Regional Level", "d-to": "Applied territorial economic analysis, regional strategies and landscape value capitalization.",
                "t-fi": "Local Context", "d-fi": "Micro-market analysis, tactical planning and urban dynamics against global tourism.",
                "act-t": "Institutional Nodes:",
                "bt-ue": "House Price Index", "bt-it": "Control Zones", "bt-to": "Sector GDP", "bt-fi": "Housing Stock",
                "ra-1": "According to research by Bellaver et al. (2025), real estate market only capitalizes risk after repeated exposure.",
                "ra-hero": "Transactions Analyzed (2016-2024)",
                "rb-a-t": "Market Adjustment", "rb-a-d": "In regions with high recurrence (Tuscany), where risk memory is high, market punishes value.",
                "rb-1": "According to Riccioli et al. (2021), aesthetic landscape values inject an indirect premium into the Tuscan market.",
                "rb-hero": "Aesthetic Landscape Premium",
                "rb-b-t": "Landscape Effect", "rb-b-d": "Average increase for extreme proximity (< 100m) to protected forest landscapes.",
                "cta-main": "ARE YOU INTERESTED IN THESE TOPICS?", "cont-text": "TO BE CONTINUED...", "c-rev": "Flip for detailed analysis ➜"
            }
        };

        function changeLang(lang) {
            document.querySelectorAll('.lang-btn').forEach(btn => btn.classList.remove('active'));
            document.getElementById(`btn-${lang}`).classList.add('active');
            
            document.querySelectorAll('[data-i18n]').forEach(el => {
                const key = el.getAttribute('data-i18n');
                if (translations[lang][key]) el.innerHTML = translations[lang][key];
            });
        }
    </script>
</body>
</html>
