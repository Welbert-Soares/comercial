# Dashboard Comercial - Análise de Performance de Vendas

[![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=Power%20BI&logoColor=black)](https://powerbi.microsoft.com/)
[![Status](https://img.shields.io/badge/Status-Em%20Produção-green?style=for-the-badge)](https://github.com/)
[![Versão](https://img.shields.io/badge/Versão-1.0-blue?style=for-the-badge)](https://github.com/)

## 📊 Visão Geral do Projeto

Este projeto apresenta uma solução completa de Business Intelligence para análise de performance comercial, desenvolvida em Power BI. O dashboard oferece insights estratégicos sobre vendas, segmentação de mercado, performance de fabricantes e eficiência da rede de pontos de venda.

### 🎯 Objetivos Principais
- Monitoramento em tempo real da performance comercial
- Análise multidimensional de vendas por segmento, categoria e fabricante
- Identificação de oportunidades de crescimento e otimização
- Suporte à tomada de decisões estratégicas baseada em dados

### 📈 Principais Métricas
| KPI | Valor | Participação |
|-----|-------|--------------|
| **Valor Total de Vendas** | R$ 359,31 mil | 100% |
| **Segmento Doméstico** | R$ 256,8 mil | 71,47% |
| **Segmento Corporativo** | R$ 89,95 mil | 25,03% |
| **Segmento Industrial** | R$ 12,56 mil | 3,49% |

## 🗂️ Estrutura do Projeto

```
comercial/
├── 📁 .vscode/                 # Configurações VS Code
│   └── tasks.json             # Tarefas automatizadas
├── 📁 csv/                     # Dados fonte
│   └── Dados_Comerciais.xlsx  # Base de dados principal
├── 📁 dashboard/               # Arquivos Power BI
│   ├── dashboard_comercial_1.pbix # Dashboard principal
│   └── backup/                # Backups automáticos
├── 📁 doc/                     # Documentação completa
│   ├── analise_detalhada.md   # Análise completa dos resultados
│   ├── especificacoes_tecnicas.md # Documentação técnica
│   ├── manual_usuario.md      # Manual do usuário
│   ├── casos_uso.md           # Cases de negócio
│   └── guia_implantacao.md    # Guia de deployment
├── 📁 pdf/                     # Relatórios exportados
│   └── dashboard_comercial_1.pdf
├── 📁 public/                  # Screenshots e imagens
│   ├── resumo_vendas.png      # Visão executiva
│   ├── principais_influenciadores.png # Análise de fatores
│   └── [outros screenshots]   # Demais capturas
├── 📁 templates/               # Templates de relatórios
│   └── relatorio_executivo_template.md
├── 📁 releases/                # Packages de versões
├── 📁 data/                    # Dados processados (futuro)
├── .gitignore                  # Configuração Git
├── CHANGELOG.md                # Histórico de versões
├── LICENSE.md                  # Termos de uso
├── project.json                # Metadados do projeto
├── dashboard-comercial.code-workspace # Workspace VS Code
└── README.md                   # Este arquivo
```

## 🚀 Quick Start

### Pré-requisitos
- Microsoft Power BI Desktop (versão mais recente)
- Microsoft Excel (para visualização dos dados fonte)
- Acesso aos dados comerciais da empresa

### Como Usar
1. **Abrir o Dashboard**
   ```bash
   # Navegue até a pasta do projeto
   cd comercial/dashboard/
   # Abra o arquivo Power BI
   start dashboard_comercial_1.pbix
   ```

2. **Atualizar Dados**
   - Abra o Power BI Desktop
   - Vá em "Página Inicial" > "Atualizar"
   - Os dados serão atualizados automaticamente

3. **Exportar Relatórios**
   - Arquivo > Exportar > PDF
   - Salve na pasta `pdf/`

## 📊 Principais Insights

### 🎯 Performance por Segmento
- **Doméstico**: Líder absoluto com 71,47% das vendas
- **Corporativo**: 25,03% - Oportunidade de expansão B2B
- **Industrial**: 3,49% - Nicho especializado com potencial

### 🏭 Análise de Fabricantes
- **Brastemp**: Líder com R$ 92,786 mil (25,82%)
- **Samsung**: R$ 83 mil - Segundo colocado
- **Consul**: R$ 59 mil - Terceiro lugar
- **Concentração**: Top 3 representam ~65% das vendas

### 📱 Performance por Categoria
1. **Eletrodomésticos**: R$ 193,32 mil (53,8%)
2. **Celulares**: R$ 98,60 mil (27,4%)
3. **Eletrônicos**: R$ 48,33 mil (13,5%)
4. **Eletroportáteis**: R$ 19,06 mil (5,3%)

## 🔍 Análises Disponíveis

### 📈 Dashboards Principais
- **Visão Executiva**: KPIs consolidados e tendências
- **Análise por Segmento**: Performance detalhada por mercado
- **Performance de Produtos**: Análise por categoria e fabricante
- **Rede de Vendas**: Eficiência por ponto de venda
- **Análise Geográfica**: Distribuição regional das vendas

### 🎛️ Filtros Interativos
- Período (data)
- Segmento de mercado
- Categoria de produto
- Fabricante
- Ponto de venda
- Vendedor
- Região geográfica

## 🎯 Cases de Negócio

### Case 1: Otimização do Mix de Produtos
**Problema**: Eletroportáteis representa apenas 5,3% das vendas
**Solução**: Estratégia focada em aumento de participação
**Impacto Estimado**: +15% na categoria

### Case 2: Expansão B2B
**Problema**: Segmentos corporativo e industrial somam apenas 28,52%
**Solução**: Desenvolvimento de estratégias B2B específicas
**Impacto Estimado**: +25% em vendas corporativas

### Case 3: Diversificação de Fornecedores
**Problema**: Dependência excessiva dos top 3 fabricantes
**Solução**: Estratégia de diversificação de portfólio
**Impacto Estimado**: Redução de 20% no risco de concentração

## 📚 Documentação Detalhada

- **[Análise Detalhada](doc/analise_detalhada.md)**: Insights completos e recommendations
- **[Especificações Técnicas](doc/especificacoes_tecnicas.md)**: Documentação técnica do Power BI
- **[Manual do Usuário](doc/manual_usuario.md)**: Guia completo de uso
- **[Cases de Uso](doc/casos_uso.md)**: Cenários de aplicação prática

## 🔄 Atualizações e Versioning

| Versão | Data | Descrição |
|--------|------|-----------|
| v1.0 | Jun/2025 | Versão inicial com análises principais |
| v1.1 | Em desenvolvimento | Análise temporal e tendências |

## 🤝 Contribuições

Para sugestões de melhorias ou reportar issues:
1. Documente o problema ou sugestão
2. Inclua screenshots se relevante
3. Descreva o comportamento esperado

## 📞 Contato e Suporte

- **Desenvolvedor**: Welbert
- **Projeto**: Dashboard Comercial Power BI
- **Status**: Em Produção
- **Última Atualização**: Junho 2025

## 📄 Licença

Este projeto é propriedade da empresa e destinado ao uso interno para análises comerciais e tomada de decisões estratégicas.

---

**📊 Dashboard em ação**: Transformando dados em insights para impulsionar o crescimento comercial.
