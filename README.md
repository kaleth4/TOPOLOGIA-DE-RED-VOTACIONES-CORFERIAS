<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Topología de Red: Corferias Elecciones</title>
<script src="https://cdn.tailwindcss.com"></script>
<script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;800&display=swap" rel="stylesheet">
<style>
    body {
        font-family: 'Inter', sans-serif;
        background-color: #F8F9FA;
        color: #0A2540;
    }
    .bg-dark-blue { background-color: #0A2540; }
    .text-dark-blue { color: #0A2540; }
    .bg-indigo { background-color: #635BFF; }
    .text-indigo { color: #635BFF; }
    .bg-cyan { background-color: #00D4FF; }
    .text-cyan { color: #00D4FF; }
    .bg-pink { background-color: #FF4263; }
    .bg-green { background-color: #00D28B; }
    .text-green { color: #00D28B; }

    .chart-container {
        position: relative;
        width: 100%;
        max-width: 600px;
        margin-left: auto;
        margin-right: auto;
        height: 300px;
        max-height: 400px;
    }
    @media (min-width: 768px) {
        .chart-container {
            height: 380px;
        }
    }
    .node-card {
        transition: transform 0.2s;
    }
    .node-card:hover {
        transform: translateY(-5px);
    }
</style>
</head>
<body class="antialiased">

<header class="bg-dark-blue text-white py-12 px-6 lg:px-12 shadow-lg mb-10">
    <div class="max-w-6xl mx-auto">
        <div class="uppercase tracking-widest text-cyan font-bold text-sm mb-2">Análisis de Infraestructura Crítica</div>
        <h1 class="text-4xl md:text-5xl font-extrabold mb-4 leading-tight">Arquitectura de Red Electoral en Corferias</h1>
        <p class="text-lg md:text-xl text-gray-300 max-w-3xl">
            Corferias funciona como el puesto de votación y centro de consolidación de datos más grande de Colombia durante las jornadas electorales. Este documento técnico visualiza la topología jerárquica de alta disponibilidad, los flujos de tráfico y los protocolos de seguridad implementados por la Registraduría Nacional para garantizar cero caídas y máxima integridad de los datos.
        </p>
    </div>
</header>

<main class="max-w-6xl mx-auto px-6 lg:px-12 pb-20">

    <section class="mb-16">
        <h2 class="text-3xl font-bold mb-6 text-dark-blue border-b-4 border-indigo inline-block pb-2">Métricas de Desempeño Core</h2>
        <p class="text-gray-700 mb-8 text-lg">
            Para soportar la concurrencia masiva y la transmisión segura de los formularios E-14 y la biometría, la red opera bajo estándares de grado portador (carrier-grade).
        </p>
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6">
            <div class="bg-white rounded-xl shadow-md p-6 border-l-4 border-indigo">
                <div class="text-indigo text-4xl mb-2">&#9889;</div>
                <div class="text-3xl font-bold text-dark-blue mb-1">99.999%</div>
                <div class="text-sm text-gray-500 uppercase tracking-wide font-semibold">Uptime Requerido</div>
            </div>
            <div class="bg-white rounded-xl shadow-md p-6 border-l-4 border-cyan">
                <div class="text-cyan text-4xl mb-2">&#128246;</div>
                <div class="text-3xl font-bold text-dark-blue mb-1">20 Gbps</div>
                <div class="text-sm text-gray-500 uppercase tracking-wide font-semibold">Ancho de Banda Dual</div>
            </div>
            <div class="bg-white rounded-xl shadow-md p-6 border-l-4 border-green">
                <div class="text-green text-4xl mb-2">&#9201;</div>
                <div class="text-3xl font-bold text-dark-blue mb-1">&lt; 5 ms</div>
                <div class="text-sm text-gray-500 uppercase tracking-wide font-semibold">Latencia Interna</div>
            </div>
            <div class="bg-white rounded-xl shadow-md p-6 border-l-4 border-pink">
                <div class="text-pink text-4xl mb-2">&#128274;</div>
                <div class="text-3xl font-bold text-dark-blue mb-1">AES-256</div>
                <div class="text-sm text-gray-500 uppercase tracking-wide font-semibold">Cifrado End-to-End</div>
            </div>
        </div>
    </section>

    <section class="mb-16">
        <h2 class="text-3xl font-bold mb-6 text-dark-blue border-b-4 border-indigo inline-block pb-2">Topología Jerárquica de Alta Disponibilidad</h2>
        <p class="text-gray-700 mb-8 text-lg">
            La infraestructura se diseña utilizando el modelo jerárquico de Cisco de tres capas. Esto permite aislamiento de fallos, escalabilidad masiva en pabellones y segmentación estricta entre la red pública de medios y la red privada de escrutinio.
        </p>
        
        <div class="bg-white rounded-xl shadow-lg p-8">
            <div class="flex flex-col items-center">
                
                <div class="w-full max-w-2xl bg-slate-100 rounded-lg p-4 mb-4 border-2 border-slate-300 text-center relative z-10 node-card">
                    <div class="font-bold text-xl text-dark-blue mb-2">Capa de Núcleo (Core Layer)</div>
                    <div class="flex justify-center gap-4">
                        <div class="bg-indigo text-white px-4 py-2 rounded shadow">Router Core A (ISP 1)</div>
                        <div class="bg-indigo text-white px-4 py-2 rounded shadow">Router Core B (ISP 2)</div>
                    </div>
                    <div class="text-xs text-gray-600 mt-2">Conmutación de alta velocidad, enrutamiento BGP hacia Registraduría, Firewalls Perimetrales HA.</div>
                </div>

                <div class="text-2xl text-indigo my-[-10px] z-0">&#8595; &#8595;</div>

                <div class="w-full max-w-3xl bg-slate-100 rounded-lg p-4 mb-4 border-2 border-slate-300 text-center relative z-10 node-card">
                    <div class="font-bold text-xl text-dark-blue mb-2">Capa de Distribución (Distribution Layer)</div>
                    <div class="flex flex-wrap justify-center gap-4">
                        <div class="bg-cyan text-dark-blue font-semibold px-4 py-2 rounded shadow">Switch L3 Pabellones Escrutinio</div>
                        <div class="bg-cyan text-dark-blue font-semibold px-4 py-2 rounded shadow">Switch L3 Transmisión</div>
                        <div class="bg-cyan text-dark-blue font-semibold px-4 py-2 rounded shadow">Switch L3 Prensa/Público</div>
                    </div>
                    <div class="text-xs text-gray-600 mt-2">Políticas de enrutamiento, filtrado ACL, terminación VLAN, segmentación de tráfico crítico vs no crítico.</div>
                </div>

                <div class="flex justify-around w-full max-w-3xl text-2xl text-cyan my-[-10px] z-0">
                    <div>&#8595;</div>
                    <div>&#8595;</div>
                    <div>&#8595;</div>
                </div>

                <div class="w-full max-w-4xl bg-slate-100 rounded-lg p-4 border-2 border-slate-300 text-center relative z-10 node-card">
                    <div class="font-bold text-xl text-dark-blue mb-2">Capa de Acceso (Access Layer)</div>
                    <div class="grid grid-cols-2 md:grid-cols-4 gap-4">
                        <div class="bg-white border-2 border-gray-200 p-2 rounded shadow">
                            <div class="text-xs font-bold text-dark-blue">Estaciones Biométricas</div>
                            <div class="text-xs text-gray-500">Móviles / Tablets</div>
                        </div>
                        <div class="bg-white border-2 border-gray-200 p-2 rounded shadow">
                            <div class="text-xs font-bold text-dark-blue">Portátiles Transmisión</div>
                            <div class="text-xs text-gray-500">Ethernet Seguro</div>
                        </div>
                        <div class="bg-white border-2 border-gray-200 p-2 rounded shadow">
                            <div class="text-xs font-bold text-dark-blue">Access Points (Wi-Fi)</div>
                            <div class="text-xs text-gray-500">Red SSID Prensa</div>
                        </div>
                        <div class="bg-white border-2 border-gray-200 p-2 rounded shadow">
                            <div class="text-xs font-bold text-dark-blue">Sistemas Auditoría</div>
                            <div class="text-xs text-gray-500">Acceso LAN Restringido</div>
                        </div>
                    </div>
                    <div class="text-xs text-gray-600 mt-2">Switches L2 PoE+, Puntos de acceso inalámbrico, autenticación de puertos 802.1X.</div>
                </div>

            </div>
        </div>
    </section>

    <div class="grid grid-cols-1 md:grid-cols-2 gap-8 mb-16">
        <section class="bg-white rounded-xl shadow-lg p-6">
            <h3 class="text-2xl font-bold mb-4 text-dark-blue">Volumen de Tráfico por Hora</h3>
            <p class="text-gray-600 text-sm mb-6">
                El tráfico de red sigue un patrón predecible durante el día de elecciones, con picos significativos durante la validación matutina y el cierre de urnas a las 4:00 PM para la transmisión de preconteo.
            </p>
            <div class="chart-container">
                <canvas id="trafficChart"></canvas>
            </div>
        </section>

        <section class="bg-white rounded-xl shadow-lg p-6">
            <h3 class="text-2xl font-bold mb-4 text-dark-blue">Distribución de Ancho de Banda</h3>
            <p class="text-gray-600 text-sm mb-6">
                Mediante QoS (Quality of Service), se prioriza el tráfico crítico (biometría y escrutinio) sobre la red pública y de medios para evitar congestión en el núcleo.
            </p>
            <div class="chart-container">
                <canvas id="distributionChart"></canvas>
            </div>
        </section>
    </div>

    <section class="bg-white rounded-xl shadow-lg p-8 mb-16">
        <div class="grid grid-cols-1 md:grid-cols-2 gap-8 items-center">
            <div>
                <h3 class="text-3xl font-bold mb-4 text-dark-blue border-b-4 border-pink inline-block pb-2">Matriz de Seguridad y Resiliencia</h3>
                <p class="text-gray-700 mb-4 text-lg">
                    La topología no solo busca velocidad, sino invulnerabilidad. El gráfico ilustra la fortaleza relativa de los cinco pilares de seguridad implementados en la red LAN/WAN de Corferias.
                </p>
                <ul class="space-y-3 mt-6">
                    <li class="flex items-start">
                        <span class="text-pink font-bold mr-2">&#10003;</span>
                        <span class="text-sm text-gray-800"><strong class="text-dark-blue">Segmentación VLAN:</strong> Aislamiento total entre dispositivos de transmisión oficial y dispositivos de terceros.</span>
                    </li>
                    <li class="flex items-start">
                        <span class="text-pink font-bold mr-2">&#10003;</span>
                        <span class="text-sm text-gray-800"><strong class="text-dark-blue">IDS/IPS Activo:</strong> Detección y prevención de intrusiones en tiempo real analizando anomalías de tráfico.</span>
                    </li>
                    <li class="flex items-start">
                        <span class="text-pink font-bold mr-2">&#10003;</span>
                        <span class="text-sm text-gray-800"><strong class="text-dark-blue">Túneles VPN:</strong> Todo dato oficial viaja encapsulado vía IPsec hacia los datacenters de la Registraduría.</span>
                    </li>
                </ul>
            </div>
            <div>
                <div class="chart-container">
                    <canvas id="securityRadarChart"></canvas>
                </div>
            </div>
        </div>
    </section>

</main>

<footer class="bg-dark-blue text-white py-8 text-center text-sm">
    <p>&copy; 2026 Análisis de Infraestructura Crítica Electoral. Datos y estructuras basados en modelos arquitectónicos estándar de telecomunicaciones para eventos masivos.</p>
</footer>

<script>
    function wrapLabel(label) {
        if (label.length <= 16) return label;
        let words = label.split(' ');
        let lines = [];
        let currentLine = '';
        for (let word of words) {
            if ((currentLine + word).length > 16) {
                if (currentLine) lines.push(currentLine.trim());
                currentLine = word + ' ';
            } else {
                currentLine += word + ' ';
            }
        }
        if (currentLine) lines.push(currentLine.trim());
        return lines;
    }

    const chartTooltipConfig = {
        tooltip: {
            callbacks: {
                title: function(tooltipItems) {
                    const item = tooltipItems[0];
                    let label = item.chart.data.labels[item.dataIndex];
                    if (Array.isArray(label)) {
                        return label.join(' ');
                    } else {
                        return label;
                    }
                }
            }
        }
    };

    const colors = {
        indigo: '#635BFF',
        cyan: '#00D4FF',
        pink: '#FF4263',
        green: '#00D28B',
        darkBlue: '#0A2540',
        gray: '#E2E8F0'
    };

    const rawTrafficLabels = ['08:00 AM (Apertura)', '10:00 AM', '12:00 PM (Mediodía)', '02:00 PM', '04:00 PM (Cierre/Preconteo)', '06:00 PM (Transmisión)'];
    const trafficLabels = rawTrafficLabels.map(wrapLabel);
    
    const ctxTraffic = document.getElementById('trafficChart').getContext('2d');
    new Chart(ctxTraffic, {
        type: 'bar',
        data: {
            labels: trafficLabels,
            datasets: [{
                label: 'Carga de Red (Tbps)',
                data: [2.5, 4.8, 5.2, 4.5, 12.5, 18.0],
                backgroundColor: colors.indigo,
                borderRadius: 4
            }]
        },
        options: {
            responsive: true,
            maintainAspectRatio: false,
            plugins: {
                ...chartTooltipConfig,
                legend: { display: false }
            },
            scales: {
                y: {
                    beginAtZero: true,
                    grid: { color: colors.gray }
                },
                x: {
                    grid: { display: false }
                }
            }
        }
    });

    const rawDistLabels = ['Transmisión E-14 (Encriptado)', 'Validación Biométrica', 'Red Administrativa Local', 'Red de Medios/Prensa'];
    const distLabels = rawDistLabels.map(wrapLabel);

    const ctxDist = document.getElementById('distributionChart').getContext('2d');
    new Chart(ctxDist, {
        type: 'doughnut',
        data: {
            labels: distLabels,
            datasets: [{
                data: [45, 25, 10, 20],
                backgroundColor: [colors.pink, colors.cyan, colors.green, colors.darkBlue],
                borderWidth: 2,
                borderColor: '#ffffff'
            }]
        },
        options: {
            responsive: true,
            maintainAspectRatio: false,
            cutout: '65%',
            plugins: {
                ...chartTooltipConfig,
                legend: { position: 'bottom' }
            }
        }
    });

    const rawRadarLabels = ['Firewalls Alta Disponibilidad', 'Cifrado de Túneles VPN', 'Segmentación VLAN Estricta', 'Prevención Intrusos IDS/IPS', 'Redundancia Física (ISP/Energía)'];
    const radarLabels = rawRadarLabels.map(wrapLabel);

    const ctxRadar = document.getElementById('securityRadarChart').getContext('2d');
    new Chart(ctxRadar, {
        type: 'radar',
        data: {
            labels: radarLabels,
            datasets: [{
                label: 'Nivel de Implementación (0-100)',
                data: [98, 100, 95, 90, 99],
                backgroundColor: 'rgba(0, 212, 255, 0.2)',
                borderColor: colors.cyan,
                pointBackgroundColor: colors.pink,
                pointBorderColor: '#fff',
                pointHoverBackgroundColor: '#fff',
                pointHoverBorderColor: colors.pink,
                borderWidth: 2
            }]
        },
        options: {
            responsive: true,
            maintainAspectRatio: false,
            scales: {
                r: {
                    angleLines: { color: colors.gray },
                    grid: { color: colors.gray },
                    pointLabels: {
                        font: { size: 11, family: 'Inter' },
                        color: colors.darkBlue
                    },
                    suggestedMin: 50,
                    suggestedMax: 100
                }
            },
            plugins: {
                ...chartTooltipConfig,
                legend: { display: false }
            }
        }
    });
</script>
</body>
</html>
