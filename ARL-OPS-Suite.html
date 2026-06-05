<!DOCTYPE html>
<html lang="de">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Austrian Racing League - Ops CRM</title>
    <script src="https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4"></script>
    <script defer src="https://cdn.jsdelivr.net/npm/alpinejs@3.x.x/dist/cdn.min.js"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    <style>
        body { font-family: 'Inter', sans-serif; }
        .glass { background: rgba(15, 23, 42, 0.6); backdrop-filter: blur(12px); }
    </style>
</head>
<body class="bg-[#0b0f19] text-slate-200 antialiased overflow-hidden" x-data="ligaOpsApp()">

    <div x-show="!user" class="fixed inset-0 bg-[#070a13] flex items-center justify-center z-50 p-4 bg-[radial-gradient(ellipse_at_top,_var(--tw-gradient-stops))] from-blue-900/40 via-[#070a13] to-[#070a13]">
        <div class="bg-[#111827] p-8 rounded-2xl max-w-sm w-full shadow-2xl border border-slate-800 text-center">
            <div class="flex flex-col items-center mb-6">
                <img src="ARL Logo.jpg" alt="ARL Logo" class="w-24 h-24 object-contain rounded-xl mb-3 border border-slate-700 p-1 bg-[#0b0f19]">
                <span class="text-white font-extrabold text-xl tracking-wider uppercase">ARL Quality Suite</span>
                <p class="text-slate-400 text-xs mt-1">Austrian Racing League Team-Zentrale</p>
            </div>
            
            <form @submit.prevent="handleAuthSubmit()">
                <div class="space-y-4 text-left">
                    <div x-show="isRegistering">
                        <label class="block text-[10px] font-bold uppercase text-slate-400 mb-1 tracking-wider">Dein Name / Fahrername</label>
                        <input type="text" x-model="authName" :required="isRegistering" class="w-full bg-[#1f2937] border border-slate-700 text-white rounded-xl px-4 py-2.5 text-sm focus:outline-none focus:border-blue-500 transition-colors">
                    </div>
                    <div>
                        <label class="block text-[10px] font-bold uppercase text-slate-400 mb-1 tracking-wider">E-Mail-Adresse</label>
                        <input type="email" x-model="authEmail" required class="w-full bg-[#1f2937] border border-slate-700 text-white rounded-xl px-4 py-2.5 text-sm focus:outline-none focus:border-blue-500 transition-colors">
                    </div>
                    <div>
                        <label class="block text-[10px] font-bold uppercase text-slate-400 mb-1 tracking-wider">Passwort</label>
                        <input type="password" x-model="authPassword" required class="w-full bg-[#1f2937] border border-slate-700 text-white rounded-xl px-4 py-2.5 text-sm focus:outline-none focus:border-blue-500 transition-colors">
                    </div>
                    <div x-show="authError" class="text-xs text-rose-400 font-medium bg-rose-950/50 p-2.5 rounded-lg border border-rose-900/50" x-text="authError"></div>
                    <button type="submit" class="w-full bg-blue-600 hover:bg-blue-700 text-white font-bold text-sm py-2.5 rounded-xl transition-all shadow-lg shadow-blue-600/20 cursor-pointer">
                        <span x-text="isRegistering ? 'Registrierung anfragen' : 'Sicher Anmelden'"></span>
                    </button>
                </div>
            </form>
            <div class="mt-6 text-center border-t pt-4 border-slate-800">
                <button @click="isRegistering = !isRegistering; authError = ''" class="text-xs text-slate-400 hover:text-blue-400 transition-colors cursor-pointer">
                    <span x-text="isRegistering ? 'Bereits im Team? Hier einloggen' : 'Neu im Team? Account beantragen'"></span>
                </button>
            </div>
        </div>
    </div>

    <div x-show="user && !isApproved" class="fixed inset-0 bg-[#070a13] flex items-center justify-center z-40 p-4" style="display: none;">
        <div class="bg-[#111827] p-8 rounded-2xl max-w-md w-full shadow-2xl border border-slate-800 text-center space-y-4">
            <div class="w-16 h-16 bg-amber-500/10 text-amber-500 border border-amber-500/20 rounded-full flex items-center justify-center text-2xl mx-auto animate-pulse">⏳</div>
            <h2 class="text-white font-bold text-xl tracking-tight">Account wartet auf Freischaltung</h2>
            <p class="text-slate-400 text-sm leading-relaxed">Dein Account (<span class="text-blue-400 font-mono" x-text="user ? user.email : ''"></span>) wurde erfolgreich angelegt. Die Projektleitung muss deine Registrierung manuell bestätigen.</p>
            <button @click="logoutUser()" class="text-xs text-rose-400 hover:underline cursor-pointer pt-2 block mx-auto">Abmelden & Zurück</button>
        </div>
    </div>

    <div x-show="user && isApproved" class="flex h-screen w-screen" style="display: none;">
        
        <aside class="w-64 bg-[#111827] text-slate-400 flex flex-col justify-between shrink-0 z-20 border-r border-slate-800/80 shadow-xl">
            <div>
                <div class="p-5 flex items-center gap-3 border-b border-slate-800/60">
                    <img src="ARL Logo.jpg" alt="ARL Logo Mini" class="w-8 h-8 object-contain rounded bg-slate-900 p-0.5">
                    <span class="text-white font-bold text-base tracking-wider uppercase">ARL Ops Suite</span>
                </div>

                <nav class="p-3 space-y-1">
                    <button @click="currentView = 'dashboard'" :class="currentView === 'dashboard' ? 'bg-blue-600 text-white font-semibold' : 'hover:bg-slate-800/50 hover:text-slate-200'" class="w-full flex items-center gap-3 px-4 py-2.5 rounded-xl text-sm font-medium transition-all cursor-pointer text-left">Dashboard</button>
                    <button @click="currentView = 'tickets'" :class="(currentView === 'tickets' || currentView === 'ticket-detail' || currentView === 'ticket-create') ? 'bg-blue-600 text-white font-semibold' : 'hover:bg-slate-800/50 hover:text-slate-200'" class="w-full flex items-center gap-3 px-4 py-2.5 rounded-xl text-sm font-medium transition-all cursor-pointer text-left">Tickets & Anträge</button>
                    <button @click="currentView = 'team'" :class="currentView === 'team' ? 'bg-blue-600 text-white font-semibold' : 'hover:bg-slate-800/50 hover:text-slate-200'" class="w-full flex items-center gap-3 px-4 py-2.5 rounded-xl text-sm font-medium transition-all cursor-pointer text-left">👥 Team-Übersicht</button>
                    <button @click="currentView = 'archive'" :class="currentView === 'archive' ? 'bg-slate-700 text-white font-semibold' : 'hover:bg-slate-800/50 hover:text-slate-200'" class="w-full flex items-center gap-3 px-4 py-2.5 rounded-xl text-sm font-medium transition-all cursor-pointer text-left">Archiv & Papierkorb</button>
                    <button @click="currentView = 'qa'" :class="currentView === 'qa' ? 'bg-blue-600 text-white font-semibold' : 'hover:bg-slate-800/50 hover:text-slate-200'" class="w-full flex items-center gap-3 px-4 py-2.5 rounded-xl text-sm font-medium transition-all cursor-pointer text-left">Steward Analyst</button>
                    
                    <template x-if="isAdmin || isSupervisor">
                        <button @click="currentView = 'admin'" :class="currentView === 'admin' ? 'bg-amber-600 text-white font-semibold' : 'hover:bg-slate-800/50 hover:text-amber-400'" class="w-full flex items-center gap-3 px-4 py-2.5 rounded-xl text-sm font-medium transition-all cursor-pointer text-left border border-dashed border-amber-500/20 mt-4">👑 Admin Panel</button>
                    </template>
                </nav>
            </div>
            <div class="p-4 border-t border-slate-800/60 flex justify-between items-center text-xs text-slate-600">
                <span>v2.1.0</span>
                <span class="bg-emerald-500/10 text-emerald-400 border border-emerald-500/20 px-2 py-0.5 rounded font-mono">Live Sync</span>
            </div>
        </aside>

        <div class="flex-1 flex flex-col overflow-hidden bg-[#070a13]">
            <header class="h-16 bg-[#111827] border-b border-slate-800/80 flex items-center justify-between px-6 shrink-0 z-10">
                <div>
                    <span class="bg-blue-500/10 text-blue-400 text-[10px] font-bold uppercase tracking-wider px-2 py-0.5 rounded border border-blue-500/20" x-text="currentUserRole"></span>
                </div>
                <div class="flex items-center gap-4">
                    <button @click="logoutUser()" class="text-slate-400 hover:text-rose-400 text-xs font-semibold px-2 py-1 transition-colors cursor-pointer">Abmelden</button>
                    <div class="flex items-center gap-3 border-l pl-4 border-slate-800">
                        <div class="w-8 h-8 bg-blue-600 rounded-full flex items-center justify-center text-white text-xs font-bold shadow-inner" x-text="userInitials"></div>
                        <div class="text-left hidden sm:block">
                            <p class="text-xs font-bold text-white leading-tight" x-text="myProfileName"></p>
                            <p class="text-[11px] text-slate-500" x-text="user ? user.email : ''"></p>
                        </div>
                    </div>
                </div>
            </header>

            <main class="flex-1 overflow-y-auto p-6 bg-[#070a13]">
                
                <div x-show="currentView === 'dashboard'" class="max-w-5xl mx-auto space-y-6">
                    <div class="bg-gradient-to-r from-blue-700 to-indigo-900 rounded-2xl p-6 text-white shadow-xl border border-blue-600/30">
                        <h1 class="text-2xl font-black tracking-tight" x-text="'Servus, ' + myProfileName + '!'"></h1>
                        <p class="text-blue-200 text-xs mt-1">Hier siehst du Tickets, die für deine Abteilungen freigegeben oder erwähnt wurden.</p>
                    </div>

                    <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
                        <div class="md:col-span-2 bg-[#111827] border border-slate-800 rounded-xl p-5 shadow-lg">
                            <div class="flex justify-between items-center mb-3 pb-2 border-b border-slate-800">
                                <h3 class="font-bold text-xs uppercase tracking-wider text-slate-400">🔔 Erwähnungen & Aufgaben deiner Abteilungen</h3>
                            </div>
                            <div class="space-y-2">
                                <template x-for="ticket in tickets.filter(t => t.status !== 'Abgeschlossen' && !t.isDeleted && myDepartments.includes(t.category))">
                                    <div @click="openTicket(ticket)" class="p-3 bg-blue-950/20 border border-blue-800/40 rounded-xl flex justify-between items-center cursor-pointer hover:border-blue-500 transition-colors">
                                        <div>
                                            <p class="text-xs font-bold text-white tracking-tight" x-text="ticket.title"></p>
                                            <p class="text-[10px] text-blue-300 mt-0.5" x-text="'Erwähnte Abteilung: ' + ticket.category + ' | Von: ' + ticket.createdBy"></p>
                                        </div>
                                        <span class="bg-blue-500/20 text-blue-400 text-[10px] font-mono px-2 py-0.5 rounded border border-blue-500/30">Zuständig</span>
                                    </div>
                                </template>
                                <div x-show="tickets.filter(t => t.status !== 'Abgeschlossen' && !t.isDeleted && myDepartments.includes(t.category)).length === 0" class="text-xs text-slate-500 py-6 text-center">Keine neuen Erwähnungen für deine Abteilungen vorhanden.</div>
                            </div>
                        </div>
                        <div class="bg-[#111827] border border-slate-800 rounded-xl p-5 shadow-lg flex flex-col justify-between">
                            <div>
                                <h3 class="font-bold text-sm text-white mb-2 pb-2 border-b border-slate-800 tracking-wide uppercase text-xs text-slate-400">Deine Abteilungen</h3>
                                <div class="flex flex-wrap gap-1.5 mt-2">
                                    <template x-for="d in myDepartments">
                                        <span class="bg-amber-500/10 text-amber-400 border border-amber-500/20 text-[10px] font-semibold px-2 py-0.5 rounded" x-text="d"></span>
                                    </template>
                                </div>
                            </div>
                            <button @click="currentView = 'tickets'" class="mt-4 w-full bg-blue-600 hover:bg-blue-700 text-white font-bold text-xs py-2.5 rounded-xl shadow-md cursor-pointer">Alle Tickets ansehen</button>
                        </div>
                    </div>
                </div>

                <div x-show="currentView === 'tickets'" class="max-w-5xl mx-auto space-y-4" style="display: none;">
                    <div class="flex justify-between items-center">
                        <h2 class="text-xl font-bold text-white tracking-tight">Gesamte Ticket-Datenbank</h2>
                        <button @click="currentView = 'ticket-create'" class="bg-blue-600 hover:bg-blue-700 text-white text-xs font-bold px-4 py-2 rounded-xl shadow-md cursor-pointer">+ Neues Ticket erstellen</button>
                    </div>

                    <div class="bg-[#111827] border border-slate-800 rounded-xl shadow-lg divide-y divide-slate-800/80 overflow-hidden">
                        <template x-for="ticket in tickets.filter(t => t.status !== 'Abgeschlossen' && !t.isDeleted)">
                            <div @click="openTicket(ticket)" class="p-4 flex justify-between items-center hover:bg-slate-800/30 transition-colors cursor-pointer">
                                <div>
                                    <h4 class="text-xs font-bold text-white tracking-tight" x-text="ticket.title"></h4>
                                    <p class="text-[11px] text-slate-500 mt-0.5" x-text="'Abteilung: ' + ticket.category + ' — Eingereicht von: ' + ticket.createdBy"></p>
                                </div>
                                <div class="flex items-center gap-2.5 shrink-0">
                                    <span class="bg-[#1f2937] border border-slate-700 text-slate-300 text-[10px] font-bold px-2 py-0.5 rounded-md" x-text="ticket.status || 'Offen'"></span>
                                    <span class="bg-rose-500/10 text-rose-400 border border-rose-500/20 text-[9px] font-bold px-1.5 py-0.5 rounded" x-show="ticket.isEscalated">L2</span>
                                </div>
                            </div>
                        </template>
                        <div x-show="tickets.filter(t => t.status !== 'Abgeschlossen' && !t.isDeleted).length === 0" class="p-12 text-center text-xs text-slate-500">Keine aktiven Vorfälle verzeichnet.</div>
                    </div>
                </div>

                <div x-show="currentView === 'team'" class="max-w-5xl mx-auto space-y-4" style="display: none;">
                    <h2 class="text-xl font-bold text-white tracking-tight">👥 Offizielle ARL Team-Übersicht</h2>
                    <p class="text-xs text-slate-400">Hier sind alle verifizierten Mitarbeiter und deren aktuelle Zuständigkeitsbereiche aufgelistet.</p>
                    
                    <div class="bg-[#111827] border border-slate-800 rounded-xl shadow-lg overflow-hidden">
                        <table class="w-full text-left text-xs">
                            <thead>
                                <tr class="border-b border-slate-800 text-slate-500 font-bold bg-[#111827]">
                                    <th class="p-4">Name / Fahrername</th>
                                    <th class="p-4">E-Mail-Adresse</th>
                                    <th class="p-4 text-right">Zugehörige Abteilungen</th>
                                </tr>
                            </thead>
                            <tbody class="divide-y divide-slate-800">
                                <template x-for="m in cloudUsers.filter(u => u.status === 'Approved')">
                                    <tr class="hover:bg-slate-800/20 transition-colors">
                                        <td class="p-4 font-bold text-white flex items-center gap-2">
                                            <div class="w-6 h-6 bg-blue-600/20 text-blue-400 rounded flex items-center justify-center text-[10px] font-black" x-text="m.name ? m.name.substring(0,2).toUpperCase() : '??'"></div>
                                            <span x-text="m.name || 'Unbekannt'"></span>
                                        </td>
                                        <td class="p-4 text-slate-400 font-mono" x-text="m.email"></td>
                                        <td class="p-4 text-right">
                                            <div class="flex justify-end flex-wrap gap-1">
                                                <template x-for="d in (m.departments || [])">
                                                    <span class="bg-blue-500/10 text-blue-400 border border-blue-500/20 text-[9px] font-semibold px-2 py-0.5 rounded" x-text="d"></span>
                                                </template>
                                                <span x-show="!m.departments || !m.departments.length" class="text-slate-600 text-[11px]">Keine Zuweisung</span>
                                            </div>
                                        </td>
                                    </tr>
                                </template>
                            </tbody>
                        </table>
                    </div>
                </div>

                <div x-show="currentView === 'archive'" class="max-w-5xl mx-auto space-y-6" style="display: none;">
                    <div class="flex justify-between items-center"><h2 class="text-xl font-bold text-white tracking-tight">Archiv & Papierkorb</h2></div>
                    <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                        <div class="bg-[#111827] border border-slate-800 rounded-xl p-5 shadow-lg">
                            <h3 class="font-bold text-xs uppercase tracking-wider text-emerald-400 mb-3 pb-2 border-b border-slate-800">✔ Abgeschlossene Fälle</h3>
                            <div class="space-y-2 max-h-[500px] overflow-y-auto">
                                <template x-for="ticket in tickets.filter(t => t.status === 'Abgeschlossen' && !t.isDeleted)">
                                    <div @click="openTicket(ticket)" class="p-3 bg-emerald-950/20 border border-emerald-900/40 rounded-xl flex justify-between items-center cursor-pointer hover:border-emerald-500 transition-colors">
                                        <div class="text-left">
                                            <p class="text-xs font-bold text-slate-200" x-text="ticket.title"></p>
                                            <p class="text-[10px] text-slate-500 mt-0.5" x-text="'Erledigt für: ' + ticket.createdBy"></p>
                                        </div>
                                        <span class="bg-emerald-500/20 text-emerald-400 text-[9px] font-bold px-2 py-0.5 rounded">Archiv</span>
                                    </div>
                                </template>
                                <div x-show="tickets.filter(t => t.status === 'Abgeschlossen' && !t.isDeleted).length === 0" class="text-xs text-slate-600 text-center py-6">Keine archivierten Daten vorhanden.</div>
                            </div>
                        </div>

                        <div class="bg-[#111827] border border-slate-800 rounded-xl p-5 shadow-lg">
                            <h3 class="font-bold text-xs uppercase tracking-wider text-rose-400 mb-3 pb-2 border-b border-slate-800">🗑 Gelöschte Tickets</h3>
                            <div class="space-y-2 max-h-[500px] overflow-y-auto">
                                <template x-for="ticket in tickets.filter(t => t.isDeleted)">
                                    <div @click="openTicket(ticket)" class="p-3 bg-rose-950/10 border border-rose-900/30 rounded-xl flex justify-between items-center cursor-pointer hover:border-rose-500 transition-colors">
                                        <div class="text-left">
                                            <p class="text-xs font-bold text-slate-400 line-through" x-text="ticket.title"></p>
                                            <p class="text-[10px] text-slate-600 mt-0.5" x-text="'Gelöscht von: ' + (ticket.deletedBy || 'Admin')"></p>
                                        </div>
                                        <span class="bg-rose-500/20 text-rose-400 text-[9px] font-bold px-2 py-0.5 rounded">Papierkorb</span>
                                    </div>
                                </template>
                                <div x-show="tickets.filter(t => t.isDeleted).length === 0" class="text-xs text-slate-600 text-center py-6">Der Papierkorb ist leer.</div>
                            </div>
                        </div>
                    </div>
                </div>

                <div x-show="currentView === 'ticket-create'" class="max-w-2xl mx-auto space-y-4" style="display: none;">
                    <div class="flex items-center justify-between">
                        <h2 class="text-xl font-bold text-white tracking-tight">Vorfalls-Akte anlegen</h2>
                        <button @click="currentView = 'tickets'" class="text-xs font-medium text-slate-500 hover:text-slate-300">Abbrechen</button>
                    </div>
                    <div class="bg-[#111827] border border-slate-800 rounded-2xl p-6 shadow-lg">
                        <form @submit.prevent="submitNewTicket()">
                            <div class="space-y-4">
                                <div>
                                    <label class="block text-xs font-bold uppercase text-slate-400 mb-1">Ticket-Titel / Fallnummer</label>
                                    <input type="text" x-model="newTicketData.title" required placeholder="z.B. Vorfall #04 - Kurve 3 [Müller vs. Schmid]" class="w-full bg-[#1f2937] border border-slate-700 rounded-xl px-4 py-2.5 text-sm focus:outline-none focus:border-blue-500 text-white">
                                </div>
                                <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
                                    <div>
                                        <label class="block text-xs font-bold uppercase text-slate-400 mb-1">Zuständige Abteilung</label>
                                        <select x-model="newTicketData.category" required class="w-full bg-[#1f2937] border border-slate-700 rounded-xl px-4 py-2.5 text-sm focus:outline-none focus:border-blue-500 text-white">
                                            <option value="">-- Abteilung wählen --</option>
                                            <option value="Finanzwesen">Finanzwesen</option>
                                            <option value="Techsupport">Techsupport</option>
                                            <option value="Support Level 1/Steward Level 1">Support Level 1/Steward Level 1</option>
                                            <option value="Supervisor L2">Supervisor L2</option>
                                            <option value="Vertrieb & Beratung">Vertrieb & Beratung</option>
                                        </select>
                                    </div>
                                    <div>
                                        <label class="block text-xs font-bold uppercase text-slate-400 mb-1">Status</label>
                                        <select x-model="newTicketData.status" class="w-full bg-[#1f2937] border border-slate-700 rounded-xl px-4 py-2.5 text-sm focus:outline-none focus:border-blue-500 text-white">
                                            <option value="Offen">Offen</option>
                                            <option value="In Bearbeitung">In Bearbeitung</option>
                                            <option value="Abgeschlossen">Abgeschlossen</option>
                                        </select>
                                    </div>
                                </div>
                                <div>
                                    <label class="block text-xs font-bold uppercase text-slate-400 mb-1">Begründung & Vorfallstext</label>
                                    <textarea x-model="newTicketData.description" required rows="4" placeholder="Detaillierte Beschreibung der Situation einfügen..." class="w-full bg-[#1f2937] border border-slate-700 rounded-xl p-3 text-sm focus:outline-none focus:border-blue-500 resize-none text-white"></textarea>
                                </div>
                                <div class="flex items-center gap-3 bg-[#1f2937]/30 p-3 rounded-xl border border-slate-800">
                                    <input type="checkbox" id="escalateCheck" x-model="newTicketData.isEscalated" class="w-4 h-4 text-blue-600 border-slate-700 rounded bg-slate-900 focus:ring-blue-500">
                                    <label @click.prevent="newTicketData.isEscalated = !newTicketData.isEscalated" for="escalateCheck" class="text-xs font-semibold text-slate-300 cursor-pointer select-none">Als kritischen L2-Fall eskalieren</label>
                                </div>
                                <button type="submit" class="w-full bg-blue-600 hover:bg-blue-700 text-white font-bold text-sm py-2.5 rounded-xl shadow-md cursor-pointer">In der Cloud abspeichern</button>
                            </div>
                        </form>
                    </div>
                </div>

                <div x-show="currentView === 'ticket-detail'" class="max-w-5xl mx-auto space-y-4" style="display: none;">
                    <div class="flex items-center justify-between">
                        <button @click="currentView = 'tickets'" class="p-2 bg-[#111827] border border-slate-800 rounded-xl text-slate-400 hover:bg-slate-800 shadow-sm text-xs font-medium cursor-pointer">← Zurück</button>
                        <template x-if="(isAdmin || isSupervisor) && activeTicket && !activeTicket.isDeleted">
                            <button @click="deleteTicket(activeTicket.id)" class="bg-rose-600/20 hover:bg-rose-600 text-rose-400 hover:text-white border border-rose-500/30 text-xs font-bold px-4 py-2 rounded-xl transition-all shadow-md cursor-pointer">🗑 Ticket in Papierkorb verschieben</button>
                        </template>
                    </div>

                    <div class="bg-[#111827] border border-slate-800 rounded-2xl p-6 shadow-lg">
                        <div class="flex justify-between items-start border-b pb-4 border-slate-800">
                            <div>
                                <h1 class="text-2xl font-black text-white tracking-tight" :class="activeTicket && activeTicket.isDeleted ? 'line-through text-slate-500':''" x-text="activeTicket ? activeTicket.title : ''"></h1>
                                <p class="text-xs text-slate-500 mt-1" x-text="activeTicket ? activeTicket.subtitle : ''"></p>
                            </div>
                            <div class="flex items-center gap-3">
                                <select x-show="!activeTicket?.isDeleted" :value="activeTicket ? activeTicket.status : 'Offen'" @change="updateTicketStatus(activeTicket.id, $event.target.value)" class="bg-[#1f2937] border border-slate-700 rounded-lg text-xs font-bold text-slate-200 p-1.5 focus:outline-none">
                                    <option value="Offen">Offen</option>
                                    <option value="In Bearbeitung">In Bearbeitung</option>
                                    <option value="Abgeschlossen">Abgeschlossen</option>
                                </select>
                                <span class="bg-emerald-500/10 text-emerald-400 border border-emerald-500/20 text-xs font-bold px-3 py-1 rounded-full" x-text="activeTicket ? activeTicket.status : 'Offen'"></span>
                            </div>
                        </div>

                        <div class="grid grid-cols-1 md:grid-cols-3 gap-6 mt-6 items-start">
                            <div class="space-y-4">
                                <div class="bg-[#1f2937]/30 border border-slate-800 p-4 rounded-xl space-y-3 text-xs text-left">
                                    <div>
                                        <span class="text-[10px] text-slate-500 font-bold uppercase block tracking-wider mb-0.5">Bereich / Abteilung</span>
                                        <span class="font-semibold text-slate-300" x-text="activeTicket ? activeTicket.category : 'Allgemein'"></span>
                                    </div>
                                    <div>
                                        <span class="text-[10px] text-slate-500 font-bold uppercase block tracking-wider mb-0.5">Ersteller</span>
                                        <span class="font-semibold text-blue-400 font-mono" x-text="activeTicket ? activeTicket.createdBy : ''"></span>
                                    </div>
                                </div>
                            </div>

                            <div class="md:col-span-2 space-y-5">
                                <div class="bg-[#1f2937]/30 border border-slate-800 p-5 rounded-xl text-left">
                                    <h4 class="text-[10px] font-bold text-slate-500 uppercase tracking-wider">Inhalt der Anfrage</h4>
                                    <p class="text-xs font-semibold text-slate-300 mt-1" x-text="activeTicket ? activeTicket.description : ''"></p>
                                </div>

                                <div class="border border-slate-800 rounded-xl p-5 space-y-4 bg-[#111827]">
                                    <h3 class="font-bold text-xs text-white border-b pb-2 border-slate-800 uppercase tracking-wider">Interne Diskussion</h3>
                                    <div class="space-y-3 max-h-64 overflow-y-auto pr-1">
                                        <template x-for="c in activeComments">
                                            <div class="flex gap-3 p-3 bg-[#1f2937]/40 border border-slate-800 rounded-xl items-start text-left">
                                                <div class="w-7 h-7 bg-blue-600 text-white font-bold text-xs rounded-lg flex items-center justify-center shrink-0" x-text="c.initials"></div>
                                                <div class="text-xs flex-1">
                                                    <div class="flex items-center justify-between"><span class="font-bold text-slate-300" x-text="c.author"></span><span class="text-[10px] text-slate-500" x-text="c.date"></span></div>
                                                    <p class="text-slate-400 mt-1 font-medium" x-text="c.text"></p>
                                                </div>
                                            </div>
                                        </template>
                                    </div>

                                    <div x-show="!activeTicket?.isDeleted" class="pt-3 border-t border-slate-800 space-y-2">
                                        <textarea x-model="newComment" placeholder="Notiz hinterlassen..." class="w-full bg-[#1f2937] border border-slate-700 rounded-xl p-3 text-xs focus:outline-none focus:border-blue-500 h-20 resize-none font-medium text-white"></textarea>
                                        <div class="flex justify-end">
                                            <button @click="submitNewComment()" class="bg-blue-600 hover:bg-blue-700 text-white font-bold text-xs px-5 py-2 rounded-xl shadow-md cursor-pointer">Senden</button>
                                        </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>

                <div x-show="currentView === 'qa'" class="max-w-5xl mx-auto space-y-5" style="display: none;">
                    <div class="flex justify-between items-center"><h2 class="text-xl font-bold text-white tracking-tight">Steward Evaluation Center</h2></div>
                    <div class="border-b border-slate-800 flex gap-6 text-xs font-bold uppercase tracking-wider">
                        <button @click="qaSubTab = 'evaluations'" :class="qaSubTab === 'evaluations' ? 'text-blue-400 border-b-2 border-blue-500 pb-2' : 'text-slate-500 pb-2'" class="cursor-pointer">Neue Lizenz-Bewertung</button>
                        <button @click="qaSubTab = 'time-tracking'" :class="qaSubTab === 'time-tracking' ? 'text-blue-400 border-b-2 border-blue-500 pb-2' : 'text-slate-500 pb-2'" class="cursor-pointer">Historie</button>
                    </div>

                    <div x-show="qaSubTab === 'evaluations'" class="grid grid-cols-1 md:grid-cols-3 gap-6 items-start">
                        <div class="md:col-span-2 bg-[#111827] border border-slate-800 rounded-xl p-6 shadow-lg space-y-4">
                            <h3 class="font-bold text-sm text-white pb-2 border-b border-slate-800">Fahrerleistungsbewertung absenden</h3>
