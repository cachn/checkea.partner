<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Checkea · Paneles y Planes</title>
  <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-[#070D13] text-slate-100 antialiased p-4 sm:p-6">
  <div class="mx-auto max-w-4xl">
    <!-- Cabecera -->
    <header class="mb-5 flex flex-wrap items-center justify-between gap-4 border-b border-slate-800/80 pb-4">
      <div class="flex items-center gap-3">
        <svg width="40" height="40" viewBox="0 0 120 120" fill="none" xmlns="http://www.w3.org/2000/svg" class="shrink-0 rounded-xl">
          <rect x="2" y="2" width="116" height="116" rx="28" fill="#0B1620" stroke="#182A3A" stroke-width="4"/>
          <path d="M77.5 34.5C71.8 30.8 65 28.8 57.8 28.8C38.2 28.8 22.4 44.6 22.4 64.2C22.4 83.8 38.2 99.6 57.8 99.6C71.9 99.6 84.1 91.4 89.8 79.5" stroke="#38C172" stroke-width="15" stroke-linecap="round"/>
          <path d="M44 63.5L56.5 76L95 37.5" stroke="#38C172" stroke-width="15" stroke-linecap="round" stroke-linejoin="round"/>
        </svg>
        <div>
          <span class="inline-flex items-baseline text-2xl font-bold tracking-tight">
            <span class="text-[#38C172]">c</span><span class="text-[#3B6EF6]">heckea</span><span class="text-[#38C172]">.</span>
          </span>
          <p class="text-xs text-slate-400">Centro de control de pagos</p>
        </div>
      </div>

      <div class="flex items-center gap-3">
        <span id="headerPlanBadge" class="rounded-full border border-[#38C172]/40 bg-[#38C172]/10 px-3 py-1 text-xs font-semibold text-[#38C172]">
          Plan Basic
        </span>
        <div class="rounded-xl border border-slate-800 bg-[#0D151D] px-3.5 py-2 text-right">
          <span class="block text-[10px] uppercase tracking-wider text-slate-400">Verificadas hoy</span>
          <span id="headerVerified" class="text-lg font-bold text-[#38C172]">18</span>
        </div>
      </div>
    </header>

    <!-- Navegación por paneles -->
    <nav class="mb-6 flex flex-wrap gap-2" aria-label="Paneles de Checkea">
      <button data-tab="inicio" class="tab-btn rounded-xl bg-[#38C172] px-4 py-2 text-xs font-semibold text-[#070D13]">
        Inicio
      </button>
      <button data-tab="verificar" class="tab-btn rounded-xl border border-slate-800 bg-[#0D151D] px-4 py-2 text-xs font-medium text-slate-300 hover:border-slate-700">
        Verificar pago
      </button>
      <button data-tab="historial" class="tab-btn rounded-xl border border-slate-800 bg-[#0D151D] px-4 py-2 text-xs font-medium text-slate-300 hover:border-slate-700">
        Historial y alertas
      </button>
      <button data-tab="usuario" class="tab-btn rounded-xl border border-slate-800 bg-[#0D151D] px-4 py-2 text-xs font-medium text-slate-300 hover:border-slate-700">
        Usuario y planes
      </button>
    </nav>

    <!-- PANEL 1: INICIO -->
    <section id="panel-inicio" class="panel-view space-y-6">
      <div class="rounded-2xl border border-slate-800 bg-[#0D151D] p-5">
        <span class="block text-[11px] font-semibold uppercase tracking-wider text-slate-400">
          Transacciones verificadas hoy
        </span>
        <div class="mt-1 flex items-baseline gap-3">
          <span id="homeVerified" class="text-4xl font-bold text-[#38C172]">18</span>
          <span class="text-xs text-slate-400">Actividad diaria confirmada sin depender de capturas</span>
        </div>
      </div>

      <div class="rounded-2xl border border-slate-800 bg-[#0D151D] p-5">
        <h2 class="mb-4 text-base font-semibold text-white">¿Qué deseas hacer?</h2>
        <div class="grid gap-3 sm:grid-cols-2">
          <button type="button" data-goto="verificar" class="goto-btn rounded-2xl border border-slate-800 bg-[#070D13] p-4 text-left transition hover:border-[#38C172]/60">
            <div class="text-sm font-semibold text-white">Verificar pago</div>
            <p class="mt-1 text-xs text-slate-400">Consultar una transacción de Pago Móvil</p>
          </button>

          <button type="button" data-goto="historial" class="goto-btn rounded-2xl border border-slate-800 bg-[#070D13] p-4 text-left transition hover:border-slate-600">
            <div class="text-sm font-semibold text-white">Historial</div>
            <p class="mt-1 text-xs text-slate-400">Revisar movimientos recientes y estados</p>
          </button>

          <button type="button" data-goto="historial" class="goto-btn rounded-2xl border border-slate-800 bg-[#070D13] p-4 text-left transition hover:border-rose-500/50">
            <div class="text-sm font-semibold text-white">Alertas</div>
            <p class="mt-1 text-xs text-slate-400">Consultar referencias duplicadas o advertencias</p>
          </button>

          <button type="button" data-goto="usuario" class="goto-btn rounded-2xl border border-slate-800 bg-[#070D13] p-4 text-left transition hover:border-slate-600">
            <div class="text-sm font-semibold text-white">Planes y cuenta</div>
            <p class="mt-1 text-xs text-slate-400">Ver datos del usuario, equipo y planes BCV</p>
          </button>
        </div>
      </div>

      <div class="rounded-2xl border border-slate-800 bg-[#0D151D] p-5">
        <div class="mb-3 flex items-center justify-between">
          <h3 class="text-sm font-semibold text-white">Últimas operaciones</h3>
          <button type="button" data-goto="historial" class="goto-btn text-xs font-medium text-[#38C172] hover:underline">
            Ver todas
          </button>
        </div>
        <div id="homeRecentOps" class="divide-y divide-slate-800/80"></div>
      </div>
    </section>

    <!-- PANEL 2: VERIFICAR PAGO -->
    <section id="panel-verificar" class="panel-view hidden">
      <div class="grid gap-6 md:grid-cols-2">
        <div class="rounded-2xl border border-slate-800 bg-[#0D151D] p-5">
          <h2 class="mb-1 text-base font-semibold text-white">Verificar Pago Móvil</h2>
          <p class="mb-4 text-xs text-slate-400">
            Ingresa el monto y al menos uno: últimos 4/6 dígitos de referencia, teléfono o cédula/RIF.
          </p>

          <form id="checkForm" class="space-y-4">
            <div class="grid grid-cols-3 gap-3">
              <div class="col-span-2">
                <label class="mb-1 block text-xs font-medium text-slate-300">Monto recibido</label>
                <input id="amount" type="number" step="0.01" min="0.01" value="2400.00" required
                  class="w-full rounded-xl border border-slate-700 bg-[#070D13] px-3.5 py-2.5 text-sm text-white outline-none focus:border-[#38C172]" />
              </div>
              <div>
                <label class="mb-1 block text-xs font-medium text-slate-300">Moneda</label>
                <select id="currency" class="w-full rounded-xl border border-slate-700 bg-[#070D13] px-3 py-2.5 text-sm text-white outline-none focus:border-[#38C172]">
                  <option value="VES">VES</option>
                  <option value="USD">USD</option>
                </select>
              </div>
            </div>

            <div>
              <label class="mb-1 block text-xs font-medium text-slate-300">Últimos 4 o 6 dígitos de referencia</label>
              <input id="refSuffix" type="text" maxlength="8" placeholder="Ej. 778899 o 8899"
                class="w-full rounded-xl border border-slate-700 bg-[#070D13] px-3.5 py-2.5 text-sm text-white outline-none focus:border-[#38C172]" />
            </div>

            <div class="grid gap-3 sm:grid-cols-2">
              <div>
                <label class="mb-1 block text-xs font-medium text-slate-300">Teléfono emisor</label>
                <input id="phone" type="text" placeholder="04141234567"
                  class="w-full rounded-xl border border-slate-700 bg-[#070D13] px-3.5 py-2.5 text-sm text-white outline-none focus:border-[#38C172]" />
              </div>
              <div>
                <label class="mb-1 block text-xs font-medium text-slate-300">Cédula / RIF</label>
                <input id="idNumber" type="text" placeholder="V19876543"
                  class="w-full rounded-xl border border-slate-700 bg-[#070D13] px-3.5 py-2.5 text-sm text-white outline-none focus:border-[#38C172]" />
              </div>
            </div>

            <p id="formError" class="hidden rounded-xl border border-rose-500/40 bg-rose-950/30 px-3 py-2 text-xs text-rose-300"></p>

            <button type="submit" class="w-full rounded-xl bg-[#38C172] px-4 py-3 text-sm font-semibold text-[#070D13] hover:bg-[#2fb367]">
              Checkear pago
            </button>
          </form>
        </div>

        <div id="statusCard" class="flex flex-col justify-between rounded-2xl border border-slate-800 bg-[#0D151D] p-5">
          <div>
            <div class="mb-3 flex items-center justify-between">
              <span class="text-xs font-medium uppercase tracking-wider text-slate-400">Resultado de verificación</span>
              <span id="statusBadge" class="rounded-full border border-slate-700 bg-slate-800 px-3 py-1 text-xs font-semibold text-slate-300">
                Listo para consultar
              </span>
            </div>
            <p id="statusTitle" class="mb-2 text-lg font-semibold text-white">
              Ingresa el monto y al menos un dato de Pago Móvil.
            </p>
            <p id="statusHint" class="text-sm text-slate-300/90">
              Una captura de pantalla nunca confirma el pago por sí sola.
            </p>
          </div>

          <div class="mt-6 rounded-xl border border-slate-800/80 bg-[#070D13]/70 p-3 text-xs text-slate-400">
            Regla activa: la misma referencia con igual monto y moneda no se aprueba dos veces.
          </div>
        </div>
      </div>
    </section>

    <!-- PANEL 3: HISTORIAL Y ALERTAS -->
    <section id="panel-historial" class="panel-view hidden space-y-6">
      <div class="rounded-2xl border border-slate-800 bg-[#0D151D] p-5">
        <div class="mb-3 flex items-center justify-between">
          <h2 class="text-base font-semibold text-white">Historial de operaciones</h2>
          <span class="text-xs text-slate-400">Comercio activo</span>
        </div>
        <div id="fullHistoryList" class="divide-y divide-slate-800/80"></div>
      </div>

      <div class="rounded-2xl border border-slate-800 bg-[#0D151D] p-5">
        <div class="mb-3 flex items-center justify-between">
          <h2 class="text-base font-semibold text-white">Alertas de seguridad</h2>
          <span id="alertsBadgeCount" class="rounded-full bg-rose-500/15 px-2.5 py-0.5 text-xs font-medium text-rose-400">0 activas</span>
        </div>
        <div id="alertsList" class="space-y-2 text-xs text-slate-400">
          No hay alertas registradas en esta sesión.
        </div>
      </div>
    </section>

    <!-- PANEL 4: USUARIO Y PLANES -->
    <section id="panel-usuario" class="panel-view hidden space-y-6">
      <div class="rounded-2xl border border-slate-800 bg-[#0D151D] p-5">
        <div class="mb-4 flex flex-wrap items-center justify-between gap-2">
          <div>
            <h2 class="text-base font-semibold text-white">Datos del usuario y comercio</h2>
            <p class="text-xs text-slate-400">Configura tu cuenta, equipo y referencia de tasa BCV para Pago Móvil.</p>
          </div>
          <span id="activePlanPill" class="rounded-full border border-[#38C172]/40 bg-[#38C172]/10 px-3 py-1 text-xs font-semibold text-[#38C172]">
            Plan Basic · 1–3 usuarios
          </span>
        </div>

        <form id="profileForm" class="grid gap-4 sm:grid-cols-2">
          <div>
            <label class="mb-1 block text-xs font-medium text-slate-300">Nombre del usuario</label>
            <input id="userName" type="text" value="Usuario Demo"
              class="w-full rounded-xl border border-slate-700 bg-[#070D13] px-3.5 py-2 text-sm text-white outline-none focus:border-[#38C172]" />
          </div>

          <div>
            <label class="mb-1 block text-xs font-medium text-slate-300">Rol</label>
            <select id="userRole" class="w-full rounded-xl border border-slate-700 bg-[#070D13] px-3.5 py-2 text-sm text-white outline-none focus:border-[#38C172]">
              <option value="Dueño / Administrador">Dueño / Administrador</option>
              <option value="Supervisor / Encargado">Supervisor / Encargado</option>
              <option value="Cajero / Vendedor">Cajero / Vendedor</option>
            </select>
          </div>

          <div>
            <label class="mb-1 block text-xs font-medium text-slate-300">Nombre del comercio</label>
            <input id="merchantName" type="text" value="Comercio Demo Caracas"
              class="w-full rounded-xl border border-slate-700 bg-[#070D13] px-3.5 py-2 text-sm text-white outline-none focus:border-[#38C172]" />
          </div>

          <div>
            <label class="mb-1 block text-xs font-medium text-slate-300">Tasa BCV del día (Bs. / USD)</label>
            <input id="bcvRate" type="number" step="0.01" min="1" value="50.00"
              class="w-full rounded-xl border border-slate-700 bg-[#070D13] px-3.5 py-2 text-sm text-white outline-none focus:border-[#38C172]" />
          </div>

          <div class="sm:col-span-2 flex items-center justify-between pt-2">
            <span id="profileSavedMsg" class="text-xs text-[#38C172]"></span>
            <button type="submit" class="rounded-xl bg-[#38C172] px-4 py-2.5 text-xs font-semibold text-[#070D13] hover:bg-[#2fb367]">
              Guardar datos
            </button>
          </div>
        </form>
      </div>

      <!-- Planes mensuales al cambio BCV por Pago Móvil -->
      <div class="rounded-2xl border border-slate-800 bg-[#0D151D] p-5">
        <div class="mb-4 flex flex-wrap items-center justify-between gap-2">
          <div>
            <h3 class="text-base font-semibold text-white">Planes mensuales (Pago Móvil al cambio BCV)</h3>
            <p class="text-xs text-slate-400">Escala según cantidad de usuarios, velocidad operativa y equipos multi-caja.</p>
          </div>
          <span class="text-xs text-slate-400">Tasa activa: <strong id="bcvDisplay" class="text-white">50.00</strong> Bs/$</span>
        </div>

        <div class="grid gap-4 md:grid-cols-3">
          <!-- Plan Basic -->
          <div id="card-BASIC" class="plan-card flex flex-col justify-between rounded-2xl border border-[#38C172]/60 bg-[#070D13] p-4">
            <div>
              <div class="flex items-center justify-between">
                <span class="text-sm font-bold text-white">Basic</span>
                <span class="rounded-full bg-slate-800 px-2.5 py-0.5 text-[11px] text-slate-300">1 a 3 usuarios</span>
              </div>
              <div class="mt-3">
                <span class="text-2xl font-bold text-white">$11,99</span>
                <span class="text-xs text-slate-400"> / mes</span>
                <div class="text-xs font-medium text-[#38C172]">≈ Bs. <span class="ves-calc" data-usd="11.99">599.50</span> al cambio BCV</div>
              </div>
              <ul class="mt-3 space-y-1.5 text-xs text-slate-300">
                <li>• Verificación de Pago Móvil sin capturas</li>
                <li>• Bloqueo de referencias duplicadas</li>
                <li>• Historial y alertas esenciales</li>
              </ul>
            </div>
            <button type="button" data-select-plan="BASIC" class="select-plan-btn mt-4 w-full rounded-xl bg-[#38C172] py-2 text-xs font-semibold text-[#070D13]">
              Plan seleccionado
            </button>
          </div>

          <!-- Plan Pro -->
          <div id="card-PRO" class="plan-card flex flex-col justify-between rounded-2xl border border-slate-800 bg-[#070D13] p-4">
            <div>
              <div class="flex items-center justify-between">
                <span class="text-sm font-bold text-white">Pro</span>
                <span class="rounded-full bg-blue-500/15 px-2.5 py-0.5 text-[11px] text-blue-300">Hasta 5 usuarios</span>
              </div>
              <div class="mt-3">
                <span class="text-2xl font-bold text-white">$14,99</span>
                <span class="text-xs text-slate-400"> / mes</span>
                <div class="text-xs font-medium text-[#38C172]">≈ Bs. <span class="ves-calc" data-usd="14.99">749.50</span> al cambio BCV</div>
              </div>
              <ul class="mt-3 space-y-1.5 text-xs text-slate-300">
                <li>• Todo lo de Basic + mayor velocidad en caja</li>
                <li>• Menos trabajo manual y cierre más ágil</li>
                <li>• Hasta 5 usuarios con roles operativos</li>
              </ul>
            </div>
            <button type="button" data-select-plan="PRO" class="select-plan-btn mt-4 w-full rounded-xl border border-slate-700 bg-[#0D151D] py-2 text-xs font-semibold text-white hover:border-[#38C172]">
              Elegir Pro
            </button>
          </div>

          <!-- Plan Business -->
          <div id="card-BUSINESS" class="plan-card flex flex-col justify-between rounded-2xl border border-slate-800 bg-[#070D13] p-4">
            <div>
              <div class="flex items-center justify-between">
                <span class="text-sm font-bold text-white">Business</span>
                <span class="rounded-full bg-amber-500/15 px-2.5 py-0.5 text-[11px] text-amber-300">Usuarios ilimitados</span>
              </div>
              <div class="mt-3">
                <span class="text-2xl font-bold text-white">$16,99</span>
                <span class="text-xs text-slate-400"> / mes</span>
                <div class="text-xs font-medium text-[#38C172]">≈ Bs. <span class="ves-calc" data-usd="16.99">849.50</span> al cambio BCV</div>
              </div>
              <ul class="mt-3 space-y-1.5 text-xs text-slate-300">
                <li>• Todo lo de Pro + usuarios ilimitados</li>
                <li>• Equipos multi-caja y control por turnos</li>
                <li>• Máxima agilidad y trazabilidad</li>
              </ul>
            </div>
            <button type="button" data-select-plan="BUSINESS" class="select-plan-btn mt-4 w-full rounded-xl border border-slate-700 bg-[#0D151D] py-2 text-xs font-semibold text-white hover:border-[#38C172]">
              Elegir Business
            </button>
          </div>
        </div>
      </div>
    </section>
  </div>

  <script>
    let verifiedCount = 18;
    let opCounter = 185;
    let currentPlan = "BASIC";
    const usedRefs = new Set();
    const alerts = [];

    const planMeta = {
      BASIC: { label: "Plan Basic", pill: "Plan Basic · 1–3 usuarios" },
      PRO: { label: "Plan Pro", pill: "Plan Pro · Hasta 5 usuarios" },
      BUSINESS: { label: "Plan Business", pill: "Plan Business · Usuarios ilimitados" }
    };

    const operations = [
      { code: "#00182", amount: "35.00", currency: "USD", summary: "Ref ···482910", status: "VERIFIED", time: "Hoy · 18:05" },
      { code: "#00183", amount: "18.00", currency: "USD", summary: "Tel ···1234", status: "PENDING", time: "Hoy · 18:11" },
      { code: "#00184", amount: "50.00", currency: "USD", summary: "CI V-24888999", status: "NOT_FOUND", time: "Hoy · 18:16" }
    ];

    function updateBcvCalculations() {
      const rateInput = document.getElementById("bcvRate");
      const rate = Math.max(1, parseFloat(rateInput.value) || 50);
      document.getElementById("bcvDisplay").textContent = rate.toFixed(2);
      document.querySelectorAll(".ves-calc").forEach((el) => {
        const usd = parseFloat(el.dataset.usd);
        el.textContent = (usd * rate).toFixed(2);
      });
    }

    function renderPlanSelection() {
      document.getElementById("headerPlanBadge").textContent = planMeta[currentPlan].label;
      document.getElementById("activePlanPill").textContent = planMeta[currentPlan].pill;

      ["BASIC", "PRO", "BUSINESS"].forEach((planKey) => {
        const card = document.getElementById(`card-${planKey}`);
        const btn = card.querySelector(".select-plan-btn");
        if (planKey === currentPlan) {
          card.className = "plan-card flex flex-col justify-between rounded-2xl border border-[#38C172]/60 bg-[#070D13] p-4";
          btn.className = "select-plan-btn mt-4 w-full rounded-xl bg-[#38C172] py-2 text-xs font-semibold text-[#070D13]";
          btn.textContent = "Plan seleccionado";
        } else {
          card.className = "plan-card flex flex-col justify-between rounded-2xl border border-slate-800 bg-[#070D13] p-4";
          btn.className = "select-plan-btn mt-4 w-full rounded-xl border border-slate-700 bg-[#0D151D] py-2 text-xs font-semibold text-white hover:border-[#38C172]";
          btn.textContent = `Elegir ${planKey.charAt(0) + planKey.slice(1).toLowerCase()}`;
        }
      });
    }

    document.querySelectorAll(".select-plan-btn").forEach((btn) => {
      btn.addEventListener("click", () => {
        currentPlan = btn.dataset.selectPlan;
        renderPlanSelection();
        document.getElementById("profileSavedMsg").textContent =
          `Plan cambiado a ${planMeta[currentPlan].label} (pago mensual por Pago Móvil al cambio BCV).`;
      });
    });

    document.getElementById("bcvRate").addEventListener("input", updateBcvCalculations);

    function switchTab(tabName) {
      document.querySelectorAll(".panel-view").forEach((p) => p.classList.add("hidden"));
      document.getElementById(`panel-${tabName}`).classList.remove("hidden");

      document.querySelectorAll(".tab-btn").forEach((btn) => {
        if (btn.dataset.tab === tabName) {
          btn.className = "tab-btn rounded-xl bg-[#38C172] px-4 py-2 text-xs font-semibold text-[#070D13]";
        } else {
          btn.className = "tab-btn rounded-xl border border-slate-800 bg-[#0D151D] px-4 py-2 text-xs font-medium text-slate-300 hover:border-slate-700";
        }
      });
    }

    document.querySelectorAll(".tab-btn").forEach((btn) => {
      btn.addEventListener("click", () => switchTab(btn.dataset.tab));
    });
    document.querySelectorAll(".goto-btn").forEach((btn) => {
      btn.addEventListener("click", () => switchTab(btn.dataset.goto));
    });

    function badgeHtml(st) {
      if (st === "VERIFIED") {
        return `<span class="rounded-full bg-emerald-500/15 px-2.5 py-1 text-xs font-medium text-emerald-400">Confirmado</span>`;
      }
      if (st === "FLAGGED_DUPLICATE") {
        return `<span class="rounded-full bg-rose-500/15 px-2.5 py-1 text-xs font-medium text-rose-400">Alerta</span>`;
      }
      if (st === "NOT_FOUND") {
        return `<span class="rounded-full bg-slate-700/60 px-2.5 py-1 text-xs font-medium text-slate-300">No verificado</span>`;
      }
      return `<span class="rounded-full bg-amber-500/15 px-2.5 py-1 text-xs font-medium text-amber-300">Pendiente</span>`;
    }

    function renderLists() {
      document.getElementById("headerVerified").textContent = String(verifiedCount);
      document.getElementById("homeVerified").textContent = String(verifiedCount);

      const recentHtml = operations.slice(0, 3).map((op) => `
        <div class="flex flex-wrap items-center justify-between gap-2 py-3 text-sm">
          <div>
            <span class="font-medium text-white">${op.code}</span>
            <span class="ml-2 text-xs text-slate-400">${op.summary} · ${op.time}</span>
          </div>
          <div class="flex items-center gap-3">
            <span class="font-semibold text-slate-200">${op.currency} ${op.amount}</span>
            ${badgeHtml(op.status)}
          </div>
        </div>
      `).join("");

      const fullHtml = operations.map((op) => `
        <div class="flex flex-wrap items-center justify-between gap-2 py-3 text-sm">
          <div>
            <span class="font-medium text-white">${op.code}</span>
            <span class="ml-2 text-xs text-slate-400">${op.summary} · ${op.time}</span>
          </div>
          <div class="flex items-center gap-3">
            <span class="font-semibold text-slate-200">${op.currency} ${op.amount}</span>
            ${badgeHtml(op.status)}
          </div>
        </div>
      `).join("");

      document.getElementById("homeRecentOps").innerHTML = recentHtml;
      document.getElementById("fullHistoryList").innerHTML = fullHtml;

      const alertCountEl = document.getElementById("alertsBadgeCount");
      const alertsListEl = document.getElementById("alertsList");
      alertCountEl.textContent = `${alerts.length} ${alerts.length === 1 ? "activa" : "activas"}`;

      if (alerts.length > 0) {
        alertsListEl.innerHTML = alerts.map((a) => `
          <div class="rounded-xl border border-rose-500/40 bg-rose-950/25 p-3 text-rose-200">
            <div class="font-semibold text-rose-300">${a.title}</div>
            <div class="mt-0.5 text-xs text-rose-200/80">${a.detail}</div>
          </div>
        `).join("");
      }
    }

    const form = document.getElementById("checkForm");
    const formError = document.getElementById("formError");
    const statusCard = document.getElementById("statusCard");
    const statusBadge = document.getElementById("statusBadge");
    const statusTitle = document.getElementById("statusTitle");
    const statusHint = document.getElementById("statusHint");

    function setResultState(type, badge, title, hint) {
      statusBadge.textContent = badge;
      statusTitle.textContent = title;
      statusHint.textContent = hint;

      if (type === "VERIFIED") {
        statusCard.className = "flex flex-col justify-between rounded-2xl border border-emerald-500/40 bg-emerald-950/25 p-5";
        statusBadge.className = "rounded-full border border-emerald-500/30 bg-emerald-500/15 px-3 py-1 text-xs font-semibold text-emerald-400";
      } else {
        statusCard.className = "flex flex-col justify-between rounded-2xl border border-rose-500/50 bg-rose-950/30 p-5";
        statusBadge.className = "rounded-full border border-rose-500/30 bg-rose-500/15 px-3 py-1 text-xs font-semibold text-rose-400";
      }
    }

    form.addEventListener("submit", (e) => {
      e.preventDefault();
      formError.classList.add("hidden");

      const amount = parseFloat(document.getElementById("amount").value);
      const currency = document.getElementById("currency").value;
      const refSuffix = document.getElementById("refSuffix").value.trim().toUpperCase();
      const phone = document.getElementById("phone").value.trim();
      const idNumber = document.getElementById("idNumber").value.trim().toUpperCase();

      if (!refSuffix && !phone && !idNumber) {
        formError.textContent = "Debes indicar al menos uno: últimos 4/6 dígitos de referencia, teléfono o cédula/RIF.";
        formError.classList.remove("hidden");
        return;
      }

      const key = `${currency}-${amount.toFixed(2)}-${refSuffix || phone || idNumber}`;
      const summary = [
        refSuffix ? `Ref ${refSuffix}` : null,
        phone ? `Tel ${phone}` : null,
        idNumber ? `CI ${idNumber}` : null
      ].filter(Boolean).join(" · ");

      let opStatus = "VERIFIED";
      if (refSuffix && usedRefs.has(key)) {
        opStatus = "FLAGGED_DUPLICATE";
        setResultState(
          "DUPLICATE",
          "Alerta · Duplicada",
          "Referencia duplicada detectada: bloqueada para revisión.",
          "Esta referencia ya fue usada con el mismo monto y moneda. No entregues el producto."
        );
        alerts.unshift({
          title: `Referencia duplicada (${refSuffix})`,
          detail: `${currency} ${amount.toFixed(2)} · ${summary}`
        });
      } else {
        if (refSuffix) usedRefs.add(key);
        verifiedCount += 1;
        setResultState(
          "VERIFIED",
          "Confirmado",
          `Pago Móvil de ${currency} ${amount.toFixed(2)} confirmado.`,
          "Validación aprobada sin duplicados. Puedes entregar el producto."
        );
      }

      operations.unshift({
        code: `#00${opCounter++}`,
        amount: amount.toFixed(2),
        currency,
        summary,
        status: opStatus,
        time: "Ahora"
      });

      renderLists();
    });

    document.getElementById("profileForm").addEventListener("submit", (e) => {
      e.preventDefault();
      updateBcvCalculations();
      const uName = document.getElementById("userName").value.trim() || "Usuario Demo";
      const mName = document.getElementById("merchantName").value.trim() || "Comercio Demo";
      document.getElementById("profileSavedMsg").textContent =
        `Guardado: ${uName} · ${mName} (${planMeta[currentPlan].label})`;
    });

    updateBcvCalculations();
    renderPlanSelection();
    renderLists();
  </script>
</body>
</html>
