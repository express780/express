

<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>FlotteExpress - Suivi Chauffeur</title>
    <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-slate-50 text-slate-800 font-sans pb-12">

    <header class="bg-slate-900 text-white p-4 shadow-md sticky top-0 z-50">
        <div class="max-w-md mx-auto flex justify-between items-center">
            <h1 class="font-bold text-lg">🚛 FlotteExpress</h1>
            <span class="text-xs bg-blue-600 px-2 py-1 rounded-full font-medium">VL / PL : AB-123-CD</span>
        </div>
    </header>

    <main class="max-w-md mx-auto p-4 space-y-4">

        <div class="bg-white p-4 rounded-2xl shadow-sm border border-slate-100 flex items-center justify-between">
            <div>
                <p class="text-xs text-slate-400 font-medium">Véhicule du jour</p>
                <p class="text-base font-bold text-slate-700">Renault Master (VL)</p>
            </div>
            <button onclick="alert('Changement de véhicule')" class="text-xs text-blue-600 bg-blue-50 px-3 py-1.5 rounded-lg font-semibold hover:bg-blue-100">Modifier</button>
        </div>

        <div class="grid grid-cols-1 gap-3">
            
            <div onclick="openSection('etat-lieux')" class="bg-white p-4 rounded-2xl shadow-sm border border-slate-100 flex items-center space-x-4 cursor-pointer hover:border-blue-500 transition">
                <div class="bg-blue-50 text-blue-600 p-3 rounded-xl text-xl">📷</div>
                <div class="flex-1">
                    <h2 class="font-bold text-slate-800">État des lieux</h2>
                    <p class="text-xs text-slate-500">Photos avant / après tournée</p>
                </div>
                <span class="text-slate-300">➔</span>
            </div>

            <div onclick="openSection('carburant')" class="bg-white p-4 rounded-2xl shadow-sm border border-slate-100 flex items-center space-x-4 cursor-pointer hover:border-blue-500 transition">
                <div class="bg-amber-50 text-amber-600 p-3 rounded-xl text-xl">⛽</div>
                <div class="flex-1">
                    <h2 class="font-bold text-slate-800">Plein de Carburant</h2>
                    <p class="text-xs text-slate-500">Saisie km & photo ticket</p>
                </div>
                <span class="text-slate-300">➔</span>
            </div>

            <div onclick="openSection('panne')" class="bg-white p-4 rounded-2xl shadow-sm border border-slate-100 flex items-center space-x-4 cursor-pointer hover:border-red-500 transition">
                <div class="bg-red-50 text-red-600 p-3 rounded-xl text-xl">⚠️</div>
                <div class="flex-1">
                    <h2 class="font-bold text-slate-800">Signaler un problème</h2>
                    <p class="text-xs text-slate-500">Anomalie ou voyant moteur</p>
                </div>
                <span class="text-slate-300">➔</span>
            </div>

        </div>

        <div id="dynamic-section" class="bg-white p-5 rounded-2xl shadow-sm border border-slate-100 mt-6 hidden">
            <div class="flex justify-between items-center mb-4">
                <h3 id="section-title" class="font-bold text-slate-800 text-base">Titre</h3>
                <button onclick="closeSection()" class="text-slate-400 text-sm font-bold">✕ Fermer</button>
            </div>
            <div id="section-content">
                </div>
        </div>

    </main>

    <script>
        function openSection(type) {
            const container = document.getElementById('dynamic-section');
            const title = document.getElementById('section-title');
            const content = document.getElementById('section-content');
            
            container.classList.remove('hidden');

            if (type === 'etat-lieux') {
                title.innerText = "📷 État des lieux du véhicule";
                content.innerHTML = `
                    <div class="space-y-3">
                        <p class="text-xs text-slate-500">Prenez en photo les 4 côtés du véhicule avant le départ.</p>
                        <div class="grid grid-cols-2 gap-2">
                            <button class="border-2 border-dashed border-slate-200 p-4 rounded-xl text-xs text-slate-500 hover:border-blue-500">📸 Avant</button>
                            <button class="border-2 border-dashed border-slate-200 p-4 rounded-xl text-xs text-slate-500 hover:border-blue-500">📸 Arrière</button>
                            <button class="border-2 border-dashed border-slate-200 p-4 rounded-xl text-xs text-slate-500 hover:border-blue-500">📸 Côté Gauche</button>
                            <button class="border-2 border-dashed border-slate-200 p-4 rounded-xl text-xs text-slate-500 hover:border-blue-500">📸 Côté Droit</button>
                        </div>
                        <button onclick="alert('État des lieux enregistré !')" class="w-full bg-slate-900 text-white font-medium py-3 rounded-xl mt-3">Valider l'inspection</button>
                    </div>
                `;
            } else if (type === 'carburant') {
                title.innerText = "⛽ Enregistrer un Plein";
                content.innerHTML = `
                    <div class="space-y-3">
                        <div>
                            <label class="text-xs font-semibold text-slate-600">Kilométrage actuel</label>
                            <input type="number" placeholder="Ex: 145230" class="w-full mt-1 p-3 bg-slate-50 border border-slate-200 rounded-xl text-sm">
                        </div>
                        <div>
                            <label class="text-xs font-semibold text-slate-600">Montant total (€)</label>
                            <input type="number" placeholder="Ex: 85.50" class="w-full mt-1 p-3 bg-slate-50 border border-slate-200 rounded-xl text-sm">
                        </div>
                        <div>
                            <label class="text-xs font-semibold text-slate-600">Photo du ticket</label>
                            <input type="file" class="w-full mt-1 text-xs text-slate-500 file:mr-4 file:py-2 file:px-4 file:rounded-xl file:border-0 file:text-xs file:font-semibold file:bg-blue-50 file:text-blue-700 hover:file:bg-blue-100">
                        </div>
                        <button onclick="alert('Plein enregistré avec succès !')" class="w-full bg-slate-900 text-white font-medium py-3 rounded-xl mt-3">Envoyer le justificatif</button>
                    </div>
                `;
            } else if (type === 'panne') {
                title.innerText = "⚠️ Signaler un dysfonctionnement";
                content.innerHTML = `
                    <div class="space-y-3">
                        <div class="grid grid-cols-2 gap-2 text-xs">
                            <label class="flex items-center space-x-2 p-3 bg-slate-50 rounded-xl border border-slate-200"><input type="checkbox"> <span>Pneumatiques</span></label>
                            <label class="flex items-center space-x-2 p-3 bg-slate-50 rounded-xl border border-slate-200"><input type="checkbox"> <span>Freinage</span></label>
                            <label class="flex items-center space-x-2 p-3 bg-slate-50 rounded-xl border border-slate-200"><input type="checkbox"> <span>Éclairage</span></label>
                            <label class="flex items-center space-x-2 p-3 bg-slate-50 rounded-xl border border-slate-200"><input type="checkbox"> <span>Voyant Moteur</span></label>
                        </div>
                        <div>
                            <label class="text-xs font-semibold text-slate-600">Précisions</label>
                            <textarea placeholder="Décrivez le problème..." class="w-full mt-1 p-3 bg-slate-50 border border-slate-200 rounded-xl text-sm h-20"></textarea>
                        </div>
                        <button onclick="alert('Alerte envoyée au gestionnaire !')" class="w-full bg-red-600 text-white font-medium py-3 rounded-xl mt-3">Envoyer l'alerte</button>
                    </div>
                `;
            }
        }

        function closeSection() {
            document.getElementById('dynamic-section').classList.add('hidden');
        }
    </script>
</body>
</html>
