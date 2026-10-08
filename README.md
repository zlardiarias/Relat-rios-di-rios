<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Relatório de Atividades Diárias - MPMA</title>
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Font Inter & FontAwesome -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #f1f5f9;
        }
        .bg-mpma-blue {
            background-color: #0c2340;
        }
        .text-mpma-blue {
            color: #0c2340;
        }
        .border-mpma-blue {
            border-color: #0c2340;
        }
        .btn-mpma {
            background-color: #0c2340;
            transition: background-color 0.2s ease;
        }
        .btn-mpma:hover {
            background-color: #143663;
        }
    </style>
</head>
<body class="min-h-screen flex flex-col justify-between py-8 px-4 sm:px-6 lg:px-8">

    <div class="max-w-xl w-full mx-auto bg-white rounded-xl shadow-xl overflow-hidden mb-6 border border-slate-200">
        
        <div class="bg-mpma-blue text-white px-6 py-8 text-center relative">
            <div class="absolute top-4 right-4">
                <button id="btn-admin" onclick="toggleAdminModal(true)" class="text-xs bg-white/10 hover:bg-white/25 text-white px-3 py-1.5 rounded-md transition flex items-center gap-1.5">
                    <i class="fa-solid fa-table-list"></i> Ver Planilha / Relatórios
                </button>
            </div>
            
            <div class="flex justify-center mb-3">
                <div class="bg-white px-4 py-2 rounded-lg shadow-sm inline-block">
                    <!-- LOGO MPMA SVG -->
                    <svg class="h-10 w-auto" viewBox="0 0 200 60" fill="none" xmlns="http://www.w3.org/2000/svg">
                        <rect width="200" height="60" rx="4" fill="white"/>
                        <circle cx="35" cy="30" r="22" fill="#D32F2F"/>
                        <path d="M28 22H42V25H36V40H34V25H28V22Z" fill="white"/>
                        <path d="M25 37H45V40H25V37Z" fill="white"/>
                        <text x="68" y="27" font-family="Inter, sans-serif" font-weight="800" font-size="20" fill="#0C2340">MPMA</text>
                        <text x="68" y="42" font-family="Inter, sans-serif" font-weight="600" font-size="8" fill="#555555">Ministério Público</text>
                        <text x="68" y="50" font-family="Inter, sans-serif" font-weight="500" font-size="7" fill="#777777">do Estado do Maranhão</text>
                    </svg>
                </div>
            </div>
            
            <h1 class="text-lg sm:text-xl font-bold tracking-wide uppercase mt-2">Relatório de Atividades Diárias</h1>
            <p class="text-xs sm:text-sm text-slate-300 font-medium tracking-wide mt-1">SECRETARIA DE PLANEJAMENTO E GESTÃO - SEPLAG</p>
        </div>

        <form id="activity-form" class="p-6 sm:p-8 space-y-5">
            
            <div>
                <label for="servidor" class="block text-xs font-bold text-mpma-blue uppercase tracking-wider mb-1.5">
                    Nome do Servidor / Membro
                </label>
                <input type="text" id="servidor" required
                    class="w-full px-4 py-3 rounded-lg border border-slate-300 focus:ring-2 focus:ring-mpma-blue focus:outline-none text-slate-700 placeholder-slate-400 text-sm"
                    placeholder="Digite seu nome completo">
            </div>

            <div>
                <label for="email" class="block text-xs font-bold text-mpma-blue uppercase tracking-wider mb-1.5">
                    E-mail Institucional
                </label>
                <input type="email" id="email" required
                    class="w-full px-4 py-3 rounded-lg border border-slate-300 focus:ring-2 focus:ring-mpma-blue focus:outline-none text-slate-700 placeholder-slate-400 text-sm"
                    placeholder="nome@mpma.mp.br">
            </div>

            <div>
                <label for="data" class="block text-xs font-bold text-mpma-blue uppercase tracking-wider mb-1.5">
                    Data de Referência
                </label>
                <div class="relative">
                    <input type="date" id="data" required
                        class="w-full px-4 py-3 rounded-lg border border-slate-300 focus:ring-2 focus:ring-mpma-blue focus:outline-none text-slate-700 text-sm bg-white">
                </div>
            </div>

            <div>
                <label for="entregas" class="block text-xs font-bold text-mpma-blue uppercase tracking-wider mb-1.5">
                    Principais Entregas / Atividades Concluídas no Dia
                </label>
                <textarea id="entregas" rows="4" required
                    class="w-full px-4 py-3 rounded-lg border border-slate-300 focus:ring-2 focus:ring-mpma-blue focus:outline-none text-slate-700 placeholder-slate-400 text-sm resize-y"
                    placeholder="Descreva detalhadamente as entregas finalizadas..."></textarea>
            </div>

            <div>
                <label for="demandas" class="block text-xs font-bold text-mpma-blue uppercase tracking-wider mb-1.5">
                    Demandas em Andamento
                </label>
                <textarea id="demandas" rows="4" required
                    class="w-full px-4 py-3 rounded-lg border border-slate-300 focus:ring-2 focus:ring-mpma-blue focus:outline-none text-slate-700 placeholder-slate-400 text-sm resize-y"
                    placeholder="Informe o estado das demandas correntes e prazos..."></textarea>
            </div>

            <div>
                <label for="observacoes" class="block text-xs font-bold text-mpma-blue uppercase tracking-wider mb-1.5">
                    Observações / Intempéries / Pendências
                </label>
                <textarea id="observacoes" rows="4"
                    class="w-full px-4 py-3 rounded-lg border border-slate-300 focus:ring-2 focus:ring-mpma-blue focus:outline-none text-slate-700 placeholder-slate-400 text-sm resize-y"
                    placeholder="Registros adicionais relevantes para o setor..."></textarea>
            </div>

            <div class="pt-2">
                <button type="submit" id="btn-submit"
                    class="w-full btn-mpma text-white font-bold py-3.5 px-4 rounded-lg shadow-md hover:shadow-lg transition flex items-center justify-center gap-2 uppercase tracking-wider text-sm">
                    <span id="submit-text">Enviar Relatório</span>
                    <i id="submit-spinner" class="fa-solid fa-spinner fa-spin hidden"></i>
                </button>
            </div>
        </form>

        <div class="px-6 py-4 bg-slate-50 border-t border-slate-100 text-center text-xs text-slate-500 font-medium">
            Procuradoria Geral de Justiça do Estado do Maranhão - MPMA
        </div>
    </div>

    <div id="admin-modal" class="fixed inset-0 bg-slate-900/60 backdrop-blur-sm z-50 hidden flex items-center justify-center p-4">
        <div class="bg-white w-full max-w-5xl h-[85vh] rounded-2xl shadow-2xl flex flex-col overflow-hidden animate-in fade-in zoom-in-95 duration-200">
            
            <!-- Modal Header -->
            <div class="bg-mpma-blue text-white px-6 py-4 flex items-center justify-between">
                <div class="flex items-center gap-3">
                    <i class="fa-solid fa-file-excel text-emerald-400 text-xl"></i>
                    <div>
                        <h3 class="font-bold text-base">Planilha de Relatórios Enviados</h3>
                        <p class="text-xs text-slate-300">Consulta de dados e exportação para relatórios</p>
                    </div>
                </div>
                <div class="flex items-center gap-3">
                    <button onclick="exportToCSV()" class="bg-emerald-600 hover:bg-emerald-700 text-white text-xs font-semibold px-3 py-2 rounded-lg transition flex items-center gap-1.5 shadow">
                        <i class="fa-solid fa-download"></i> Exportar CSV (Excel)
                    </button>
                    <button onclick="toggleAdminModal(false)" class="text-slate-300 hover:text-white p-2 rounded-lg transition">
                        <i class="fa-solid fa-xmark text-lg"></i>
                    </button>
                </div>
            </div>

            <!-- Modal Body (Table) -->
            <div class="flex-1 overflow-auto p-6 bg-slate-50">
                <div id="loading-data" class="text-center py-12 text-slate-500">
                    <i class="fa-solid fa-spinner fa-spin text-2xl mb-2 text-mpma-blue"></i>
                    <p class="text-sm">Carregando relatórios do banco de dados...</p>
                </div>
                
                <div id="table-container" class="hidden overflow-x-auto rounded-xl border border-slate-200 bg-white shadow-sm">
                    <table class="w-full text-left border-collapse text-xs">
                        <thead>
                            <tr class="bg-slate-100 text-slate-700 uppercase font-bold border-b border-slate-200">
                                <th class="p-3">Data Ref.</th>
                                <th class="p-3">Servidor</th>
                                <th class="p-3">E-mail</th>
                                <th class="p-3">Entregas</th>
                                <th class="p-3">Demandas</th>
                                <th class="p-3">Observações</th>
                                <th class="p-3 text-center">Ações</th>
                            </tr>
                        </thead>
                        <tbody id="reports-table-body" class="divide-y divide-slate-100">
                            <!-- Rows inserted dynamically -->
                        </tbody>
                    </table>
                </div>
                
                <div id="empty-state" class="hidden text-center py-16">
                    <i class="fa-solid fa-folder-open text-4xl text-slate-300 mb-3"></i>
                    <p class="text-slate-600 font-medium text-sm">Nenhum relatório cadastrado até o momento.</p>
                </div>
            </div>

            <!-- Modal Footer -->
            <div class="px-6 py-3 bg-white border-t border-slate-200 flex justify-between items-center text-xs text-slate-500">
                <span id="total-records">Total de registros: 0</span>
                <button onclick="toggleAdminModal(false)" class="px-4 py-2 bg-slate-200 hover:bg-slate-300 text-slate-700 font-medium rounded-lg transition">
                    Fechar
                </button>
            </div>
        </div>
    </div>

    <div id="msg-modal" class="fixed inset-0 bg-slate-900/50 backdrop-blur-sm z-50 hidden flex items-center justify-center p-4">
        <div class="bg-white w-full max-w-sm rounded-xl shadow-xl p-6 text-center animate-in fade-in zoom-in-95 duration-200">
            <div id="msg-icon" class="w-12 h-12 rounded-full bg-emerald-100 text-emerald-600 flex items-center justify-center mx-auto mb-4 text-xl">
                <i class="fa-solid fa-check"></i>
            </div>
            <h3 id="msg-title" class="font-bold text-slate-800 text-lg mb-1">Sucesso!</h3>
            <p id="msg-text" class="text-slate-600 text-sm mb-6">Relatório enviado com sucesso.</p>
            <button onclick="closeMsgModal()" class="w-full py-2.5 bg-mpma-blue text-white rounded-lg font-semibold text-sm hover:bg-blue-900 transition">
                OK
            </button>
        </div>
    </div>

    <script type="module">
        import { initializeApp } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-app.js";
        import { getAuth, signInAnonymously, signInWithCustomToken } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-auth.js";
        import { getFirestore, collection, addDoc, onSnapshot, query, deleteDoc, doc } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-firestore.js";

        const appId = typeof __app_id !== 'undefined' ? __app_id : 'mpma-seplag-relatorios';
        const firebaseConfig = typeof __firebase_config !== 'undefined' ? JSON.parse(__firebase_config) : {
            apiKey: "demo-key",
            authDomain: "demo.firebaseapp.com",
            projectId: "demo-project",
            storageBucket: "demo.appspot.com",
            messagingSenderId: "123456",
            appId: "1:123456:web:123456"
        };

        let app, db, auth;
        let reportsData = [];

        try {
            app = initializeApp(firebaseConfig);
            db = getFirestore(app);
            auth = getAuth(app);

            const initAuth = async () => {
                try {
                    if (typeof __initial_auth_token !== 'undefined' && __initial_auth_token) {
                        await signInWithCustomToken(auth, __initial_auth_token);
                    } else {
                        await signInAnonymously(auth);
                    }
                } catch (err) {
                    console.error("Auth error:", err);
                    await signInAnonymously(auth);
                }
            };
            initAuth().then(() => {
                setupRealtimeListener();
            });
        } catch (e) {
            console.error("Firebase init error:", e);
        }

        // Preencher data atual por padrão
        const todayStr = new Date().toISOString().split('T')[0];
        document.getElementById('data').value = todayStr;

        // Submissão do Formulário
        const form = document.getElementById('activity-form');
        form.addEventListener('submit', async (e) => {
            e.preventDefault();
            
            const submitText = document.getElementById('submit-text');
            const submitSpinner = document.getElementById('submit-spinner');
            const btnSubmit = document.getElementById('btn-submit');
            
            submitText.textContent = "Enviando...";
            submitSpinner.classList.remove('hidden');
            btnSubmit.disabled = true;

            const formData = {
                servidor: document.getElementById('servidor').value.trim(),
                email: document.getElementById('email').value.trim(),
                data: document.getElementById('data').value,
                entregas: document.getElementById('entregas').value.trim(),
                demandas: document.getElementById('demandas').value.trim(),
                observacoes: document.getElementById('observacoes').value.trim(),
                createdAt: new Date().toISOString()
            };

            try {
                if (db && auth.currentUser) {
                    const colRef = collection(db, 'artifacts', appId, 'public', 'data', 'atividades');
                    await addDoc(colRef, formData);
                } else {
                    // Fallback local caso firebase falhe
                    let localReports = JSON.parse(localStorage.getItem('mpma_local_reports') || '[]');
                    localReports.push({ id: 'local_' + Date.now(), ...formData });
                    localStorage.setItem('mpma_local_reports', JSON.stringify(localReports));
                    renderTable(localReports);
                }

                showMsgModal('Sucesso!', 'Relatório de atividades enviado com sucesso para o banco de dados do MPMA.', 'success');
                form.reset();
                document.getElementById('data').value = todayStr;
            } catch (err) {
                console.error("Erro ao salvar:", err);
                showMsgModal('Erro', 'Não foi possível enviar o relatório. Tente novamente.', 'error');
            } finally {
                submitText.textContent = "Enviar Relatório";
                submitSpinner.classList.add('hidden');
                btnSubmit.disabled = false;
            }
        });

        // Configurar listener em tempo real para a planilha
        function setupRealtimeListener() {
            if (!db) return;
            try {
                const colRef = collection(db, 'artifacts', appId, 'public', 'data', 'atividades');
                const q = query(colRef);
                
                onSnapshot(q, (snapshot) => {
                    reportsData = [];
                    snapshot.forEach((docSnap) => {
                        reportsData.push({ id: docSnap.id, ...docSnap.data() });
                    });
                    // Ordenar por data decrescente
                    reportsData.sort((a, b) => new Date(b.data || b.createdAt) - new Date(a.data || a.createdAt));
                    renderTable(reportsData);
                }, (error) => {
                    console.error("Firestore snapshot error:", error);
                    loadLocalFallback();
                });
            } catch (e) {
                console.error("Listener error:", e);
                loadLocalFallback();
            }
        }

        function loadLocalFallback() {
            const local = JSON.parse(localStorage.getItem('mpma_local_reports') || '[]');
            reportsData = local;
            renderTable(reportsData);
        }

        window.renderTable = function(data) {
            const loading = document.getElementById('loading-data');
            const tableContainer = document.getElementById('table-container');
            const emptyState = document.getElementById('empty-state');
            const tbody = document.getElementById('reports-table-body');
            const totalRecs = document.getElementById('total-records');

            loading.classList.add('hidden');
            totalRecs.textContent = `Total de registros: ${data.length}`;

            if (data.length === 0) {
                tableContainer.classList.add('hidden');
                emptyState.classList.remove('hidden');
                return;
            }

            emptyState.classList.add('hidden');
            tableContainer.classList.remove('hidden');
            
            tbody.innerHTML = '';
            data.forEach(item => {
                const tr = document.createElement('tr');
                tr.className = "hover:bg-slate-50 transition border-b border-slate-100";
                
                // Formatar data pt-BR
                let formattedDate = item.data;
                if (item.data && item.data.includes('-')) {
                    const parts = item.data.split('-');
                    if(parts.length === 3) formattedDate = `${parts[2]}/${parts[1]}/${parts[0]}`;
                }

                tr.innerHTML = `
                    <td class="p-3 font-medium text-slate-800 whitespace-nowrap">${formattedDate || '-'}</td>
                    <td class="p-3 font-semibold text-mpma-blue">${escapeHtml(item.servidor || '')}</td>
                    <td class="p-3 text-slate-600">${escapeHtml(item.email || '')}</td>
                    <td class="p-3 text-slate-700 max-w-xs truncate" title="${escapeHtml(item.entregas || '')}">${escapeHtml(item.entregas || '')}</td>
                    <td class="p-3 text-slate-700 max-w-xs truncate" title="${escapeHtml(item.demandas || '')}">${escapeHtml(item.demandas || '')}</td>
                    <td class="p-3 text-slate-700 max-w-xs truncate" title="${escapeHtml(item.observacoes || '')}">${escapeHtml(item.observacoes || '')}</td>
                    <td class="p-3 text-center whitespace-nowrap">
                        <button onclick="viewReportDetail('${item.id}')" class="text-mpma-blue hover:text-blue-700 p-1.5 rounded transition" title="Visualizar Detalhes">
                            <i class="fa-solid fa-eye"></i>
                        </button>
                    </td>
                `;
                tbody.appendChild(tr);
            });
        };

        window.toggleAdminModal = function(show) {
            const modal = document.getElementById('admin-modal');
            if (show) {
                modal.classList.remove('hidden');
            } else {
                modal.classList.add('hidden');
            }
        };

        window.showMsgModal = function(title, text, type) {
            const modal = document.getElementById('msg-modal');
            const icon = document.getElementById('msg-icon');
            const titleEl = document.getElementById('msg-title');
            const textEl = document.getElementById('msg-text');

            titleEl.textContent = title;
            textEl.textContent = text;

            if (type === 'success') {
                icon.className = "w-12 h-12 rounded-full bg-emerald-100 text-emerald-600 flex items-center justify-center mx-auto mb-4 text-xl";
                icon.innerHTML = '<i class="fa-solid fa-check"></i>';
            } else {
                icon.className = "w-12 h-12 rounded-full bg-rose-100 text-rose-600 flex items-center justify-center mx-auto mb-4 text-xl";
                icon.innerHTML = '<i class="fa-solid fa-triangle-exclamation"></i>';
            }

            modal.classList.remove('hidden');
        };

        window.closeMsgModal = function() {
            document.getElementById('msg-modal').classList.add('hidden');
        };

        window.exportToCSV = function() {
            if (!reportsData || reportsData.length === 0) {
                showMsgModal('Aviso', 'Não há dados para exportar.', 'error');
                return;
            }

            let csvContent = "\uFEFFData de Referencia;Servidor / Membro;E-mail Institucional;Entregas Concluidas;Demandas em Andamento;Observacoes\n";
            
            reportsData.forEach(row => {
                const clean = (val) => `"${(val || '').replace(/"/g, '""').replace(/\n/g, ' ')}"`;
                csvContent += [
                    clean(row.data),
                    clean(row.servidor),
                    clean(row.email),
                    clean(row.entregas),
                    clean(row.demandas),
                    clean(row.observacoes)
                ].join(";") + "\n";
            });

            const blob = new Blob([csvContent], { type: 'text/csv;charset=utf-8;' });
            const url = URL.createObjectURL(blob);
            const a = document.createElement('a');
            a.setAttribute('href', url);
            a.setAttribute('download', `relatorio_atividades_mpma_${new Date().toISOString().split('T')[0]}.csv`);
            document.body.appendChild(a);
            a.click();
            document.body.removeChild(a);
        };

        window.viewReportDetail = function(id) {
            const item = reportsData.find(r => r.id === id);
            if (!item) return;

            const detailHtml = `
                <div class="space-y-3 text-left text-xs">
                    <div><strong class="text-mpma-blue">Data:</strong> ${item.data}</div>
                    <div><strong class="text-mpma-blue">Servidor:</strong> ${escapeHtml(item.servidor)}</div>
                    <div><strong class="text-mpma-blue">E-mail:</strong> ${escapeHtml(item.email)}</div>
                    <div><strong class="text-mpma-blue">Entregas:</strong><p class="mt-1 p-2 bg-slate-50 rounded border border-slate-200 whitespace-pre-wrap">${escapeHtml(item.entregas)}</p></div>
                    <div><strong class="text-mpma-blue">Demandas:</strong><p class="mt-1 p-2 bg-slate-50 rounded border border-slate-200 whitespace-pre-wrap">${escapeHtml(item.demandas)}</p></div>
                    <div><strong class="text-mpma-blue">Observações:</strong><p class="mt-1 p-2 bg-slate-50 rounded border border-slate-200 whitespace-pre-wrap">${escapeHtml(item.observacoes || 'Nenhuma')}</p></div>
                </div>
            `;
            
            // Reutilizar modal de mensagem para exibir detalhes ampliado
            const modal = document.getElementById('msg-modal');
            const icon = document.getElementById('msg-icon');
            const titleEl = document.getElementById('msg-title');
            const textEl = document.getElementById('msg-text');

            icon.className = "w-10 h-10 rounded-full bg-blue-100 text-mpma-blue flex items-center justify-center mx-auto mb-2 text-lg";
            icon.innerHTML = '<i class="fa-solid fa-file-lines"></i>';
            titleEl.textContent = "Detalhes do Relatório";
            textEl.innerHTML = detailHtml;
            modal.classList.remove('hidden');
        };

        function escapeHtml(text) {
            if (!text) return '';
            return text
                .replace(/&/g, "&amp;")
                .replace(/</g, "&lt;")
                .replace(/>/g, "&gt;")
                .replace(/"/g, "&quot;")
                .replace(0, "'");
        }
    </script>
</body>
</html>
