# Especificações Técnicas - Dashboard Comercial Power BI

## 🏗️ Arquitetura do Sistema

### Visão Geral da Arquitetura
```
Dados Fonte (Excel) → Power BI Desktop → Dashboard Interativo → Relatórios PDF
     ↓                    ↓                    ↓                    ↓
Dados_Comerciais.xlsx → dashboard_comercial_1.pbix → Visualizações → Exports
```

## 📋 Especificações Técnicas

### Requisitos do Sistema
| Componente | Especificação Mínima | Recomendado |
|------------|----------------------|-------------|
| **Power BI Desktop** | Versão 2.0+ | Versão mais recente |
| **RAM** | 4 GB | 8 GB+ |
| **Processador** | Intel i5 / AMD Ryzen 5 | Intel i7 / AMD Ryzen 7 |
| **Armazenamento** | 2 GB livres | 5 GB+ livres |
| **Sistema Operacional** | Windows 10 | Windows 11 |

### Tecnologias Utilizadas
- **Microsoft Power BI Desktop** - Ferramenta principal de desenvolvimento
- **DAX (Data Analysis Expressions)** - Linguagem para medidas calculadas
- **Power Query** - ETL e transformação de dados
- **Microsoft Excel** - Fonte de dados primária

## 📊 Estrutura de Dados

### Fonte de Dados Principal
**Arquivo**: `Dados_Comerciais.xlsx`
**Localização**: `./csv/Dados_Comerciais.xlsx`

#### Schema de Dados Identificado
```sql
Vendas {
    ValorVenda: Currency
    Segmento: Text ["Doméstico", "Corporativo", "Industrial"]
    Categoria: Text ["Eletrodomésticos", "Celulares", "Eletrônicos", "Eletroportáteis"]
    Fabricante: Text
    PontoVenda: Text
    Vendedor: Text
    Data: Date (inferido)
    Regiao: Text (inferido)
}
```

#### Relacionamentos de Dados
- **Fato Principal**: Tabela de Vendas
- **Dimensões**:
  - DimSegmento (Doméstico, Corporativo, Industrial)
  - DimCategoria (Eletrodomésticos, Celulares, Eletrônicos, Eletroportáteis)
  - DimFabricante (Brastemp, Samsung, Consul, etc.)
  - DimPontoVenda (A9990, A9991, B7659, etc.)
  - DimVendedor (André Pereira, Artur Moreira, Josias Silva)

## 🧮 Medidas DAX Implementadas

### Medidas Principais
```dax
// Medida: Total Valor Venda
Total Valor Venda = SUM(Vendas[ValorVenda])

// Medida: Percentual por Segmento
Percentual Segmento = 
DIVIDE(
    [Total Valor Venda],
    CALCULATE([Total Valor Venda], ALL(Vendas[Segmento])),
    0
) * 100

// Medida: Média de Valor por Venda
Média ValorVenda = AVERAGE(Vendas[ValorVenda])

// Medida: Ranking de Fabricantes
Ranking Fabricante = 
RANKX(
    ALL(Vendas[Fabricante]),
    [Total Valor Venda],
    ,
    DESC
)

// Medida: Variação Percentual vs Líder
Variação vs Líder = 
VAR LiderVendas = 
    CALCULATE(
        [Total Valor Venda],
        FILTER(
            ALL(Vendas[Fabricante]),
            [Ranking Fabricante] = 1
        )
    )
VAR VendasAtual = [Total Valor Venda]
RETURN
    DIVIDE(LiderVendas - VendasAtual, VendasAtual, 0) * 100
```

### Medidas de Análise Avançada
```dax
// Medida: Concentração de Mercado (HHI)
Indice_HHI_Segmento = 
SUMX(
    VALUES(Vendas[Segmento]),
    POWER([Percentual Segmento] / 100, 2)
)

// Medida: Ticket Médio por Segmento
Ticket Médio Segmento = 
DIVIDE(
    [Total Valor Venda],
    COUNTROWS(Vendas),
    0
)

// Medida: Performance Relativa
Performance Relativa = 
VAR MediaGeral = CALCULATE([Média ValorVenda], ALL())
VAR MediaSegmento = [Média ValorVenda]
RETURN
    DIVIDE(MediaSegmento, MediaGeral, 0) - 1

// Medida: Top 3 Concentração
Top3_Concentração = 
SUMX(
    TOPN(3, VALUES(Vendas[Fabricante]), [Total Valor Venda], DESC),
    [Percentual por Fabricante]
)
```

## 📈 Estrutura de Visualizações

### Páginas do Dashboard

#### 1. Página Executiva
**Componentes:**
- Card: Total de Vendas
- Gráfico de Pizza: Vendas por Segmento
- Gráfico de Barras: Top Fabricantes
- Tabela: KPIs Principais
- Filtros: Data, Segmento

**Medidas Utilizadas:**
- `Total Valor Venda`
- `Percentual Segmento`
- `Ranking Fabricante`

#### 2. Análise por Categoria
**Componentes:**
- Gráfico de Colunas: Vendas por Categoria
- Gráfico de Barras Horizontais: Categoria vs Fabricante
- Matriz: Performance Detalhada
- Segmentador: Categoria

**Medidas Utilizadas:**
- `Total Valor Venda`
- `Performance Relativa`
- `Média ValorVenda`

#### 3. Rede de Vendas
**Componentes:**
- Mapa: Distribuição Geográfica
- Gráfico de Dispersão: Performance por Loja
- Tabela: Ranking de Pontos de Venda
- Filtro: Vendedor

#### 4. Análise de Influenciadores
**Componentes:**
- Visual de Influenciadores Principais
- Gráfico de Decomposição
- Análise de Correlação

## 🔧 Configurações Técnicas

### Configurações de Atualização de Dados
```json
{
  "dataRefresh": {
    "mode": "Manual",
    "frequency": "Daily",
    "schedule": "08:00",
    "timezone": "America/Sao_Paulo"
  }
}
```

### Configurações de Performance
- **Modo de Armazenamento**: Import
- **Compressão**: Ativada
- **Agregações**: Configuradas para grandes volumes
- **Cache**: Otimizado para consultas frequentes

### Configurações de Segurança
- **RLS (Row Level Security)**: Configurável por vendedor/região
- **Exportação**: Controlada por perfil de usuário
- **Compartilhamento**: Workspace específico

## 🎨 Paleta de Cores e Temas

### Paleta Principal
```css
Primary Colors:
- Azul Principal: #004B87
- Azul Secundário: #0078D4
- Verde Sucesso: #107C10
- Laranja Alerta: #FF8C00
- Vermelho Crítico: #D13438

Background Colors:
- Fundo Principal: #FFFFFF
- Fundo Secundário: #F8F9FA
- Bordas: #E1E5E9
```

### Formatação de Números
- **Moeda**: R$ #,##0.00
- **Percentual**: 0.00%
- **Números Inteiros**: #,##0
- **Decimais**: #,##0.00

## 🔄 ETL e Transformações

### Power Query - Transformações Aplicadas
```m
// Exemplo de transformação básica
let
    Source = Excel.Workbook(File.Contents("Dados_Comerciais.xlsx")),
    Navigation = Source{[Item="Vendas",Kind="Sheet"]}[Data],
    PromotedHeaders = Table.PromoteHeaders(Navigation),
    ChangedTypes = Table.TransformColumnTypes(PromotedHeaders,{
        {"ValorVenda", Currency.Type},
        {"Data", type date},
        {"Segmento", type text},
        {"Categoria", type text},
        {"Fabricante", type text}
    }),
    // Limpeza de dados
    FilteredRows = Table.SelectRows(ChangedTypes, each [ValorVenda] > 0),
    TrimmedText = Table.TransformColumns(FilteredRows,{
        {"Segmento", Text.Trim},
        {"Categoria", Text.Trim},
        {"Fabricante", Text.Trim}
    })
in
    TrimmedText
```

### Validações de Qualidade de Dados
- **Valores Nulos**: Tratamento automático
- **Duplicatas**: Identificação e remoção
- **Outliers**: Análise estatística
- **Consistência**: Validação de categorias

## 📊 Modelo de Dados Detalhado

### Tabela Fato: Vendas
| Coluna | Tipo | Descrição | Exemplo |
|--------|------|-----------|---------|
| `ID_Venda` | Integer | Identificador único | 1001 |
| `ValorVenda` | Currency | Valor da venda | R$ 2.500,00 |
| `Data` | Date | Data da transação | 2025-06-01 |
| `ID_Segmento` | Integer | FK para DimSegmento | 1 |
| `ID_Categoria` | Integer | FK para DimCategoria | 2 |
| `ID_Fabricante` | Integer | FK para DimFabricante | 5 |
| `ID_PontoVenda` | Integer | FK para DimPontoVenda | 12 |
| `ID_Vendedor` | Integer | FK para DimVendedor | 3 |

### Tabelas Dimensão

#### DimSegmento
| ID | Segmento | Descrição |
|----|----------|-----------|
| 1 | Doméstico | Mercado residencial |
| 2 | Corporativo | Empresas privadas |
| 3 | Industrial | Setor industrial |

#### DimCategoria
| ID | Categoria | Grupo | Margem_Típica |
|----|-----------|-------|---------------|
| 1 | Eletrodomésticos | Linha Branca | 25% |
| 2 | Celulares | Mobile | 15% |
| 3 | Eletrônicos | Tech | 20% |
| 4 | Eletroportáteis | Pequenos | 30% |

## 🔍 Monitoramento e Manutenção

### Métricas de Performance do Dashboard
- **Tempo de Carregamento**: < 5 segundos
- **Tempo de Atualização**: < 2 minutos
- **Tamanho do Arquivo**: < 50 MB
- **Consultas Simultâneas**: Até 10 usuários

### Logs e Auditoria
- **Log de Atualizações**: Registro automático
- **Log de Acesso**: Rastreamento de usuários
- **Log de Erros**: Identificação de problemas
- **Versionamento**: Controle de mudanças

### Plano de Backup
```
Backup Schedule:
├── Daily: Arquivo .pbix → OneDrive
├── Weekly: Export completo → SharePoint
├── Monthly: Archive → Storage permanente
└── Quarterly: Documentação → Git repository
```

## 🛠️ Troubleshooting

### Problemas Comuns

#### 1. Erro de Atualização de Dados
**Sintoma**: Falha na atualização automática
**Causa**: Arquivo Excel bloqueado ou movido
**Solução**:
```
1. Verificar se o arquivo está acessível
2. Fechar Excel se estiver aberto
3. Reconfigurar fonte de dados se necessário
```

#### 2. Performance Lenta
**Sintoma**: Dashboard carrega devagar
**Causa**: Volume de dados ou consultas complexas
**Solução**:
```
1. Implementar agregações
2. Otimizar medidas DAX
3. Reduzir número de visuais por página
```

#### 3. Visualizações em Branco
**Sintoma**: Gráficos não exibem dados
**Causa**: Filtros muito restritivos ou relacionamentos incorretos
**Solução**:
```
1. Verificar filtros aplicados
2. Validar relacionamentos entre tabelas
3. Conferir medidas DAX
```

## 📋 Checklist de Deployment

### Pré-Deployment
- [ ] Dados fonte validados
- [ ] Medidas DAX testadas
- [ ] Performance otimizada
- [ ] Visualizações formatadas
- [ ] Filtros configurados

### Deployment
- [ ] Arquivo .pbix salvo na pasta correta
- [ ] Documentação atualizada
- [ ] Backup criado
- [ ] Usuários notificados
- [ ] Treinamento realizado

### Pós-Deployment
- [ ] Funcionalidade validada
- [ ] Performance monitorada
- [ ] Feedback coletado
- [ ] Ajustes implementados
- [ ] Próximas versões planejadas

## 🔮 Roadmap Técnico

### Versão 1.1 (Próxima)
- Análise temporal com drill-down por mês/trimestre
- Implementação de forecasting com algoritmos do Power BI
- Dashboard mobile-friendly
- Alertas automáticos por email

### Versão 1.2 (Futuro)
- Integração com Power BI Service
- Implementação de RLS (Row Level Security)
- API REST para integração com outros sistemas
- Machine Learning para análise preditiva

### Versão 2.0 (Longo Prazo)
- Migração para Azure Synapse Analytics
- Real-time data streaming
- Advanced analytics com Python/R
- Chatbot integrado para consultas naturais

---

**⚙️ Nota Técnica**: Este documento deve ser atualizado a cada modificação significativa no dashboard. Mantenha sempre a versão mais recente sincronizada com o arquivo .pbix em produção.
