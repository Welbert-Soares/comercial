# Manual do Usuário - Dashboard Comercial Power BI

## 🎯 Bem-vindo ao Dashboard Comercial

Este manual irá guiá-lo através de todas as funcionalidades do Dashboard Comercial de Vendas, permitindo que você extraia insights valiosos para tomada de decisões estratégicas.

## 📖 Índice
1. [Primeiros Passos](#primeiros-passos)
2. [Navegação no Dashboard](#navegação-no-dashboard)
3. [Interpretação dos KPIs](#interpretação-dos-kpis)
4. [Funcionalidades Interativas](#funcionalidades-interativas)
5. [Casos de Uso Práticos](#casos-de-uso-práticos)
6. [Exportação e Compartilhamento](#exportação-e-compartilhamento)
7. [Troubleshooting](#troubleshooting)

## 🚀 Primeiros Passos

### Abrindo o Dashboard
1. **Localização**: Navegue até `comercial/dashboard/`
2. **Arquivo**: Clique duplo em `dashboard_comercial_1.pbix`
3. **Aguarde**: O Power BI Desktop iniciará automaticamente

### Interface Principal
```
┌─────────────────────────────────────────────────────────┐
│ [Menu] [Página 1] [Página 2] [Página 3] [Página 4]    │
├─────────────────────────────────────────────────────────┤
│                                                         │
│  📊 Visuais Principais    🎛️ Filtros e Segmentadores   │
│                                                         │
│  📈 Gráficos Detalhados   📋 Tabelas de Dados         │
│                                                         │
└─────────────────────────────────────────────────────────┘
```

## 🧭 Navegação no Dashboard

### Estrutura das Páginas

#### 📊 Página 1: Visão Executiva
**Objetivo**: Overview geral da performance comercial
**Principais Componentes**:
- 💰 **Card de Vendas Totais**: R$ 359,31 mil
- 🥧 **Gráfico Pizza**: Distribuição por segmento
- 📊 **Gráfico Barras**: Top fabricantes
- 📋 **Tabela KPIs**: Métricas consolidadas

**Como Usar**:
1. Observe o card principal para o valor total
2. Analise a distribuição por segmento no gráfico pizza
3. Identifique os principais fabricantes no gráfico de barras
4. Use a tabela para detalhes específicos

#### 📱 Página 2: Análise por Categoria
**Objetivo**: Performance detalhada por categoria de produto
**Principais Componentes**:
- 📊 **Gráfico Colunas**: Vendas por categoria
- 🔄 **Matriz Dinâmica**: Categoria vs Fabricante
- 📈 **Gráfico Tendência**: Performance temporal
- 🎯 **Segmentador**: Filtro por categoria

**Como Usar**:
1. Selecione uma categoria específica no segmentador
2. Observe a performance no gráfico de colunas
3. Analise a matriz para ver cruzamento categoria-fabricante
4. Use filtros para drill-down detalhado

#### 🏪 Página 3: Rede de Vendas
**Objetivo**: Análise da performance por ponto de venda
**Principais Componentes**:
- 🗺️ **Mapa Geográfico**: Distribuição das lojas
- 📊 **Gráfico Dispersão**: Performance vs Tamanho
- 📋 **Ranking Lojas**: Top performers
- 👥 **Análise Vendedores**: Performance individual

**Como Usar**:
1. Clique em pontos do mapa para ver detalhes da loja
2. Use o gráfico de dispersão para identificar outliers
3. Consulte o ranking para benchmark interno
4. Analise performance por vendedor

#### 🔍 Página 4: Análise de Influenciadores
**Objetivo**: Identificar fatores que impactam as vendas
**Principais Componentes**:
- 🎯 **Visual Influenciadores**: Fatores principais
- 📊 **Decomposição**: Análise de árvore
- 📈 **Correlações**: Relacionamentos entre variáveis
- 🔢 **Estatísticas**: Medidas avançadas

## 📊 Interpretação dos KPIs

### KPIs Principais e Significado

#### 💰 Valor Total de Vendas: R$ 359,31 mil
**O que significa**: Volume total comercializado no período
**Como interpretar**:
- ✅ **Verde**: Meta atingida ou superada
- 🟡 **Amarelo**: Próximo da meta (90-99%)
- 🔴 **Vermelho**: Abaixo da meta (<90%)

**Ações sugeridas**:
- Se verde: Manter estratégia atual
- Se amarelo: Acelerar ações de fechamento
- Se vermelho: Revisar estratégia urgentemente

#### 🏠 Segmento Doméstico: 71,47%
**O que significa**: Participação do mercado residencial
**Como interpretar**:
- **Alta concentração**: Risco de dependência
- **Oportunidade B2B**: Mercado corporativo sub-explorado
- **Estabilidade**: Base sólida de clientes

#### 🏭 Top Fabricantes
**Brastemp (25,82%)**: Líder absoluto
**Samsung (23,10%)**: Forte competidor
**Consul (16,42%)**: Terceiro colocado

**Como interpretar**:
- **Concentração moderada**: Não há monopólio
- **Competição saudável**: Equilíbrio entre marcas
- **Oportunidade**: Desenvolver marcas menores

### Semáforo de Performance

| Indicador | 🟢 Excelente | 🟡 Atenção | 🔴 Crítico |
|-----------|-------------|-------------|------------|
| **Vendas Totais** | >R$ 400k | R$ 300-400k | <R$ 300k |
| **Concentração Segmento** | 60-70% | 70-80% | >80% |
| **Diversificação Fabricantes** | HHI <0.2 | HHI 0.2-0.3 | HHI >0.3 |
| **Performance Categoria** | Todas >15% | 1-2 <15% | >2 <15% |

## 🎛️ Funcionalidades Interativas

### Filtros e Segmentadores

#### 📅 Filtro de Data
**Localização**: Canto superior direito
**Como usar**:
1. Clique no ícone de calendário
2. Selecione período desejado
3. Aplique para filtrar todos os visuais

**Tipos de seleção**:
- **Período específico**: Data início e fim
- **Últimos N dias**: Períodos relativos
- **Mês/Trimestre**: Agrupamentos temporais

#### 🏢 Filtro de Segmento
**Localização**: Lateral esquerda
**Opções disponíveis**:
- ✅ **Doméstico**: Selecionado por padrão
- ⬜ **Corporativo**: Click para incluir
- ⬜ **Industrial**: Click para incluir

**Como usar**:
1. Clique na caixa de seleção
2. Múltipla seleção permitida
3. Visual atualiza automaticamente

#### 📱 Filtro de Categoria
**Localização**: Parte superior central
**Como usar**:
1. Clique no dropdown
2. Selecione uma ou múltiplas categorias
3. Use "Ctrl+Click" para seleção múltipla

### Interações entre Visuais

#### Cross-Filtering (Filtro Cruzado)
**Como funciona**: Clicar em um visual filtra os outros
**Exemplo prático**:
1. Clique em "Eletrodomésticos" no gráfico de categoria
2. Todos os outros visuais mostram apenas dados de eletrodomésticos
3. Clique novamente para remover o filtro

#### Drill-Down (Aprofundamento)
**Como usar**:
1. Clique com botão direito no visual
2. Selecione "Drill down"
3. Navegue pelos níveis hierárquicos

**Exemplo**: Segmento → Categoria → Fabricante → Produto

#### Drill-Through (Navegação Direcionada)
**Como funciona**: Navegar para página específica com contexto
**Exemplo**:
1. Clique direito em um fabricante
2. Selecione "Drill through para Análise Detalhada"
3. Nova página abre com dados específicos do fabricante

## 💼 Casos de Uso Práticos

### Caso 1: "Quero entender por que as vendas de eletroportáteis estão baixas"

**Passo a passo**:
1. **Ir para Página 2** (Análise por Categoria)
2. **Selecionar "Eletroportáteis"** no segmentador
3. **Analisar performance** por fabricante
4. **Identificar oportunidades** de melhoria
5. **Comparar com outras categorias** (remover filtro)

**Insights esperados**:
- Participação de apenas 5,3%
- Potencial de crescimento identificado
- Fabricantes com melhor performance

### Caso 2: "Preciso avaliar a performance da loja SP8821"

**Passo a passo**:
1. **Ir para Página 3** (Rede de Vendas)
2. **Localizar loja SP8821** no mapa ou ranking
3. **Clicar na loja** para filtrar dados
4. **Analisar métricas específicas** da loja
5. **Comparar com benchmark** de outras lojas

**Insights esperados**:
- Ranking da loja vs outras
- Performance por categoria na loja
- Oportunidades de melhoria

### Caso 3: "Quero planejar estratégia para o segmento corporativo"

**Passo a passo**:
1. **Ir para Página 1** (Visão Executiva)
2. **Selecionar apenas "Corporativo"** no filtro de segmento
3. **Analisar distribuição por categoria**
4. **Identificar fabricantes principais**
5. **Ir para Página 4** para análise de influenciadores

**Insights esperados**:
- Participação atual: 25,03%
- Categorias preferenciais do B2B
- Fabricantes com melhor penetração

### Caso 4: "Preciso comparar performance entre vendedores"

**Passo a passo**:
1. **Ir para Página 3** (Rede de Vendas)
2. **Usar filtro de vendedor** ou visual específico
3. **Comparar métricas** entre André, Artur e Josias
4. **Analisar por categoria** de cada vendedor
5. **Identificar best practices** do melhor performer

## 📤 Exportação e Compartilhamento

### Exportando Relatórios

#### PDF Completo
1. **Menu Arquivo** → **Exportar** → **PDF**
2. **Configurar opções**:
   - Todas as páginas ou selecionadas
   - Qualidade de imagem
   - Orientação da página
3. **Salvar** na pasta `pdf/`

#### Excel com Dados
1. **Clique direito** em qualquer visual
2. **Exportar dados** → **Excel**
3. **Escolher nível** de detalhamento
4. **Salvar** arquivo gerado

#### PowerPoint
1. **Menu Arquivo** → **Exportar** → **PowerPoint**
2. **Configurar layout** dos slides
3. **Incluir anotações** se necessário

### Compartilhamento Seguro

#### Via Email
1. **Exportar** relatório em PDF
2. **Anexar** ao email corporativo
3. **Incluir contexto** da análise
4. **Definir audiência** apropriada

#### Workspace Corporativo
1. **Publicar** no Power BI Service
2. **Configurar permissões** por usuário
3. **Criar dashboard** público
4. **Agendar atualizações** automáticas

## ❓ Troubleshooting

### Problemas Comuns e Soluções

#### 🔴 "Dashboard não abre"
**Possíveis causas**:
- Power BI Desktop não instalado
- Arquivo corrompido
- Falta de permissões

**Soluções**:
1. Verificar instalação do Power BI Desktop
2. Tentar abrir backup na pasta `backup/`
3. Contatar administrador para permissões

#### 🟡 "Dados não aparecem nos visuais"
**Possíveis causas**:
- Filtros muito restritivos
- Problema na fonte de dados
- Relacionamentos quebrados

**Soluções**:
1. **Limpar todos os filtros**: Botão "Limpar filtros"
2. **Verificar conexão**: Menu "Página Inicial" → "Atualizar"
3. **Reabrir arquivo**: Fechar e abrir novamente

#### 🟠 "Performance lenta"
**Possíveis causas**:
- Muitos dados carregados
- Filtros complexos
- Hardware insuficiente

**Soluções**:
1. **Aplicar filtros básicos** primeiro
2. **Fechar outros programas** pesados
3. **Trabalhar página por página**

#### 🔵 "Valores não coincidem com expectativa"
**Possíveis causas**:
- Período incorreto selecionado
- Filtros não percebidos
- Interpretação incorreta

**Soluções**:
1. **Verificar filtros ativos** (indicador no topo)
2. **Confirmar período** selecionado
3. **Consultar documentação** de métricas

### Dicas de Performance

#### ⚡ Otimizando o Uso
1. **Aplique filtros antes** de analisar detalhes
2. **Use uma página por vez** para análises profundas
3. **Feche visuais desnecessários** quando não usar
4. **Atualize dados apenas** quando necessário

#### 🎯 Melhores Práticas
1. **Comece sempre pela Visão Executiva**
2. **Use filtros progressivos** (do geral para o específico)
3. **Salve análises importantes** em PDF
4. **Documente insights** para reuniões

## 📞 Suporte e Contato

### Para Dúvidas Técnicas
- **Arquivo**: Consulte `especificacoes_tecnicas.md`
- **Problemas de Dados**: Verificar `Dados_Comerciais.xlsx`
- **Performance**: Revisar configurações do sistema

### Para Dúvidas de Negócio
- **Interpretação de KPIs**: Consulte `analise_detalhada.md`
- **Cases de Uso**: Consulte `casos_uso.md`
- **Estratégias**: Agende reunião com time comercial

### Melhorias e Sugestões
- **Novas funcionalidades**: Documente necessidade
- **Dados adicionais**: Especifique fonte e formato
- **Visuais customizados**: Descreva requisitos

---

**💡 Dica Final**: Este dashboard é uma ferramenta poderosa, mas seu valor está na interpretação correta dos dados. Use-o como base para discussões estratégicas e tomada de decisões fundamentadas em dados reais.
