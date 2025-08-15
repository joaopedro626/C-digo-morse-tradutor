# C-digo-morse-tradutor
<!DOCTYPE html>
<html lang="pt">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Presidente do Burundi: Destino de Uma Nação</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #2c5530, #1a3d1f);
            color: white;
            min-height: 100vh;
            overflow-x: hidden;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }
        
        .header {
            text-align: center;
            margin-bottom: 30px;
            background: rgba(0,0,0,0.3);
            padding: 20px;
            border-radius: 15px;
            border: 2px solid #d4af37;
        }
        
        .header h1 {
            font-size: 2.5em;
            color: #d4af37;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.5);
            margin-bottom: 10px;
        }
        
        .stats-panel {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 15px;
            margin-bottom: 30px;
        }
        
        .stat-card {
            background: rgba(0,0,0,0.4);
            padding: 15px;
            border-radius: 10px;
            border-left: 4px solid #d4af37;
            backdrop-filter: blur(10px);
        }
        
        .stat-title {
            font-size: 0.9em;
            color: #ccc;
            margin-bottom: 5px;
        }
        
        .stat-value {
            font-size: 1.8em;
            font-weight: bold;
            color: #fff;
        }
        
        .stat-bar {
            width: 100%;
            height: 8px;
            background: rgba(255,255,255,0.2);
            border-radius: 4px;
            margin-top: 8px;
            overflow: hidden;
        }
        
        .stat-fill {
            height: 100%;
            border-radius: 4px;
            transition: width 0.5s ease;
        }
        
        .game-area {
            background: rgba(0,0,0,0.3);
            border-radius: 15px;
            padding: 25px;
            margin-bottom: 20px;
        }
        
        .scenario {
            background: linear-gradient(135deg, #1a3d1f, #2c5530);
            border: 2px solid #d4af37;
            border-radius: 12px;
            padding: 20px;
            margin-bottom: 20px;
            box-shadow: 0 8px 32px rgba(0,0,0,0.3);
        }
        
        .scenario h3 {
            color: #d4af37;
            font-size: 1.5em;
            margin-bottom: 15px;
            text-align: center;
        }
        
        .scenario p {
            line-height: 1.6;
            margin-bottom: 20px;
            font-size: 1.1em;
        }
        
        .choices {
            display: grid;
            gap: 12px;
        }
        
        .choice-btn {
            background: linear-gradient(135deg, #2c5530, #1a3d1f);
            border: 2px solid #d4af37;
            color: white;
            padding: 15px 20px;
            border-radius: 10px;
            cursor: pointer;
            font-size: 1em;
            transition: all 0.3s ease;
            text-align: left;
        }
        
        .choice-btn:hover {
            background: linear-gradient(135deg, #3a6b3f, #225829);
            transform: translateY(-2px);
            box-shadow: 0 6px 20px rgba(212, 175, 55, 0.3);
        }
        
        .result {
            background: rgba(212, 175, 55, 0.1);
            border: 1px solid #d4af37;
            border-radius: 10px;
            padding: 15px;
            margin-top: 15px;
            font-style: italic;
        }
        
        .year-counter {
            text-align: center;
            font-size: 1.5em;
            color: #d4af37;
            margin-bottom: 20px;
            font-weight: bold;
        }
        
        .game-over {
            background: linear-gradient(135deg, #8B0000, #4B0000);
            border: 2px solid #ff6b6b;
            text-align: center;
            padding: 30px;
            border-radius: 15px;
        }
        
        .victory {
            background: linear-gradient(135deg, #006400, #228B22);
            border: 2px solid #90EE90;
        }
        
        .restart-btn {
            background: #d4af37;
            color: #1a3d1f;
            border: none;
            padding: 12px 25px;
            border-radius: 8px;
            font-size: 1.1em;
            font-weight: bold;
            cursor: pointer;
            margin-top: 15px;
            transition: all 0.3s ease;
        }
        
        .restart-btn:hover {
            background: #b8941f;
            transform: scale(1.05);
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <h1>🏛️ Presidente do Burundi</h1>
            <p>Destino de Uma Nação em Suas Mãos</p>
        </div>
        
        <div class="year-counter" id="yearCounter">Ano 1 da Presidência</div>
        
        <div class="stats-panel">
            <div class="stat-card">
                <div class="stat-title">População Abaixo da Pobreza</div>
                <div class="stat-value" id="poverty">72%</div>
                <div class="stat-bar">
                    <div class="stat-fill" id="povertyBar" style="width: 72%; background: #ff6b6b;"></div>
                </div>
            </div>
            
            <div class="stat-card">
                <div class="stat-title">PIB (Bilhões USD)</div>
                <div class="stat-value" id="gdp">$2.6</div>
                <div class="stat-bar">
                    <div class="stat-fill" id="gdpBar" style="width: 26%; background: #4ecdc4;"></div>
                </div>
            </div>
            
            <div class="stat-card">
                <div class="stat-title">Inflação</div>
                <div class="stat-value" id="inflation">22%</div>
                <div class="stat-bar">
                    <div class="stat-fill" id="inflationBar" style="width: 44%; background: #ffe66d;"></div>
                </div>
            </div>
            
            <div class="stat-card">
                <div class="stat-title">Estabilidade Política</div>
                <div class="stat-value" id="stability">45%</div>
                <div class="stat-bar">
                    <div class="stat-fill" id="stabilityBar" style="width: 45%; background: #a8e6cf;"></div>
                </div>
            </div>
            
            <div class="stat-card">
                <div class="stat-title">Saúde Pública</div>
                <div class="stat-value" id="health">35%</div>
                <div class="stat-bar">
                    <div class="stat-fill" id="healthBar" style="width: 35%; background: #ff8b94;"></div>
                </div>
            </div>
            
            <div class="stat-card">
                <div class="stat-title">Educação</div>
                <div class="stat-value" id="education">40%</div>
                <div class="stat-bar">
                    <div class="stat-fill" id="educationBar" style="width: 40%; background: #b4a7d6;"></div>
                </div>
            </div>
        </div>
        
        <div class="game-area" id="gameArea">
            <!-- Cenários serão inseridos aqui -->
        </div>
    </div>

    <script>
        let gameState = {
            year: 1,
            poverty: 72,
            gdp: 2.6,
            inflation: 22,
            stability: 45,
            health: 35,
            education: 40,
            gameOver: false,
            currentScenario: 0
        };

        const scenarios = [
            {
                title: "Crise Alimentar Iminente",
                description: "Devido às mudanças climáticas e à dependência da agricultura (90% da população), o Burundi enfrenta uma grave crise alimentar. 80% da população vive com menos de $2,15 por dia. Refugiados da RDC aumentam a pressão sobre os recursos. Como você responderá?",
                choices: [
                    {
                        text: "Investir em agricultura moderna e irrigação (custa $200M, mas pode reduzir pobreza)",
                        effects: { poverty: -8, gdp: 0.3, inflation: 2, stability: 5, health: 3 }
                    },
                    {
                        text: "Buscar ajuda internacional massiva e distribuir alimentos (dependência externa)",
                        effects: { poverty: -5, gdp: -0.1, inflation: 1, stability: -3, health: 2 }
                    },
                    {
                        text: "Focar na mineração para gerar receita rápida (ignora agricultura)",
                        effects: { poverty: 2, gdp: 0.4, inflation: -1, stability: -5, health: -2 }
                    }
                ]
            },
            {
                title: "Pressão da Oposição Política",
                description: "Partidos de oposição acusam seu governo de autoritarismo e pedem eleições antecipadas. Manifestações crescem nas ruas de Bujumbura. A imprensa internacional critica suas políticas. Como responder?",
                choices: [
                    {
                        text: "Abrir diálogo democrático e convocar mesa de negociação nacional",
                        effects: { poverty: 0, gdp: 0.1, inflation: 0, stability: 12, health: 1, education: 2 }
                    },
                    {
                        text: "Implementar reformas constitucionais para maior transparência",
                        effects: { poverty: -1, gdp: 0.05, inflation: 1, stability: 8, health: 0, education: 3 }
                    },
                    {
                        text: "Reprimir manifestações e restringir atividades da oposição",
                        effects: { poverty: 1, gdp: -0.2, inflation: 2, stability: -18, health: -2, education: -3 }
                    }
                ]
            },
            {
                title: "Tensões Étnicas Crescentes",
                description: "Historicamente, o Burundi sofreu com conflitos entre hutus e tutsis. Tensões estão aumentando devido à pobreza extrema e competição por recursos escassos. Protestos começam a eclodir. Como agir?",
                choices: [
                    {
                        text: "Criar programas de reconciliação nacional e cotas étnicas equilibradas",
                        effects: { poverty: -1, gdp: 0.1, inflation: 0, stability: 15, health: 2, education: 3 }
                    },
                    {
                        text: "Usar força policial para manter ordem e reprimir protestos",
                        effects: { poverty: 0, gdp: -0.1, inflation: 1, stability: -15, health: -5 }
                    },
                    {
                        text: "Focar apenas no desenvolvimento econômico, ignorando questões étnicas",
                        effects: { poverty: -2, gdp: 0.2, inflation: -1, stability: -8, health: 1 }
                    }
                ]
            },
            {
                title: "Corrupção no Governo",
                description: "Escândalos de corrupção envolvendo ministros do seu governo vieram à tona. Recursos destinados a projetos sociais foram desviados. A população perde confiança na administração. Como agir?",
                choices: [
                    {
                        text: "Lançar investigação independente e demitir todos os envolvidos",
                        effects: { poverty: -2, gdp: 0.1, inflation: 0, stability: 20, health: 1, education: 2 }
                    },
                    {
                        text: "Criar novo sistema de auditoria e transparência governamental",
                        effects: { poverty: -1, gdp: 0.15, inflation: -1, stability: 15, health: 2, education: 4 }
                    },
                    {
                        text: "Minimizar o escândalo e proteger aliados políticos",
                        effects: { poverty: 3, gdp: -0.2, inflation: 2, stability: -25, health: -1, education: -2 }
                    }
                ]
            },
            {
                title: "Relações Internacionais Tensas",
                description: "A União Africana e países vizinhos criticam políticas internas do Burundi. Ameaças de sanções econômicas pairam sobre o país. Refugiados burundianos em países vizinhos criam tensões diplomáticas.",
                choices: [
                    {
                        text: "Aceitar mediação internacional e implementar reformas democráticas",
                        effects: { poverty: -3, gdp: 0.3, inflation: -2, stability: 10, health: 3, education: 5 }
                    },
                    {
                        text: "Buscar novos parceiros (China, Rússia) e ignorar pressão ocidental",
                        effects: { poverty: -1, gdp: 0.4, inflation: -1, stability: -5, health: 1, education: 2 }
                    },
                    {
                        text: "Adotar postura isolacionista e focar apenas em questões internas",
                        effects: { poverty: 2, gdp: -0.3, inflation: 3, stability: -8, health: -2, education: -1 }
                    }
                ]
            },
            {
                title: "Crise do Sistema de Saúde",
                description: "Com apenas 35% de cobertura de saúde adequada, uma epidemia de malária se espalha. Hospitais estão superlotados e faltam medicamentos básicos. A situação é crítica.",
                choices: [
                    {
                        text: "Investir massivamente em infraestrutura de saúde e formar médicos",
                        effects: { poverty: -2, gdp: -0.1, inflation: 1, stability: 8, health: 20, education: 2 }
                    },
                    {
                        text: "Focar em medicina preventiva e saneamento básico (mais barato)",
                        effects: { poverty: -3, gdp: 0.05, inflation: 0, stability: 5, health: 12, education: 1 }
                    },
                    {
                        text: "Privatizar o sistema de saúde para atrair investimento estrangeiro",
                        effects: { poverty: 3, gdp: 0.15, inflation: -1, stability: -10, health: -5 }
                    }
                ]
            },
            {
                title: "Pressão dos Militares",
                description: "Generais das Forças Armadas estão insatisfeitos com cortes no orçamento militar. Rumores de golpe circulam. Eles exigem maior participação nas decisões políticas e aumento de salários.",
                choices: [
                    {
                        text: "Negociar com militares e aumentar orçamento de defesa",
                        effects: { poverty: 1, gdp: -0.1, inflation: 1, stability: 8, health: -1, education: -2 }
                    },
                    {
                        text: "Reformar comando militar e promover lealdade institucional",
                        effects: { poverty: 0, gdp: 0.05, inflation: 0, stability: 12, health: 0, education: 1 }
                    },
                    {
                        text: "Confrontar militares e reduzir sua influência política",
                        effects: { poverty: -1, gdp: 0.1, inflation: -1, stability: -20, health: 1, education: 2 }
                    }
                ]
            },
            {
                title: "Educação em Colapso",
                description: "Com 40% de qualidade educacional, muitas crianças não frequentam escola. 41.5% da população tem menos de 15 anos. Sem educação, o futuro do país está comprometido.",
                choices: [
                    {
                        text: "Construir escolas e treinar professores massivamente",
                        effects: { poverty: -4, gdp: 0.2, inflation: 1, stability: 10, health: 2, education: 25 }
                    },
                    {
                        text: "Focar em educação técnica para agricultura e mineração",
                        effects: { poverty: -6, gdp: 0.3, inflation: 0, stability: 5, health: 1, education: 15 }
                    },
                    {
                        text: "Implementar educação digital básica (mais barata e eficiente)",
                        effects: { poverty: -2, gdp: 0.1, inflation: 0, stability: 3, health: 0, education: 18 }
                    }
                ]
            },
            {
                title: "Disputa por Recursos Naturais",
                description: "Descobertas de depósitos minerais significativos atraem interesse de empresas multinacionais. Comunidades locais protestam contra exploração. Há potencial tanto para desenvolvimento quanto para conflitos.",
                choices: [
                    {
                        text: "Criar empresa estatal de mineração com participação das comunidades",
                        effects: { poverty: -8, gdp: 0.8, inflation: -2, stability: 12, health: -1, education: 3 }
                    },
                    {
                        text: "Aceitar parcerias internacionais com regulamentação ambiental",
                        effects: { poverty: -10, gdp: 1.2, inflation: -5, stability: 5, health: -3, education: 5 }
                    },
                    {
                        text: "Suspender exploração até resolver conflitos com comunidades",
                        effects: { poverty: 0, gdp: -0.1, inflation: 1, stability: 8, health: 2, education: 1 }
                    }
                ]
            },
            {
                title: "Crise de Refugiados Internos",
                description: "Conflitos regionais e mudanças climáticas criam grande número de deslocados internos. Campos de refugiados estão superlotados. A situação humanitária é crítica e gera tensões sociais.",
                choices: [
                    {
                        text: "Criar programa de reassentamento e integração nacional",
                        effects: { poverty: -3, gdp: 0.1, inflation: 2, stability: 15, health: 5, education: 3 }
                    },
                    {
                        text: "Buscar apoio internacional para campos de refugiados",
                        effects: { poverty: -1, gdp: 0.05, inflation: 1, stability: 8, health: 8, education: 2 }
                    },
                    {
                        text: "Implementar políticas de retorno forçado às regiões de origem",
                        effects: { poverty: 2, gdp: -0.05, inflation: 0, stability: -15, health: -5, education: -2 }
                    }
                ]
            }
        ];

        function updateStats() {
            document.getElementById('poverty').textContent = Math.max(0, Math.min(100, gameState.poverty)) + '%';
            document.getElementById('gdp').textContent = '$' + gameState.gdp.toFixed(1);
            document.getElementById('inflation').textContent = Math.max(0, gameState.inflation) + '%';
            document.getElementById('stability').textContent = Math.max(0, Math.min(100, gameState.stability)) + '%';
            document.getElementById('health').textContent = Math.max(0, Math.min(100, gameState.health)) + '%';
            document.getElementById('education').textContent = Math.max(0, Math.min(100, gameState.education)) + '%';
            
            // Update bars
            document.getElementById('povertyBar').style.width = Math.max(0, Math.min(100, gameState.poverty)) + '%';
            document.getElementById('gdpBar').style.width = Math.min(100, (gameState.gdp / 10) * 100) + '%';
            document.getElementById('inflationBar').style.width = Math.min(100, (gameState.inflation / 50
