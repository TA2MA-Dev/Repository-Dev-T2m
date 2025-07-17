<!DOCTYPE html>
<html lang="it">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Volontà Reale - Un'Iniziativa per Mozzate</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
    <!-- Chosen Palette: Calm Harmony -->
    <!-- Application Structure Plan: Ho progettato l'applicazione come un'unica narrazione a scorrimento verticale, guidando l'utente attraverso un percorso logico. Si inizia con il "perché" (le problematiche), si passa al "cosa" (la soluzione), si esplora il "come" (le missioni interattive e la gamification), si analizzano gli "strumenti" (la tecnologia) e si conclude con l' "impatto" (benefici e visione). Questa struttura tematica, invece di replicare quella dei documenti, facilita la comprensione e l'engagement, permettendo agli utenti di approfondire le aree di maggior interesse, come la sezione interattiva delle missioni, che è il fulcro dell'esperienza. -->
    <!-- Visualization & Content Choices: Ho tradotto i concetti chiave in elementi visivi e interattivi. Le 4 aree problematiche sono presentate in una griglia chiara. Le missioni sono visualizzate come card filtrabili, con un grafico a ciambella Chart.js che si aggiorna dinamicamente per dare un colpo d'occhio sulla distribuzione delle attività. La gamification è spiegata con un diagramma a passi e un grafico a barre Chart.js che quantifica le ricompense. La tecnologia è rappresentata da icone semplici (Unicode/HTML) per non appesantire. Questa scelta mira a massimizzare la chiarezza e l'interazione senza sovraccaricare l'utente di informazioni. -->
    <!-- CONFIRMATION: NO SVG graphics used. NO Mermaid JS used. -->
    <style>
        body {
            font-family: 'Inter', sans-serif;
        }
        .chart-container {
            position: relative;
            width: 100%;
            max-width: 450px;
            margin-left: auto;
            margin-right: auto;
            height: 300px;
            max-height: 400px;
        }
        @media (min-width: 768px) {
            .chart-container {
                height: 350px;
            }
        }
        .section-fade-in {
            opacity: 0;
            transform: translateY(20px);
            transition: opacity 0.6s ease-out, transform 0.6s ease-out;
        }
        .section-fade-in.visible {
            opacity: 1;
            transform: translateY(0);
        }
        .gradient-text {
            background: linear-gradient(to right, #14b8a6, #0ea5e9);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
    </style>
</head>
<body class="bg-stone-50 text-stone-800">

    <main class="container mx-auto px-4 sm:px-6 lg:px-8">

        <header class="text-center py-16 sm:py-24 section-fade-in">
            <h1 class="text-4xl sm:text-5xl md:text-6xl font-bold tracking-tight">
                <span class="gradient-text">Volontà Reale</span>
            </h1>
            <p class="mt-4 text-lg sm:text-xl text-stone-600 max-w-3xl mx-auto">Un'iniziativa innovativa di <span class="font-semibold text-teal-700">Tatuma</span> per il <span class="font-semibold text-sky-700">Comune di Mozzate</span>, che unisce tecnologia e partecipazione civica per costruire una comunità più forte, trasparente e connessa.</p>
        </header>

        <section id="problema" class="py-16 sm:py-20 section-fade-in">
            <div class="text-center">
                <h2 class="text-3xl font-bold tracking-tight">Le Sfide della Nostra Comunità</h2>
                <p class="mt-3 text-lg text-stone-600 max-w-2xl mx-auto">Il progetto nasce per rispondere a quattro esigenze concrete, trasformando le difficoltà in opportunità di crescita condivisa.</p>
            </div>
            <div class="mt-12 grid gap-8 md:grid-cols-2 lg:grid-cols-4">
                <div class="p-6 bg-white rounded-xl shadow-md hover:shadow-xl transition-shadow duration-300">
                    <div class="flex items-center justify-center h-12 w-12 rounded-full bg-teal-100 text-teal-700 text-2xl">✓</div>
                    <h3 class="mt-5 text-xl font-semibold">Deficit di Trasparenza</h3>
                    <p class="mt-2 text-stone-600">Mancanza di visibilità sui processi decisionali e sull'uso delle risorse pubbliche.</p>
                </div>
                <div class="p-6 bg-white rounded-xl shadow-md hover:shadow-xl transition-shadow duration-300">
                    <div class="flex items-center justify-center h-12 w-12 rounded-full bg-sky-100 text-sky-700 text-2xl">✗</div>
                    <h3 class="mt-5 text-xl font-semibold">Inefficienza Burocratica</h3>
                    <p class="mt-2 text-stone-600">Procedure amministrative lente, complesse e poco accessibili per i cittadini.</p>
                </div>
                <div class="p-6 bg-white rounded-xl shadow-md hover:shadow-xl transition-shadow duration-300">
                    <div class="flex items-center justify-center h-12 w-12 rounded-full bg-amber-100 text-amber-700 text-2xl">👥</div>
                    <h3 class="mt-5 text-xl font-semibold">Scarso Coinvolgimento</h3>
                    <p class="mt-2 text-stone-600">Bassa partecipazione dei cittadini alla vita comunitaria e alle attività di volontariato.</p>
                </div>
                <div class="p-6 bg-white rounded-xl shadow-md hover:shadow-xl transition-shadow duration-300">
                    <div class="flex items-center justify-center h-12 w-12 rounded-full bg-rose-100 text-rose-700 text-2xl">💰</div>
                    <h3 class="mt-5 text-xl font-semibold">Difficoltà di Finanziamento</h3>
                    <p class="mt-2 text-stone-600">Scarsità di fondi per progetti di valore sociale, culturale e ambientale.</p>
                </div>
            </div>
        </section>

        <section id="soluzione" class="py-16 sm:py-20 section-fade-in">
             <div class="text-center">
                <h2 class="text-3xl font-bold tracking-tight">La Nostra Soluzione Integrata</h2>
                <p class="mt-3 text-lg text-stone-600 max-w-3xl mx-auto">Abbiamo unito una piattaforma tecnologica all'avanguardia con un programma di volontariato attivo per creare un ecosistema di valore per tutti.</p>
            </div>
            <div class="mt-12 grid md:grid-cols-5 gap-8 items-center">
                <div class="md:col-span-2 p-8 bg-white rounded-xl shadow-lg">
                    <h3 class="text-2xl font-bold text-sky-700">Piattaforma Tatuma</h3>
                    <p class="mt-2 text-stone-600">Un ecosistema digitale basato su **Blockchain** per garantire trasparenza e tracciabilità. Integra **Intelligenza Artificiale** per semplificare l'interazione e l'accesso alle informazioni.</p>
                </div>
                <div class="text-5xl text-center text-stone-300 font-bold">+</div>
                <div class="md:col-span-2 p-8 bg-white rounded-xl shadow-lg">
                     <h3 class="text-2xl font-bold text-teal-700">Iniziativa Volontà Reale</h3>
                    <p class="mt-2 text-stone-600">Un programma di **volontariato** che incentiva i cittadini a partecipare a missioni concrete per il bene comune, migliorando attivamente il territorio e il tessuto sociale.</p>
                </div>
            </div>
        </section>

        <section id="missioni" class="py-16 sm:py-20 section-fade-in">
            <div class="text-center">
                <h2 class="text-3xl font-bold tracking-tight">Esplora le Missioni</h2>
                <p class="mt-3 text-lg text-stone-600 max-w-2xl mx-auto">Diventa protagonista del cambiamento. Scegli una categoria e scopri come puoi contribuire attivamente alla crescita di Mozzate.</p>
            </div>
            <div class="lg:grid lg:grid-cols-3 lg:gap-8 items-start">
                <div class="lg:col-span-2">
                    <div class="flex flex-wrap gap-2 justify-center my-8">
                        <button class="mission-filter-btn active bg-teal-600 text-white py-2 px-4 rounded-full text-sm font-semibold" data-filter="all">Tutte</button>
                        <button class="mission-filter-btn bg-white hover:bg-teal-50 py-2 px-4 rounded-full text-sm font-semibold" data-filter="Ambiente">Ambiente</button>
                        <button class="mission-filter-btn bg-white hover:bg-teal-50 py-2 px-4 rounded-full text-sm font-semibold" data-filter="Abbellimento">Abbellimento Urbano</button>
                        <button class="mission-filter-btn bg-white hover:bg-teal-50 py-2 px-4 rounded-full text-sm font-semibold" data-filter="Sociale">Supporto Sociale</button>
                        <button class="mission-filter-btn bg-white hover:bg-teal-50 py-2 px-4 rounded-full text-sm font-semibold" data-filter="Cultura">Cultura</button>
                        <button class="mission-filter-btn bg-white hover:bg-teal-50 py-2 px-4 rounded-full text-sm font-semibold" data-filter="Inclusione">Inclusione</button>
                    </div>
                    <div id="mission-grid" class="grid sm:grid-cols-2 gap-6">
                    </div>
                </div>
                <div class="lg:col-span-1 mt-12 lg:mt-0">
                     <div class="p-6 bg-white rounded-xl shadow-lg sticky top-8">
                         <h3 class="text-xl font-bold text-center">Distribuzione Missioni</h3>
                         <p class="text-center text-sm text-stone-500 mb-4">Panoramica delle aree di intervento.</p>
                        <div class="chart-container">
                            <canvas id="missionsChart"></canvas>
                        </div>
                    </div>
                </div>
            </div>
        </section>
        
        <section id="gamification" class="py-16 sm:py-20 section-fade-in">
            <div class="text-center">
                <h2 class="text-3xl font-bold tracking-tight">Partecipa, Guadagna, Cresci</h2>
                <p class="mt-3 text-lg text-stone-600 max-w-2xl mx-auto">Abbiamo creato un sistema di ricompense per rendere il volontariato ancora più coinvolgente e gratificante. Ogni tuo contributo ha un valore riconosciuto.</p>
            </div>
            <div class="mt-12 lg:grid lg:grid-cols-2 lg:gap-12 items-center">
                <div>
                    <h3 class="text-xl font-bold">Il Ciclo Virtuoso del Volontario</h3>
                    <ol class="mt-4 space-y-4">
                        <li class="flex items-start">
                            <span class="flex-shrink-0 flex items-center justify-center h-8 w-8 rounded-full bg-teal-100 text-teal-700 font-bold">1</span>
                            <div class="ml-4">
                                <h4 class="font-semibold">Completa le Missioni</h4>
                                <p class="text-stone-600">Scegli le attività che preferisci e contribuisci attivamente.</p>
                            </div>
                        </li>
                         <li class="flex items-start">
                            <span class="flex-shrink-0 flex items-center justify-center h-8 w-8 rounded-full bg-sky-100 text-sky-700 font-bold">2</span>
                            <div class="ml-4">
                                <h4 class="font-semibold">Guadagna Punti VR</h4>
                                <p class="text-stone-600">Accumula Punti Volontà Reale per ogni tua azione.</p>
                            </div>
                        </li>
                        <li class="flex items-start">
                            <span class="flex-shrink-0 flex items-center justify-center h-8 w-8 rounded-full bg-amber-100 text-amber-700 font-bold">3</span>
                            <div class="ml-4">
                                <h4 class="font-semibold">Sblocca Ricompense NFT</h4>
                                <p class="text-stone-600">Ottieni badge digitali unici (NFT) che certificano il tuo impegno sulla Blockchain.</p>
                            </div>
                        </li>
                    </ol>
                     <div class="mt-8 grid grid-cols-3 gap-4">
                         <div class="p-3 bg-white rounded-lg shadow text-center">
                            <div class="text-3xl">🥉</div>
                            <p class="text-xs font-semibold mt-1">Volontario Bronzo</p>
                            <span class="text-xxs text-stone-500">Comune</span>
                         </div>
                         <div class="p-3 bg-white rounded-lg shadow text-center">
                            <div class="text-3xl">🌍</div>
                            <p class="text-xs font-semibold mt-1">Eco Warrior</p>
                            <span class="text-xxs text-stone-500">Raro</span>
                         </div>
                          <div class="p-3 bg-white rounded-lg shadow text-center">
                            <div class="text-3xl">🏆</div>
                            <p class="text-xs font-semibold mt-1">Volontario Oro</p>
                            <span class="text-xxs text-stone-500">Leggendario</span>
                         </div>
                     </div>
                </div>
                 <div class="mt-12 lg:mt-0 p-6 bg-white rounded-xl shadow-lg">
                    <h3 class="text-xl font-bold text-center">Come accumulare Punti VR</h3>
                    <p class="text-center text-sm text-stone-500 mb-4">Esempi di ricompense.</p>
                    <div class="chart-container h-80">
                        <canvas id="pointsChart"></canvas>
                    </div>
                </div>
            </div>
        </section>

         <section id="tecnologia" class="py-16 sm:py-20 section-fade-in">
            <div class="text-center">
                <h2 class="text-3xl font-bold tracking-tight">La Tecnologia al Servizio della Comunità</h2>
                <p class="mt-3 text-lg text-stone-600 max-w-2xl mx-auto">Utilizziamo strumenti all'avanguardia per garantire trasparenza, efficienza e un'esperienza utente moderna e sicura.</p>
            </div>
            <div class="mt-12 grid grid-cols-2 sm:grid-cols-3 lg:grid-cols-5 gap-8 text-center">
                <div class="p-4 bg-white rounded-xl shadow-md">
                    <div class="text-4xl">🔗</div>
                    <h3 class="mt-2 font-semibold">Blockchain</h3>
                    <p class="text-sm text-stone-500">Per trasparenza e certificazione (NFT).</p>
                </div>
                <div class="p-4 bg-white rounded-xl shadow-md">
                    <div class="text-4xl">🤖</div>
                    <h3 class="mt-2 font-semibold">Intelligenza Artificiale</h3>
                    <p class="text-sm text-stone-500">Per ottimizzare e semplificare le interazioni.</p>
                </div>
                <div class="p-4 bg-white rounded-xl shadow-md">
                    <div class="text-4xl">📱</div>
                    <h3 class="mt-2 font-semibold">React</h3>
                    <p class="text-sm text-stone-500">Per un'interfaccia web moderna e veloce.</p>
                </div>
                <div class="p-4 bg-white rounded-xl shadow-md">
                     <div class="text-4xl">📦</div>
                    <h3 class="mt-2 font-semibold">IPFS</h3>
                    <p class="text-sm text-stone-500">Per l'archiviazione decentralizzata dei dati.</p>
                </div>
                <div class="p-4 bg-white rounded-xl shadow-md col-span-2 sm:col-span-1 lg:col-span-1">
                     <div class="text-4xl">⚙️</div>
                    <h3 class="mt-2 font-semibold">n8n</h3>
                    <p class="text-sm text-stone-500">Per l'automazione dei processi.</p>
                </div>
            </div>
        </section>

    </main>
    
    <footer class="bg-stone-800 text-white mt-20">
        <div class="container mx-auto py-8 px-4 sm:px-6 lg:px-8 text-center">
            <p class="font-bold text-lg">Volontà Reale</p>
            <p class="text-sm text-stone-400 mt-1">Un progetto di Tatuma per il Comune di Mozzate.</p>
            <p class="text-xs text-stone-500 mt-4">&copy; 2025 Tatuma. Tutti i diritti riservati.</p>
        </div>
    </footer>

<script>
    const missionData = [
        { id: 1, title: "Parco Splendente", category: "Ambiente", points: 75, time: "2-3 ore", description: "Raccogli rifiuti e detriti dal Parco Comunale per mantenerlo pulito e sicuro." },
        { id: 2, title: "Sentieri Puliti", category: "Ambiente", points: 90, time: "3-4 ore", description: "Mantieni puliti e accessibili i sentieri naturali e le aree verdi periferiche." },
        { id: 3, title: "Fioritura Urbana", category: "Abbellimento", points: 80, time: "2-4 ore", description: "Pianta fiori e piccole piante in aiuole pubbliche per migliorare l'estetica urbana." },
        { id: 4, title: "Murales Comunitario", category: "Abbellimento", points: 200, time: "Più sessioni", description: "Realizza opere d'arte su pareti pubbliche per trasformare spazi anonimi." },
        { id: 5, title: "Eco-Informatore", category: "Ambiente", points: 100, time: "3-5 ore", description: "Distribuisci materiale informativo sulla raccolta differenziata e buone pratiche ambientali." },
        { id: 6, title: "Workshop Green", category: "Ambiente", points: 180, time: "4 ore", description: "Organizza laboratori pratici su temi come il riciclo creativo o il compostaggio." },
        { id: 7, title: "Spesa Solidale", category: "Sociale", points: 60, time: "1-2 ore", description: "Effettua la spesa o ritira farmaci per anziani o persone con difficoltà motorie." },
        { id: 8, title: "Compagnia Digitale", category: "Sociale", points: 70, time: "1-2 ore", description: "Offri supporto tecnologico e compagnia a distanza ad anziani o persone sole." },
        { id: 9, title: "Lettore Animato", category: "Cultura", points: 80, time: "2 ore", description: "Leggi storie e anima sessioni di lettura per bambini in biblioteca." },
        { id: 10, title: "Guida Turistica Locale", category: "Cultura", points: 120, time: "2-3 ore", description: "Accompagna gruppi alla scoperta della storia e delle curiosità di Mozzate." },
        { id: 11, title: "Tutor Linguistico", category: "Inclusione", points: 70, time: "1-2 ore", description: "Offri supporto linguistico a cittadini stranieri per facilitare la loro integrazione." },
        { id: 12, title: "Eventi Inclusivi", category: "Inclusione", points: 100, time: "3+ ore", description: "Supporta l'organizzazione di eventi che promuovono la diversità e l'uguaglianza." },
    ];

    const missionGrid = document.getElementById('mission-grid');
    const filterButtons = document.querySelectorAll('.mission-filter-btn');
    let missionsChart;
    let pointsChart;

    const categoryColors = {
        'Ambiente': 'rgba(20, 184, 166, 0.7)',
        'Abbellimento': 'rgba(245, 158, 11, 0.7)',
        'Sociale': 'rgba(59, 130, 246, 0.7)',
        'Cultura': 'rgba(139, 92, 246, 0.7)',
        'Inclusione': 'rgba(236, 72, 153, 0.7)'
    };

    const categoryBorderColors = {
        'Ambiente': 'rgb(20, 184, 166)',
        'Abbellimento': 'rgb(245, 158, 11)',
        'Sociale': 'rgb(59, 130, 246)',
        'Cultura': 'rgb(139, 92, 246)',
        'Inclusione': 'rgb(236, 72, 153)'
    };
    
    function createMissionCard(mission) {
        return `
            <div class="mission-card bg-white rounded-xl shadow-md overflow-hidden transition-transform transform hover:-translate-y-1" data-category="${mission.category}">
                <div class="p-6">
                    <div class="flex justify-between items-sta

</head>
<body>
  <div class="container">
    <h1>TATUMA Dev.Chain</h1>
    <p class="lead">Un ecosistema decentralizzato per applicazioni Web3, automazioni AI e finanza distribuita. Costruito da pionieri, per pionieri.</p><div class="section">
  <h2>Perché TATUMA?</h2>
  <ul>
    <li>Architettura modulare basata su agenti AI intelligenti.</li>
    <li>Automazioni predittive integrate (Es. Serie A, smart data routing).</li>
    <li>Tokenizzazione asset reali e gestione flussi DeFi.</li>
    <li>Onboarding semplificato tramite tools low-code & no-code.</li>
  </ul>
</div>

<div class="section">
  <h2>Servizi Core</h2>
  <ul>
    <li>Smart Contracts personalizzati</li>
    <li>Pipeline AI & LLM per processi aziendali</li>
    <li>Aggregazione dati per viaggi e asset digitali</li>
    <li>VolontaRealmente: impatto sociale via NFT</li>
  </ul>
</div>

<div class="section">
  <h2>Integrazioni</h2>
  <ul>
    <li>Blockchain Layer1 & Layer2 compatibili</li>
    <li>n8n, XGBoost, Whisper, LangChain, Pinecone</li>
    <li>Telegram Bot, Web App, Automazioni su misura</li>
  </ul>
</div>

<footer>
  &copy; 2025 TATUMA Dev.Chain. Powered by Tatuma LCC. Made with TheWolFøFChain 2025©



<h1>Benvenuto in TA2MA&trade;</h1>
<h2>Dev.Chain.Model</h2>
<p><strong>Automazione, flessibilità e AI open-source</strong></p>

<!-- Contatti -->
<h2>Contatti</h2>
<p>
  <strong>Nome:</strong> Anwar Zbir<br>
  <strong>Indirizzo:</strong> Via Gorla 4, Mozzate (22076)<br>
  <strong>Email:</strong> <a href="mailto:ta2ma@gmx.us">ta2ma@gmx.us</a><br>
  <strong>Telefono:</strong> 3516328005
</p>

<!-- Chi siamo -->
<h2>Chi siamo</h2>
<p>
Negli ultimi anni, l'automazione dei flussi di lavoro si è evoluta da semplice strumento di supporto a vero e proprio motore strategico per molte organizzazioni.
</p>
<p>
Tra le soluzioni disponibili, <strong>TA2MA&trade;</strong> si distingue per il suo approccio <strong>open-source</strong>, che combina potenza e personalizzazione per ottimizzare processi e migliorare l'efficienza aziendale.
</p>

<!-- Caratteristiche -->
<h2>Cosa rende TA2MA&trade; speciale?</h2>

<h3>Dev.Chain.Model</h3>
<p>
Una piattaforma innovativa che offre automazione avanzata, riducendo il bisogno di scrivere codice e semplificando l'integrazione con l'intelligenza artificiale.
</p>

<h3>Low-code e potenza</h3>
<p>
Grazie a un'interfaccia <em>visuale a nodi</em>, è possibile creare flussi complessi con facilità. Questo consente di:
</p>
<ul>
  <li>Automatizzare attività come notifiche, aggiornamenti di database e analisi dei dati.</li>
  <li>Ottimizzare il tempo e ridurre errori manuali nei processi aziendali.</li>
</ul>

<h3>Integrazione con l'AI</h3>
<p>
TA2MA&trade; supporta modelli avanzati di Intelligenza Artificiale (LLM) attraverso framework come <strong>LangChain</strong>. Questo permette di costruire agenti intelligenti capaci di:
</p>
<ul>
  <li>Interagire con documenti e database.</li>
  <li>Effettuare analisi avanzate e categorizzazioni.</li>
  <li>Supportare decision-making automatizzato.</li>
</ul>

<h3>Flussi multi-agente</h3>
<p>
L'architettura di TA2MA&trade; consente di progettare flussi in cui <strong>più agenti collaborano</strong>:
</p>
<ul>
  <li>Un agente può estrarre dati.</li>
  <li>Un altro può analizzarli.</li>
  <li>Il tutto avviene in modo automatizzato all'interno dello stesso sistema.</li>
</ul>

<h3>Flessibilità totale</h3>
<p>
Essendo <strong>open-source</strong>, TA2MA&trade; offre:
</p>
<ul>
  <li>Personalizzazione avanzata.</li>
  <li>Possibilità di ospitare il sistema su server proprietari.</li>
  <li>Riduzione dei costi rispetto a piattaforme SaaS come Zapier.</li>
</ul>

<!-- Utilizzo -->
<h2>Chi utilizza TA2MA&trade;?</h2>
<p>
Dai liberi professionisti alle grandi organizzazioni, TA2MA&trade; trova applicazione in vari settori, tra cui:
</p>
<ul>
  <li><strong>Marketing</strong> – Automazione di campagne e gestione clienti.</li>
  <li><strong>Gestione IT</strong> – Monitoraggio e risoluzione di problemi tecnici.</li>
  <li><strong>Analisi legale</strong> – Supporto nella gestione di documenti e processi legali.</li>
</ul>
<p>
Grazie alla sua versatilità, TA2MA&trade; si adatta a qualsiasi contesto professionale.
</p>

<!-- Conclusione e Contatti -->
<h2>Contattaci per maggiori informazioni</h2>
<p>
Siamo pronti ad aiutarti a integrare <strong>TA2MA&trade;</strong> nei tuoi processi aziendali. Contattaci oggi stesso!
</p>
<ul>
  <li><strong>Email:</strong> <a href="mailto:ta2ma@gmx.us">ta2ma@gmx.us</a></li>
  <li><strong>Telefono:</strong> 329 215 1121</li>
  <li><strong>Indirizzo:</strong> Via Gorla 4, Mozzate (22076)</li>
</ul>

</body>
</html>
</head>





