# FlyPass eMSP Studio · Simulador Financiero y Ecosistema de Carga B2C (Colombia 2026)

Esta aplicación web interactiva es una herramienta de presentación comercial y estratégica de alto impacto, diseñada para **clientes, operadores de carga (CPOs como Terpel Voltex, Enel X Way, Celsia, EPM), juntas directivas y stakeholders**. Su objetivo es representar gráficamente el **flujo del dinero para el negocio eMSP (e-Mobility Service Provider)** en Colombia bajo el modelo B2C.

Esta aplicación modela con precisión la interacción entre el canal propio del CPO y la inyección de demanda masiva de **FlyPass como eMSP**.

---

## 1. El Viaje del Conductor Particular (B2C)

La aplicación modela el ciclo completo de experiencia del usuario natural en Colombia:
1. **Descubrimiento en FlyMap**: Abre la app de FlyPass y localiza electrolineras de cualquier operador integrado (**Terpel Voltex, Enel X Way, Celsia, EPM**) con disponibilidad de conectores y tarifas públicas transparentes (Módulos OCPI `Locations` y `Tariffs`).
2. **Autenticación e Inicio**: Llega a la estación física, escanea el código QR o acerca su Tag RFID. FlyPass autoriza la sesión al backend del CPO vía OCPI (`Commands` y `Tokens`).
3. **Telemetría en Vivo**: El cargador transfiere energía y FlyPass reporta en tiempo real los kWh y el costo acumulado (`Sessions`).
4. **Cierre de Sesión y CDR**: El CPO emite el **CDR (Charge Detail Record)** inmutable con la energía real suministrada (`CDRs`).
5. **Débito y Liquidación Mayorista**: FlyPass debita al conductor la tarifa minorista transparente (PVP) y liquida periódicamente al CPO la tarifa mayorista pactada.

---

## 2. Nueva Narrativa de Crecimiento: Demanda Incremental vs. Canibalización

En negociaciones con CPOs, la mayor objeción suele ser el temor a la canibalización de sus usuarios directos. El simulador despeja este temor con datos matemáticos:

- **Sesiones Base Orgánicas del CPO**: El volumen mensual habitual que el CPO ya atiende en su red propia.
- **Canibalización de Clientes Actuales (Preset 5.0% editable)**: Solo una pequeña fracción de conductores habituales del CPO migra a FlyPass por preferencia de billetera unificada (peajes, parqueaderos y carga en una sola factura).
- **Sesiones Adicionales Nuevas vía FlyPass (Uplift +35.0% editable)**: FlyPass moviliza a su comunidad de más de 500.000 conductores registrados hacia las electrolineras del CPO, inyectando demanda nueva que jamás habría llegado a su app nativa.
- **Beneficio Neto para el CPO (+25% a +35% de Utilidad)**: El margen obtenido por el volumen incremental nuevo supera por un factor de 5x a 8x el costo de la canibalización, incrementando la utilidad bruta neta del CPO de forma sustancial.

---

## 3. Estructura de Costos Reales: Canal Propio CPO vs. Canal FlyPass

### Canal Propio del CPO:
1. **Tarifa Pública (PVP)**: $1.700 COP/kWh.
2. **Pasarela de Pago (Genérica)**: 3.5% del GMV (estándar del mercado).
3. **OPEX Operativo CPO (Simplificado ~10.0% del GMV)**: Cubre licenciamiento CPMS SaaS por conector OCPP, conectividad IoT (SIMs 4G), mantenimiento preventivo/correctivo y mesa de ayuda al conductor en su app propia (referencia UPME e ICCT).
4. **Energía de Red Eléctrica**: ~$740 - $820 COP/kWh.
5. **Margen Neto en Canal Propio**: ~$670 COP/kWh.

### Canal FlyPass eMSP:
1. **Liquidación Mayorista (Descuento 15%)**: CPO recibe $1.445 COP/kWh limpios.
2. **Pasarela de Pago**: **0% para el CPO** (FlyPass asume el 1.7% de adquirencia bancaria preferencial).
3. **Soporte y App**: **0% para el CPO** (FlyPass asume el 100% de la atención 24/7 y la app).
4. **Energía de Red Eléctrica**: ~$800 COP/kWh.
5. **Margen Neto en Canal FlyPass**: **$645 COP/kWh limpios**, prácticamente idéntico al canal propio, pero sobre un **volumen incremental un 35% mayor**.

---

## 4. Características del Simulador

1. **Laboratorio de Variables con Sliders Reactivos**:
   - Parque vehicular VE objetivo y sesiones al mes.
   - Slider de **Sesiones Adicionales generadas por FlyPass (+% Uplift)**.
   - Slider de **Canibalización de Clientes del CPO (5.0% preset editable)**.
   - Descuento mayorista eMSP (5% a 30%).
   - Costo de red eléctrica ($/kWh) y tarifas PVP.
   - Adquirencia bancaria FlyPass (1.7%), Genérica CPO (3.5%) y OPEX CPO (10%).
2. **Núcleo Financiero con Tarjetas Ejecutivas en Paralelo**:
   - Margen Bruto FlyPass eMSP vs. Margen Bruto Total CPO (con indicador de Ganancia Neta Incremental vs. operar solo).
3. **Diagrama Sankey Financiero Interactivo**:
   - Mapea el GMV total, los canales (FlyPass vs CPO propio), pasarelas, OPEX CPO 10%, adquirencia 1.7%, energía de red y EBITDA neto.
4. **Gráfico de Punto Óptimo (Sweet Spot / Nash Equilibrium)**:
   - Curvas de rentabilidad que señalan la zona de acuerdo comercial ganar-ganar (12% a 18%).
5. **Cascada (Waterfall Chart) y Proyecciones a 5 Años Asset-Light**:
   - Payback estimado menor a 14 meses y TIR superior al 70%.

---

## 5. Cómo Iniciar la Aplicación

```bash
cd emsp-studio
npm start
```
Abre en tu navegador: [http://localhost:3600](http://localhost:3600)
