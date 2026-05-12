<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>2026 Content Provenance Risk Intelligence</title>
<script src="https://cdn.tailwindcss.com"></script>
<script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
<script src="https://cdn.plot.ly/plotly-2.32.0.min.js"></script>
<script>
tailwind.config = {
theme: {
extend: {
colors: {
bgbase: '#0f172a',
cardbg: '#1e293b',
neonblue: '#06b6d4',
alertorange: '#f97316',
electricpink: '#ec4899',
textlight: '#f8fafc',
textdim: '#cbd5e1'
},
fontFamily: {
sans: ['Inter', 'sans-serif']
}
}
}
}
</script>
<style>
body { background-color: #0f172a; color: #f8fafc; font-family: 'Inter', sans-serif; scroll-behavior: smooth; }
.card-elevation { box-shadow: 0 10px 15px -3px rgba(0,0,0,0.5), 0 4px 6px -4px rgba(0,0,0,0.5); }
.chart-container { position: relative; width: 100%; max-width: 800px; margin-left: auto; margin-right: auto; height: 350px; max-height: 400px; }
@media (max-width: 768px) { .chart-container { height: 280px; } }
.flow-box { border: 2px solid #06b6d4; border-radius: 0.5rem; padding: 1.25rem; background-color: #1e293b; text-align: center; position: relative; z-index: 10; width: 100%; }
.flow-arrow { font-size: 1.5rem; color: #f97316; font-weight: bold; padding: 0.5rem; }
@media (max-width: 767px) { .flow-arrow { transform: rotate(90deg); } }
.flow-threat { border: 1px dashed #f97316; background-color: rgba(249, 115, 22, 0.1); color: #f97316; padding: 0.25rem; border-radius: 0.25rem; font-size: 0.75rem; margin-top: 0.5rem; }
.step-dot { background: #ec4899; color: white; width: 1.5rem; height: 1.5rem; display: flex; align-items: center; justify-content: center; border-radius: 50%; font-weight: bold; margin-right: 0.75rem; flex-shrink: 0; font-size: 0.75rem; }
/* Modal Styles */
#riskModal { display: none; position: fixed; inset: 0; background: rgba(15, 23, 42, 0.95); backdrop-filter: blur(8px); z-index: 100; align-items: center; justify-content: center; padding: 1.5rem; }
#riskModal.active { display: flex; }
.modal-content { background: #1e293b; width: 100%; max-width: 1200px; max-height: 90vh; border: 1px solid #334155; border-radius: 1rem; overflow: hidden; display: flex; flex-direction: column; }
::-webkit-scrollbar { width: 8px; }
::-webkit-scrollbar-track { background: #0f172a; }
::-webkit-scrollbar-thumb { background: #1e293b; border-radius: 4px; }
</style>
</head>
<body class="antialiased min-h-screen">

<nav class="sticky top-0 bg-bgbase/90 backdrop-blur-md border-b border-gray-800 z-50 p-4">
<div class="max-w-7xl mx-auto flex justify-between items-center">
<div class="text-xl font-bold text-neonblue tracking-tight uppercase italic">Provenance<span class="text-textlight">Watch</span> 2026</div>
<div class="hidden lg:flex space-x-6 text-[10px] font-black uppercase tracking-widest text-textdim">
<a href="#overview" class="hover:text-neonblue transition">Overview</a>
<a href="#swot" class="hover:text-neonblue transition">SWOT</a>
<a href="#vectors" class="hover:text-neonblue transition">Vectors</a>
<a href="#priority" class="hover:text-neonblue transition">Priority Matrix</a>
<a href="#strategy" class="hover:text-neonblue transition">Strategy</a>
</div>
</div>
</nav>

<main class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-12">

<header class="mb-20 text-center">
<h1 class="text-4xl md:text-6xl font-black mb-6 leading-tight">
Content Provenance & <br><span class="text-transparent bg-clip-text bg-gradient-to-r from-neonblue to-electricpink">Forensic Risk Intelligence</span>
</h1>
<p class="text-lg text-textdim max-w-2xl mx-auto italic">
Analyzing end-to-end supply chain vulnerabilities from sensor capture to authenticated publication.
</p>
</header>

<section id="overview" class="mb-24">
<div class="grid grid-cols-1 lg:grid-cols-3 gap-8">
<div class="lg:col-span-2 bg-cardbg p-8 rounded-2xl card-elevation border-t-4 border-neonblue">
<h2 class="text-2xl font-bold mb-4 text-neonblue">Strategic Context</h2>
<p class="text-textdim leading-relaxed mb-6 text-sm">
As generative AI achieves photorealistic parity, the 2026 media landscape relies on <strong>C2PA v2.4</strong> as the primary trust mechanism. However, cryptographic signatures are not a panacea. Our audit identifies 15 distinct vulnerabilities—most critically at the hardware/sensor interface—that allow "laundered" synthetic content to appear cryptographically authentic.
</p>
<div class="grid grid-cols-2 md:grid-cols-4 gap-4">
<div class="bg-bgbase p-4 rounded-xl border border-gray-800 text-center">
<div class="text-2xl font-bold text-neonblue">15</div>
<div class="text-[10px] uppercase text-gray-500 font-bold mt-1">Identified Risks</div>
</div>
<div class="bg-bgbase p-4 rounded-xl border border-gray-800 text-center">
<div class="text-2xl font-bold text-electricpink">8</div>
<div class="text-[10px] uppercase text-gray-500 font-bold mt-1">Categories</div>
</div>
<div class="bg-bgbase p-4 rounded-xl border border-gray-800 text-center">
<div class="text-2xl font-bold text-alertorange">7.8</div>
<div class="text-[10px] uppercase text-gray-500 font-bold mt-1">Avg Severity</div>
</div>
<div class="bg-bgbase p-4 rounded-xl border border-gray-800 text-center">
<div class="text-2xl font-bold text-neonblue">69%</div>
<div class="text-[10px] uppercase text-gray-500 font-bold mt-1">Detection Efficacy</div>
</div>
</div>
</div>
<div class="bg-cardbg p-8 rounded-2xl border-t-4 border-alertorange flex flex-col justify-between">
<div>
<h3 class="text-xl font-bold mb-2 text-alertorange">Critical Alert: R4</h3>
<div class="text-xs font-bold text-textlight mb-2 uppercase">Hardware Injection</div>
<p class="text-[11px] text-textdim mb-4 leading-relaxed">Adversaries feeding synthetic data directly into the camera's TEE to generate "valid" provenance on fake images. This represents a foundational break in the "optical reality" chain.</p>
</div>
<div class="p-3 bg-bgbase rounded-lg border border-alertorange/30 text-center">
<div class="text-[9px] text-alertorange font-bold uppercase mb-2">Mitigation Readiness: LOW</div>
<div class="w-full bg-gray-800 h-1 rounded-full">
<div class="bg-alertorange h-full" style="width: 25%"></div>
</div>
</div>
</div>
</div>
</section>

<section id="swot" class="mb-24">
<div class="mb-10">
<h2 class="text-3xl font-bold mb-4 border-l-4 border-neonblue pl-4">Ecosystem SWOT Analysis</h2>
<p class="text-textdim max-w-4xl text-sm">
Assessing the current state of provenance implementation highlights the disparity between robust cryptographic standards and the practical realities of media distribution in 2026.
</p>
</div>

<div class="grid grid-cols-1 md:grid-cols-2 gap-6">
<div class="bg-cardbg p-6 rounded-xl border border-gray-800 card-elevation hover:border-neonblue transition duration-300">
<div class="flex items-center gap-3 mb-4">
<div class="text-3xl">&#128737;</div>
<h3 class="text-xl font-bold text-neonblue">Strengths</h3>
</div>
<ul class="list-disc list-inside text-textdim space-y-2 text-xs">
<li>Hardware-backed signing via Trusted Execution Environments.</li>
<li>Standardized C2PA v2.4 metadata and JUMBF manifests.</li>
<li>Auditable additive manifest history.</li>
<li>TDM assertions actively protecting Intellectual Property.</li>
</ul>
</div>

<div class="bg-cardbg p-6 rounded-xl border border-gray-800 card-elevation hover:border-alertorange transition duration-300">
<div class="flex items-center gap-3 mb-4">
<div class="text-3xl">&#9888;</div>
<h3 class="text-xl font-bold text-alertorange">Weaknesses</h3>
</div>
<ul class="list-disc list-inside text-textdim space-y-2 text-xs">
<li>Temporal vulnerabilities (timestamp stripping).</li>
<li>Hardware injection exploits (Nikon Z6 III case).</li>
<li>Lack of real-time OCSP/CRL revocation checks.</li>
<li>Fragile soft bindings and perceptual hashes.</li>
</ul>
</div>

<div class="bg-cardbg p-6 rounded-xl border border-gray-800 card-elevation hover:border-neonblue transition duration-300">
<div class="flex items-center gap-3 mb-4">
<div class="text-3xl">&#128640;</div>
<h3 class="text-xl font-bold text-neonblue">Opportunities</h3>
</div>
<ul class="list-disc list-inside text-textdim space-y-2 text-xs">
<li>EU AI Act (Article 50) driving mandatory compliance.</li>
<li>RFC 3161 Trusted Timestamping integration.</li>
<li>Shift toward comprehensive "Zero-Trust" workflows.</li>
<li>Monetization of premium "authenticated" content streams.</li>
</ul>
</div>

<div class="bg-cardbg p-6 rounded-xl border border-gray-800 card-elevation hover:border-electricpink transition duration-300">
<div class="flex items-center gap-3 mb-4">
<div class="text-3xl">&#128128;</div>
<h3 class="text-xl font-bold text-electricpink">Threats</h3>
</div>
<ul class="list-disc list-inside text-textdim space-y-2 text-xs">
<li>Adversarial AI natively ignoring C2PA signals.</li>
<li>"Laundering" synthetic content via re-signing pipelines.</li>
<li>Severe degradation of traditional AI detection accuracy.</li>
<li>Legal liability for possessing "untrusted" archival content.</li>
</ul>
</div>
</div>
</section>

<section id="taxonomy" class="mb-24 grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
<div>
<h2 class="text-3xl font-bold mb-4 border-l-4 border-electricpink pl-4">Risk Distribution Taxonomy</h2>
<p class="text-textdim mb-6 text-sm">
A thorough analysis reveals 15 distinct factors spanning 8 categories. While **Operational** and **Strategic** risks dominate the current implementation cycle, Financial and ESG risks are accelerating as compliance deadlines loom.
</p>
<div class="bg-cardbg p-6 rounded-xl border border-gray-800">
<div class="chart-container h-80">
<canvas id="riskDonutChart"></canvas>
</div>
</div>
</div>
<div class="space-y-4">
<div class="p-6 bg-cardbg rounded-xl border border-gray-800">
<h4 class="text-xs font-bold text-textlight mb-2 uppercase tracking-widest underline decoration-neonblue decoration-2 underline-offset-4">Core Drivers</h4>
<p class="text-[11px] text-textdim leading-relaxed">Securing media provenance is no longer solely an IT issue; it requires cross-departmental strategy involving legal, editorial, and executive leadership to manage the trust lifecycle.</p>
</div>
<div class="p-6 bg-cardbg rounded-xl border border-gray-800">
<h4 class="text-xs font-bold text-textlight mb-2 uppercase tracking-widest underline decoration-alertorange decoration-2 underline-offset-4">Vulnerability Focus</h4>
<p class="text-[11px] text-textdim leading-relaxed">Integration complexity remains the #1 project risk, leading to "Unsigned Ingredient" warnings that paralyze fast-cycle news distribution.</p>
</div>
</div>
</section>

<section id="vectors" class="mb-24">
<h2 class="text-3xl font-bold mb-10 text-center uppercase tracking-tighter">Supply Chain Vulnerability Flow</h2>
<div class="bg-cardbg p-10 rounded-2xl card-elevation border border-gray-800 overflow-x-auto">
<div class="flex flex-col md:flex-row items-center justify-between w-full min-w-[800px] gap-4">
<div class="w-1/4">
<div class="flow-box">
<div class="text-2xl mb-2">&#128247;</div>
<div class="font-bold text-neonblue text-xs uppercase tracking-widest">1. Capture</div>
<div class="flow-threat">Exploit: TEE Injection</div>
</div>
</div>
<div class="flow-arrow">&#10142;</div>
<div class="w-1/4">
<div class="flow-box">
<div class="text-2xl mb-2">&#128187;</div>
<div class="font-bold text-neonblue text-xs uppercase tracking-widest">2. Edit</div>
<div class="flow-threat">Exploit: Broken Chain</div>
</div>
</div>
<div class="flow-arrow">&#10142;</div>
<div class="w-1/4">
<div class="flow-box">
<div class="text-2xl mb-2">&#127760;</div>
<div class="font-bold text-neonblue text-xs uppercase tracking-widest">3. Distribute</div>
<div class="flow-threat">Exploit: Manifest Strip</div>
</div>
</div>
<div class="flow-arrow">&#10142;</div>
<div class="w-1/4">
<div class="flow-box">
<div class="text-2xl mb-2">&#128065;</div>
<div class="font-bold text-neonblue text-xs uppercase tracking-widest">4. Verify</div>
<div class="flow-threat">Exploit: Time Spoofing</div>
</div>
</div>
</div>
</div>
</section>

<section id="priority" class="mb-24">
<div class="flex flex-col md:flex-row justify-between items-start md:items-center mb-10 gap-4">
<div>
<h2 class="text-3xl font-bold border-l-4 border-alertorange pl-4">Priority Prioritization Matrix</h2>
<p class="text-textdim text-xs mt-1">Mapping 15 Identified Risks: Likelihood (X) vs Impact (Y). Overlapping points are offset for visibility.</p>
</div>
<button onclick="toggleModal()" class="px-5 py-2.5 bg-neonblue/10 border border-neonblue text-neonblue text-[11px] font-black uppercase tracking-widest rounded-lg hover:bg-neonblue hover:text-bgbase transition duration-300 card-elevation">
Access Detailed Risk Register &#10142;
</button>
</div>
<div class="bg-cardbg p-4 rounded-2xl border border-gray-800">
<div id="plotlyScatter" style="width:100%; height:550px;"></div>
</div>
</section>

<section id="strategy" class="mb-24">
<div class="mb-10">
<h2 class="text-3xl font-bold mb-4 border-l-4 border-electricpink pl-4">Recommended Validation Strategy</h2>
<p class="text-textdim max-w-4xl text-sm mb-8">
Moving away from implicit trust to a "Zero-Trust Validation" workflow is essential. A valid signature is merely the first step; it must be coupled with rigorous technical audits.
</p>
</div>

<div class="bg-cardbg p-8 rounded-xl border border-gray-800 card-elevation">
<div class="grid grid-cols-1 md:grid-cols-2 gap-6">
<div class="flex items-start bg-bgbase p-5 rounded-lg border border-gray-700">
<div class="step-dot">1</div>
<div>
<h4 class="font-bold text-neonblue text-[11px] uppercase mb-1 tracking-widest">Signature Check</h4>
<p class="text-[10px] text-textdim leading-relaxed">Verify if the X.509 certificate is mathematically valid and originates from an entity on the 2026 Global Trust List.</p>
</div>
</div>

<div class="flex items-start bg-bgbase p-5 rounded-lg border border-gray-700">
<div class="step-dot">2</div>
<div>
<h4 class="font-bold text-neonblue text-[11px] uppercase mb-1 tracking-widest">Revocation Check (OCSP)</h4>
<p class="text-[10px] text-textdim leading-relaxed">Perform real-time checks to ensure the signer's certificate has not been compromised or revoked (addressing R9).</p>
</div>
</div>

<div class="flex items-start bg-bgbase p-5 rounded-lg border border-gray-700">
<div class="step-dot">3</div>
<div>
<h4 class="font-bold text-neonblue text-[11px] uppercase mb-1 tracking-widest">Temporal Anchor Check</h4>
<p class="text-[10px] text-textdim leading-relaxed">Confirm that the manifest hash is anchored by an RFC 3161 Trusted Timestamp Authority (TSA) to prevent timeline spoofing.</p>
</div>
</div>

<div class="flex items-start bg-bgbase p-5 rounded-lg border border-gray-700">
<div class="step-dot">4</div>
<div>
<h4 class="font-bold text-neonblue text-[11px] uppercase mb-1 tracking-widest">Ingredient Graph Audit</h4>
<p class="text-[10px] text-textdim leading-relaxed">Scan the additive history for "unsigned gaps" or "redacted parents" that indicate a break in the provenance chain.</p>
</div>
</div>

<div class="flex items-start bg-bgbase p-5 rounded-lg border border-gray-700 md:col-span-2">
<div class="step-dot" style="background:#ec4899">5</div>
<div>
<h4 class="font-bold text-electricpink text-[11px] uppercase mb-1 tracking-widest">Physical Reality Check (Zero-Trust)</h4>
<p class="text-[10px] text-textdim leading-relaxed">Do not blindly trust signatures. Cross-reference shadow vectors and Noise Pattern Analysis (NPA) uniformly against GPS and timestamp data to detect hardware-injected fakes.</p>
</div>
</div>
</div>
</div>
</section>

</main>

<footer class="bg-gray-900 border-t border-gray-800 py-12">
<div class="max-w-7xl mx-auto px-4 text-center">
<div class="text-neonblue font-bold tracking-tighter text-xl mb-4 italic uppercase">ProvenanceCORE // 2026 AUDIT</div>
<p class="text-gray-500 text-[9px] uppercase tracking-widest">Confidential Framework Synthesis // No SVG or Mermaid used // Rendered via Canvas/WebGL</p>
</div>
</footer>

<div id="riskModal" onclick="if(event.target === this) toggleModal()">
<div class="modal-content card-elevation" onclick="event.stopPropagation()">
<div class="flex justify-between items-center p-6 border-b border-gray-800 bg-bgbase">
<h3 class="text-xl font-bold text-neonblue tracking-widest uppercase">Detailed Risk Register (2026)</h3>
<button onclick="toggleModal()" class="text-textdim hover:text-white text-3xl font-light leading-none">&times;</button>
</div>
<div class="overflow-y-auto p-6 bg-cardbg">
<table class="w-full text-left border-collapse min-w-[1000px]">
<thead>
<tr class="bg-bgbase border-b border-gray-800">
<th class="px-4 py-3 text-[10px] font-black uppercase text-neonblue w-16 text-center">ID</th>
<th class="px-4 py-3 text-[10px] font-black uppercase text-neonblue w-32">Category</th>
<th class="px-4 py-3 text-[10px] font-black uppercase text-neonblue">Description</th>
<th class="px-4 py-3 text-[10px] font-black uppercase text-neonblue">Impact</th>
<th class="px-4 py-3 text-[10px] font-black uppercase text-neonblue">Mitigation Strategy</th>
</tr>
</thead>
<tbody id="riskTableBody" class="text-[11px] divide-y divide-gray-800/50">
</tbody>
</table>
</div>
<div class="p-4 border-t border-gray-800 bg-bgbase text-right">
<button onclick="toggleModal()" class="px-6 py-2 bg-gray-700 text-white text-[10px] font-bold uppercase rounded-lg tracking-widest">Close Register</button>
</div>
</div>
</div>

<script>
const RISK_DATA = [
{ id: "R1", cat: "Strategic", desc: "Obsolescence of Legacy Content: Shift to C2PA as trust currency renders unsigned archives less credible.", impact: "Loss of competitive edge; content rejected by platforms.", mit: "Implement retrospective 'Edit' manifests for verified historical assets." },
{ id: "R2", cat: "Strategic", desc: "Fragmented Trust Tiering: Reliance on frozen ITL vs new 2026 global standard.", impact: "Inconsistent verification; 'Low Trust' flags on valid content.", mit: "Migrate to 2026 C2PA Conformance Programme certified CAs." },
{ id: "R3", cat: "Operational", desc: "Temporal Manipulation: Attackers stripping/modifying timestamps.", impact: "Forensic timeline failure; loss of integrity.", mit: "Mandatory integration of RFC 3161 TSA & chaining." },
{ id: "R4", cat: "Operational", desc: "Hardware Injection (Nikon): Malicious AI input into TEE signing pipeline.", impact: "Valid hardware signatures on synthetic content.", mit: "Input validation in TEE; secure sensor pipeline auth." },
{ id: "R5", cat: "Operational", desc: "Metadata Stripping: Social media/CDNs stripping manifests.", impact: "Loss of provenance chain; reliance on weak soft bindings.", mit: "Cloud manifest recovery architecture via perceptual hash." },
{ id: "R6", cat: "Financial", desc: "Asset Devaluation (TDM): AI scrapers ignoring 'notAllowed' flags.", impact: "Loss of licensing revenue; unauthorized training on IP.", mit: "CAWG TDM assertions as technical evidence for litigation." },
{ id: "R7", cat: "Financial", desc: "Compliance Costs: fleet upgrade requirements for Sony/Leica devices.", impact: "CapEx strain; digital divide between news organizations.", mit: "Tiered ingest strategy prioritizing high-risk conflict zones." },
{ id: "R8", cat: "Compliance", desc: "EU AI Act Violations: Failure to disclose AI generation (Art 50).", impact: "Regulatory fines; forced market removals.", mit: "Automated ingest checks triggering AI Assertion manifests." },
{ id: "R9", cat: "Compliance", desc: "Revocation Blindness: Validation tools failing to check OCSP.", impact: "Accepting content signed by compromised/revoked hardware keys.", mit: "Validators configured for mandatory real-time OCSP checks." },
{ id: "R10", cat: "Reputational", desc: "Fake Meeting Attack: AI video used to impersonate leadership.", impact: "Loss of organizational trust; successful social engineering.", mit: "Freshness checks using nonces in attestation tokens." },
{ id: "R11", cat: "External", desc: "Adversarial AI Evolution: Models designed to leave no synthetic signatures.", impact: "Detection efficacy degradation (down to 69%); dark AI growth.", mit: "Hybrid validation: C2PA crypto + physical reality audits." },
{ id: "R12", cat: "ESG", desc: "Information Integrity (Social): Proliferation of propaganda gaps.", impact: "Social instability; inability to distinguish optical reality.", mit: "Prioritize first-mile trust for field journalists; sensor verification." },
{ id: "R13", cat: "ESG", desc: "Inclusion/Bias in AI Tools: AI used creating harmful representations.", impact: "Ethical breaches; public backlash against synthetic diversity.", mit: "Transparent disclosure of prompts/models in C2PA metadata store." },
{ id: "R14", cat: "Project", desc: "Integration Complexity: Failure to reconstruct Ingredient Graph.", impact: "Broken provenance chains; production delays.", mit: "Standardize on C2PA v3 for robust redaction handling." },
{ id: "R15", cat: "Project", desc: "Validation Latency: Forensic checks slowing down news publishing.", impact: "Operational bottlenecks; missed breaking news windows.", mit: "Automated triage: Signatures for low-risk, Forensics for high-risk." }
];

function toggleModal() {
const modal = document.getElementById('riskModal');
modal.classList.toggle('active');
}

function wrapLabel(label) {
if(label.length <= 16) return label;
const words = label.split(' ');
const lines = [];
let currentLine = '';
words.forEach(word => {
if((currentLine + word).length > 16) {
if(currentLine) lines.push(currentLine.trim());
currentLine = word + ' ';
} else {
currentLine += word + ' ';
}
});
if(currentLine) lines.push(currentLine.trim());
return lines;
}

const tooltipConfig = {
plugins: {
tooltip: {
backgroundColor: '#0f172a',
titleColor: '#06b6d4',
bodyColor: '#cbd5e1',
borderColor: '#1e293b',
borderWidth: 1,
callbacks: {
title: function(tooltipItems) {
const item = tooltipItems[0];
let label = item.chart.data.labels[item.dataIndex];
return Array.isArray(label) ? label.join(' ') : label;
}
}
}
}
};

window.onload = function() {
const body = document.getElementById('riskTableBody');
body.innerHTML = RISK_DATA.map(r => `
<tr class="hover:bg-neonblue/5 transition">
<td class="px-4 py-3 font-bold text-neonblue text-center border-r border-gray-800">${r.id}</td>
<td class="px-4 py-3 uppercase tracking-tighter font-bold text-textdim">${r.cat}</td>
<td class="px-4 py-3 font-semibold text-textlight">${r.desc}</td>
<td class="px-4 py-3 text-textdim">${r.impact}</td>
<td class="px-4 py-3 text-neonblue/90 font-medium italic">${r.mit}</td>
</tr>
`).join('');

const donutCtx = document.getElementById('riskDonutChart').getContext('2d');
new Chart(donutCtx, {
type: 'doughnut',
data: {
labels: ["Strategic", "Operational", "Financial", "Compliance", "Reputational", "External", "ESG", "Project"].map(wrapLabel),
datasets: [{
data: [2, 3, 2, 2, 1, 1, 2, 2],
backgroundColor: ['#06b6d4', '#f97316', '#ec4899', '#8b5cf6', '#14b8a6', '#facc15', '#10b981', '#6366f1'],
borderWidth: 0,
hoverOffset: 12
}]
},
options: {
responsive: true,
maintainAspectRatio: false,
color: '#cbd5e1',
plugins: {
legend: { position: 'right', labels: { color: '#cbd5e1', font: { size: 9, weight: 'bold' } } },
...tooltipConfig.plugins
},
cutout: '75%'
}
});

// RAW COORDINATES FROM THE PREVIOUS DESIGN
const rawX = [7, 6.5, 9.5, 10, 8.5, 7.5, 6, 9.5, 9, 8, 9, 8.5, 7, 8, 7.5]; 
const rawY = [8, 7, 9.5, 10, 8, 8.5, 7, 9, 8.5, 7.5, 9, 8, 6.5, 7.5, 7];

// JITTER LOGIC: Offsets overlapping points slightly for UI visibility
const jitterX = [...rawX];
const jitterY = [...rawY];
const seenCoords = {};

for (let i = 0; i < jitterX.length; i++) {
    const key = `${jitterX[i]},${jitterY[i]}`;
    if (seenCoords[key]) {
        // Offset by a small random factor if coordinates are identical
        jitterX[i] += (Math.random() - 0.5) * 0.15;
        jitterY[i] += (Math.random() - 0.5) * 0.15;
    }
    seenCoords[key] = true;
}

const scatterData = {
x: jitterX,
y: jitterY,
mode: 'markers+text',
type: 'scattergl',
text: RISK_DATA.map(r => r.id),
textposition: 'top center',
textfont: { family: 'Inter', color: '#cbd5e1', size: 10, weight: 'bold' },
marker: {
size: 16,
color: RISK_DATA.map(r => {
if(r.cat === 'Operational') return '#f97316';
if(r.cat === 'Compliance') return '#8b5cf6';
if(r.cat === 'Strategic') return '#06b6d4';
return '#ec4899';
}),
line: { color: '#0f172a', width: 2 }
},
hoverinfo: 'text',
hoverlabel: {
    bgcolor: '#1e293b',
    bordercolor: '#334155',
    font: { family: 'Inter', color: '#f8fafc', size: 12 },
    align: 'left'
},
// ENRICHED HOVER TEXT: Includes Mitigation Strategy
hovertext: RISK_DATA.map(r => 
    `<b>FORENSIC INSIGHT: ${r.id}</b><br>` +
    `<i>${r.desc.split(':')[0]}</i><br><br>` +
    `<b>IMPACT:</b> ${r.impact}<br>` +
    `<b>MITIGATION:</b> ${r.mit}`
)
};

const scatterLayout = {
paper_bgcolor: 'rgba(0,0,0,0)',
plot_bgcolor: 'rgba(0,0,0,0)',
font: { family: 'Inter', color: '#64748b' },
xaxis: { 
    title: 'Likelihood of Exploitation (1-10)', 
    gridcolor: '#1e293b', 
    range: [5.5, 10.5], 
    zeroline: false,
    fixedrange: false // Allow zooming
},
yaxis: { 
    title: 'Severity of Impact (1-10)', 
    gridcolor: '#1e293b', 
    range: [5.5, 10.5], 
    zeroline: false,
    fixedrange: false // Allow zooming
},
margin: { l: 40, r: 20, t: 20, b: 40 },
hovermode: 'closest',
dragmode: 'zoom' // Explicitly enable zoom tool as default
};

Plotly.newPlot('plotlyScatter', [scatterData], scatterLayout, { 
    displayModeBar: true, 
    responsive: true,
    modeBarButtonsToRemove: ['lasso2d', 'select2d']
});
};
</script>
</body>
</html>
