# Guia-para-analizar-empresas
Guia para analizar empresas
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Manual de Análisis Fundamental</title>
    <style>
        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
            line-height: 1.6;
            margin: 0;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
        }
        
        .container {
            max-width: 900px;
            margin: 0 auto;
            background: white;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 20px 40px rgba(0,0,0,0.1);
            margin-top: 20px;
            margin-bottom: 20px;
        }
        
        .header {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 50px 40px;
            text-align: center;
        }
        
        .header h1 {
            font-size: 2.5rem;
            margin: 0 0 10px 0;
            font-weight: 700;
        }
        
        .header p {
            font-size: 1.2rem;
            margin: 0;
            opacity: 0.9;
        }
        
        .content {
            padding: 40px;
        }
        
        .toc {
            background: linear-gradient(135deg, #f8f9fa 0%, #e9ecef 100%);
            border-left: 5px solid #667eea;
            padding: 30px;
            margin: 30px 0;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.08);
        }
        
        .toc h2 {
            color: #667eea;
            margin-bottom: 20px;
            font-size: 1.5rem;
        }
        
        .toc-item {
            display: flex;
            justify-content: space-between;
            padding: 10px 0;
            border-bottom: 1px dotted #ccc;
            transition: background-color 0.3s;
        }
        
        .toc-item:hover {
            background-color: rgba(102, 126, 234, 0.1);
            border-radius: 5px;
            padding-left: 10px;
        }
        
        h1 {
            color: #2d3748;
            font-size: 2rem;
            margin: 50px 0 25px 0;
            border-bottom: 3px solid #667eea;
            padding-bottom: 10px;
            position: relative;
        }
        
        h1::before {
            content: '';
            position: absolute;
            bottom: -3px;
            left: 0;
            width: 60px;
            height: 3px;
            background: #764ba2;
        }
        
        h2 {
            color: #4a5568;
            font-size: 1.4rem;
            margin: 30px 0 15px 0;
            border-left: 4px solid #667eea;
            padding-left: 15px;
            background: linear-gradient(90deg, rgba(102, 126, 234, 0.1) 0%, transparent 100%);
            padding-top: 10px;
            padding-bottom: 10px;
            border-radius: 0 5px 5px 0;
        }
        
        h3 {
            color: #2d3748;
            font-size: 1.2rem;
            margin: 25px 0 12px 0;
            font-weight: 600;
        }
        
        .highlight {
            background: linear-gradient(135deg, #e6fffa 0%, #b2f5ea 100%);
            border: 1px solid #81e6d9;
            border-left: 5px solid #38b2ac;
            padding: 20px;
            margin: 20px 0;
            border-radius: 10px;
            box-shadow: 0 3px 10px rgba(56, 178, 172, 0.1);
        }
        
        .formula {
            background: linear-gradient(135deg, #fffaf0 0%, #fef5e7 100%);
            border: 1px solid #fbb6ce;
            border-left: 5px solid #ed8936;
            padding: 20px;
            margin: 20px 0;
            border-radius: 10px;
            font-family: 'Courier New', monospace;
            font-weight: bold;
            box-shadow: 0 3px 10px rgba(237, 137, 54, 0.1);
        }
        
        .warning {
            background: linear-gradient(135deg, #fed7d7 0%, #feb2b2 100%);
            border: 1px solid #fc8181;
            border-left: 5px solid #e53e3e;
            padding: 20px;
            margin: 20px 0;
            border-radius: 10px;
            box-shadow: 0 3px 10px rgba(229, 62, 62, 0.1);
        }
        
        .info {
            background: linear-gradient(135deg, #e0e7ff 0%, #c7d2fe 100%);
            border: 1px solid #a5b4fc;
            border-left: 5px solid #6366f1;
            padding: 20px;
            margin: 20px 0;
            border-radius: 10px;
            box-shadow: 0 3px 10px rgba(99, 102, 241, 0.1);
        }
        
        table {
            width: 100%;
            border-collapse: collapse;
            margin: 25px 0;
            background: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0,0,0,0.08);
        }
        
        th {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 15px;
            text-align: left;
            font-weight: 600;
        }
        
        td {
            padding: 12px 15px;
            border-bottom: 1px solid #e2e8f0;
            transition: background-color 0.3s;
        }
        
        tr:nth-child(even) {
            background: #f7fafc;
        }
        
        tr:hover {
            background: rgba(102, 126, 234, 0.05);
        }
        
        ul, ol {
            margin: 15px 0 15px 25px;
        }
        
        li {
            margin-bottom: 8px;
        }
        
        .checklist {
            background: linear-gradient(135deg, #f0fff4 0%, #dcfce7 100%);
            border: 1px solid #86efac;
            border-left: 5px solid #22c55e;
            padding: 20px;
            margin: 20px 0;
            border-radius: 10px;
            box-shadow: 0 3px 10px rgba(34, 197, 94, 0.1);
        }
        
        .checklist input[type="checkbox"] {
            margin-right: 10px;
            transform: scale(1.2);
        }
        
        .section-divider {
            height: 4px;
            background: linear-gradient(90deg, #667eea, #764ba2, #667eea);
            margin: 40px 0;
            border-radius: 2px;
        }
        
        .download-btn {
            position: fixed;
            top: 20px;
            right: 20px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            padding: 12px 20px;
            border: none;
            border-radius: 25px;
            cursor: pointer;
            font-weight: 600;
            box-shadow: 0 5px 15px rgba(102, 126, 234, 0.3);
            z-index: 1000;
            transition: all 0.3s ease;
        }
        
        .download-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 7px 20px rgba(102, 126, 234, 0.4);
        }
        
        .footer {
            background: linear-gradient(135deg, #2d3748 0%, #4a5568 100%);
            color: white;
            padding: 40px;
            text-align: center;
            border-radius: 0 0 15px 15px;
        }
        
        .metrics-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin: 20px 0;
        }
        
        .metric-card {
            background: linear-gradient(135deg, #f8f9fa 0%, #e9ecef 100%);
            padding: 20px;
            border-radius: 10px;
            border-left: 4px solid #667eea;
            text-align: center;
            box-shadow: 0 3px 10px rgba(0,0,0,0.05);
            transition: transform 0.3s ease;
        }
        
        .metric-card:hover {
            transform: translateY(-5px);
        }
        
        .metric-value {
            font-size: 1.5rem;
            font-weight: 700;
            color: #667eea;
            margin-bottom: 5px;
        }
        
        .metric-label {
            font-size: 0.9rem;
            color: #4a5568;
        }
        
        @media (max-width: 768px) {
            .container {
                margin: 10px;
                border-radius: 10px;
            }
            
            .content {
                padding: 20px;
            }
            
            .header {
                padding: 30px 20px;
            }
            
            .header h1 {
                font-size: 2rem;
            }
            
            .metrics-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <button class="download-btn" onclick="window.print()">📄 Descargar PDF</button>
    
    <div class="container">
        <div class="header">
            <h1>Manual de Análisis Fundamental</h1>
            <p>Guía Completa para el Análisis de Empresas</p>
        </div>
        
        <div class="content">
            <div class="toc">
                <h2>📚 Tabla de Contenidos</h2>
                <div class="toc-item">
                    <span>1. Introducción al Análisis Fundamental</span>
                    <span>Página 3</span>
                </div>
                <div class="toc-item">
                    <span>2. Métricas de Crecimiento</span>
                    <span>Página 4</span>
                </div>
                <div class="toc-item">
                    <span>3. Métricas de Rentabilidad</span>
                    <span>Página 7</span>
                </div>
                <div class="toc-item">
                    <span>4. Flujo de Caja</span>
                    <span>Página 10</span>
                </div>
                <div class="toc-item">
                    <span>5. Métricas de Valoración</span>
                    <span>Página 12</span>
                </div>
                <div class="toc-item">
                    <span>6. Análisis de Dividendos</span>
                    <span>Página 15</span>
                </div>
                <div class="toc-item">
                    <span>7. Análisis Cualitativo</span>
                    <span>Página 17</span>
                </div>
                <div class="toc-item">
                    <span>8. Caso de Estudio: Novo Nordisk</span>
                    <span>Página 20</span>
                </div>
                <div class="toc-item">
                    <span>9. Recursos y Conclusiones</span>
                    <span>Página 22</span>
                </div>
            </div>

            <h1>📊 Introducción al Análisis Fundamental</h1>
            
            <div class="highlight">
                <h3>¿Qué es el Análisis Fundamental?</h3>
                <p>El análisis fundamental evalúa el <strong>valor intrínseco</strong> de una empresa mediante el examen detallado de sus estados financieros, modelo de negocio, posición competitiva y factores macroeconómicos.</p>
            </div>

            <div class="info">
                <h3>🎯 Objetivo Principal</h3>
                <p>Determinar si una acción está <strong>infravalorada</strong>, <strong>sobrevalorada</strong> o <strong>correctamente valorada</strong> por el mercado, proporcionando una base sólida para decisiones de inversión a largo plazo.</p>
            </div>

            <div class="highlight">
                <h3>💡 Principio Fundamental</h3>
                <p>Una inversión es atractiva cuando el <strong>precio de mercado</strong> es inferior al <strong>valor intrínseco estimado</strong>, proporcionando un margen de seguridad adecuado.</p>
            </div>

            <div class="section-divider"></div>

            <h1>📈 Métricas de Crecimiento</h1>

            <h2>1. Crecimiento de Ingresos</h2>
            
            <div class="formula">
                <strong>Fórmula:</strong><br>
                Crecimiento = ((Ingresos Año Actual - Ingresos Año Anterior) / Ingresos Año Anterior) × 100
            </div>

            <table>
                <thead>
                    <tr>
                        <th>Tipo de Empresa</th>
                        <th>Crecimiento Esperado</th>
                        <th>Características</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>Startups Tecnológicas</td>
                        <td>20-50% anual</td>
                        <td>Alto riesgo, alta recompensa</td>
                    </tr>
                    <tr>
                        <td>Empresas Establecidas</td>
                        <td>5-15% anual</td>
                        <td>Crecimiento sostenible</td>
                    </tr>
                    <tr>
                        <td>Empresas Maduras</td>
                        <td>2-5% anual</td>
                        <td>Estabilidad y dividendos</td>
                    </tr>
                </tbody>
            </table>

            <h2>2. Earnings Per Share (EPS)</h2>
            
            <div class="highlight">
                <h3>Definición</h3>
                <p><strong>EPS:</strong> Beneficio neto por acción en circulación. Es una de las métricas más importantes para evaluar la rentabilidad por acción.</p>
            </div>

            <div class="formula">
                EPS = (Beneficio Neto - Dividendos Preferenciales) / Acciones en Circulación
            </div>

            <table>
                <thead>
                    <tr>
                        <th>Sector</th>
                        <th>Rango EPS Típico</th>
                        <th>Características</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>Tecnología</td>
                        <td>$3-10</td>
                        <td>Alto crecimiento, R&D intensivo</td>
                    </tr>
                    <tr>
                        <td>Banca/Financiero</td>
                        <td>$5-15</td>
                        <td>Sensible a tasas de interés</td>
                    </tr>
                    <tr>
                        <td>Energía</td>
                        <td>$5-20</td>
                        <td>Cíclico, dependiente de commodities</td>
                    </tr>
                    <tr>
                        <td>Salud/Farmacéutico</td>
                        <td>$5-15</td>
                        <td>Defensivo, regulado</td>
                    </tr>
                </tbody>
            </table>

            <div class="warning">
                <h3>⚠️ Factores que Distorsionan el EPS</h3>
                <ul>
                    <li><strong>Ventas de activos:</strong> Ganancias no recurrentes que inflan temporalmente el EPS</li>
                    <li><strong>Recompras de acciones:</strong> Reducen denominador, inflando artificialmente el valor</li>
                    <li><strong>Items extraordinarios:</strong> Ganancias/pérdidas excepcionales no repetibles</li>
                </ul>
            </div>

            <h2>3. CAGR (Compound Annual Growth Rate)</h2>
            
            <div class="formula">
                CAGR = (Valor Final / Valor Inicial)^(1/años) - 1
            </div>

            <table>
                <thead>
                    <tr>
                        <th>CAGR</th>
                        <th>Clasificación</th>
                        <th>Interpretación</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>5-8%</td>
                        <td>✅ Aceptable</td>
                        <td>Crecimiento sólido</td>
                    </tr>
                    <tr>
                        <td>8-12%</td>
                        <td>⭐ Muy bueno</td>
                        <td>Excelente rendimiento</td>
                    </tr>
                    <tr>
                        <td>12-15%</td>
                        <td>🚀 Excepcional</td>
                        <td>Rendimiento excepcional</td>
                    </tr>
                    <tr>
                        <td>15%+</td>
                        <td>⚠️ Precaución</td>
                        <td>Evaluar sostenibilidad</td>
                    </tr>
                </tbody>
            </table>

            <div class="section-divider"></div>

            <h1>💰 Métricas de Rentabilidad</h1>

            <h2>1. Márgenes de Rentabilidad</h2>

            <div class="metrics-grid">
                <div class="metric-card">
                    <div class="metric-value">Margen Bruto</div>
                    <div class="metric-label">(Ingresos - COGS) / Ingresos</div>
                </div>
                <div class="metric-card">
                    <div class="metric-value">Margen Operativo</div>
                    <div class="metric-label">EBIT / Ingresos</div>
                </div>
                <div class="metric-card">
                    <div class="metric-value">Margen Neto</div>
                    <div class="metric-label">Beneficio Neto / Ingresos</div>
                </div>
            </div>

            <h2>2. Return on Equity (ROE)</h2>
            
            <div class="formula">
                ROE = Beneficio Neto / Patrimonio de Accionistas × 100
            </div>

            <table>
                <thead>
                    <tr>
                        <th>Rango ROE</th>
                        <th>Clasificación</th>
                        <th>Interpretación</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>&lt; 10%</td>
                        <td>Bajo</td>
                        <td>Generalmente insuficiente</td>
                    </tr>
                    <tr>
                        <td>10-15%</td>
                        <td>Aceptable</td>
                        <td>Rendimiento promedio</td>
                    </tr>
                    <tr>
                        <td>15-20%</td>
                        <td>Bueno</td>
                        <td>Por encima del promedio</td>
                    </tr>
                    <tr>
                        <td>&gt; 20%</td>
                        <td>Excelente</td>
                        <td>Verificar sostenibilidad</td>
                    </tr>
                </tbody>
            </table>

            <div class="info">
                <h3>Tasa de Crecimiento Sostenible</h3>
                <p><strong>Fórmula:</strong> ROE × Ratio de Retención</p>
                <p>Si una empresa crece por debajo de su tasa sostenible, puede estar infravalorada.</p>
            </div>

            <div class="warning">
                <h3>Señales de Alerta en ROE</h3>
                <ul>
                    <li><strong>ROE muy alto con poco patrimonio:</strong> Alto riesgo por apalancamiento excesivo</li>
                    <li><strong>ROE inflado por deuda:</strong> El patrimonio se reduce al restar deuda</li>
                    <li><strong>Patrimonio negativo:</strong> No se puede calcular ROE</li>
                </ul>
            </div>

            <h2>3. Return on Invested Capital (ROIC)</h2>
            
            <div class="formula">
                ROIC = NOPAT / Capital Invertido<br>
                Capital Invertido = Patrimonio + Deuda - Efectivo Excedente
            </div>

            <div class="highlight">
                <h3>Regla Clave</h3>
                <p><strong>ROIC > WACC</strong> indica que la empresa está creando valor para los accionistas.</p>
            </div>

            <div class="section-divider"></div>

            <h1>💸 Free Cash Flow (FCF)</h1>
            
            <div class="highlight">
                <h3>Definición</h3>
                <p><strong>FCF:</strong> Efectivo disponible después de cubrir gastos operativos y de capital. Representa el dinero disponible para pagar a acreedores, accionistas y financiar crecimiento futuro.</p>
            </div>

            <div class="formula">
                FCF = Flujo de Caja Operativo - Gastos de Capital (CAPEX)
            </div>

            <div class="warning">
                <h3>Análisis de Tendencias</h3>
                <ul>
                    <li><strong>FCF estable o creciente:</strong> ✅ Señal positiva</li>
                    <li><strong>FCF decreciente:</strong> ⚠️ Puede romper tendencia alcista</li>
                    <li><strong>FCF negativo con ventas crecientes:</strong> 🔍 Evaluar si es por reinversión</li>
                </ul>
            </div>

            <div class="section-divider"></div>

            <h1>💲 Métricas de Valoración</h1>

            <h2>1. Price-to-Earnings Ratio (P/E)</h2>
            
            <div class="formula">
                P/E = Precio por Acción / Beneficio por Acción (EPS)
            </div>

            <table>
                <thead>
                    <tr>
                        <th>Rango P/E</th>
                        <th>Interpretación</th>
                        <th>Consideraciones</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>5-15</td>
                        <td>Posible infravaloración</td>
                        <td>Empresa madura o en declive</td>
                    </tr>
                    <tr>
                        <td>15-25</td>
                        <td>Valoración equilibrada</td>
                        <td>Empresas estables</td>
                    </tr>
                    <tr>
                        <td>25-50</td>
                        <td>Expectativas altas</td>
                        <td>Alto crecimiento esperado</td>
                    </tr>
                    <tr>
                        <td>&gt; 50</td>
                        <td>Especulación</td>
                        <td>Crecimiento explosivo o burbuja</td>
                    </tr>
                </tbody>
            </table>

            <h2>2. Price-to-Sales y Enterprise Value</h2>
            
            <div class="metrics-grid">
                <div class="metric-card">
                    <div class="metric-value">P/S Ratio</div>
                    <div class="metric-label">Cap. Mercado / Ingresos</div>
                </div>
                <div class="metric-card">
                    <div class="metric-value">EV/Revenue</div>
                    <div class="metric-label">Enterprise Value / Ingresos</div>
                </div>
                <div class="metric-card">
                    <div class="metric-value">EV/EBITDA</div>
                    <div class="metric-label">Múltiplo operativo popular</div>
                </div>
            </div>

            <div class="section-divider"></div>

            <h1>💎 Análisis de Dividendos</h1>

            <h2>Métricas Clave</h2>

            <div class="formula">
                Dividend Yield = Dividendo Anual / Precio por Acción × 100<br>
                Payout Ratio = Dividendos / Beneficio Neto × 100<br>
                Dividend Coverage = Beneficio Neto / Dividendos
            </div>

            <table>
                <thead>
                    <tr>
                        <th>Rango Yield</th>
                        <th>Tipo de Empresa</th>
                        <th>Características</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>0-2%</td>
                        <td>Crecimiento</td>
                        <td>Reinvierten beneficios</td>
                    </tr>
                    <tr>
                        <td>2-4%</td>
                        <td>Equilibradas</td>
                        <td>Yield saludable</td>
                    </tr>
                    <tr>
                        <td>4-6%</td>
                        <td>Dividendos altos</td>
                        <td>Verificar sostenibilidad</td>
                    </tr>
                    <tr>
                        <td>&gt; 6%</td>
                        <td>Muy altos</td>
                        <td>Posible trampa de dividendo</td>
                    </tr>
                </tbody>
            </table>

            <div class="warning">
                <h3>🚨 Trampas de Dividendos</h3>
                <ul>
                    <li>Yield muy alto por caída del precio</li>
                    <li>Payout ratio > 80%</li>
                    <li>FCF insuficiente para cubrir dividendos</li>
                    <li>Deuda creciente para mantener dividendos</li>
                </ul>
            </div>

            <div class="section-divider"></div>

            <h1>🎯 Análisis Cualitativo</h1>

            <h2>Ventajas Competitivas (Economic Moats)</h2>
            
            <div class="highlight">
                <h3>Definición</h3>
                <p><strong>Economic Moat:</strong> Ventaja competitiva sostenible que protege a la empresa de la competencia y le permite mantener márgenes superiores.</p>
            </div>

            <table>
                <thead>
                    <tr>
                        <th>Tipo de Moat</th>
                        <th>Descripción</th>
                        <th>Ejemplos</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>Network Effects</td>
                        <td>Valor aumenta con más usuarios</td>
                        <td>Facebook, Visa, eBay</td>
                    </tr>
                    <tr>
                        <td>Switching Costs</td>
                        <td>Alto costo de cambiar proveedor</td>
                        <td>Oracle, SAP, Adobe</td>
                    </tr>
                    <tr>
                        <td>Intangible Assets</td>
                        <td>Patentes, marcas, licencias</td>
                        <td>Coca-Cola, Pfizer, Disney</td>
                    </tr>
                    <tr>
                        <td>Cost Advantages</td>
                        <td>Economías de escala</td>
                        <td>Walmart, Amazon, Costco</td>
                    </tr>
                </tbody>
            </table>

            <h2>Calidad del Management</h2>
            
            <div class="info">
                <h3>Indicadores de Calidad</h3>
                <ul>
                    <li><strong>Track record:</strong> Historial de ejecución y cumplimiento</li>
                    <li><strong>Alineación de incentivos:</strong> Compensación vincul
