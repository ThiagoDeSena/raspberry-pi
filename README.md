# Dashboard de Monitoramento - Estufa IoT para PLA

<img width="1916" height="878" alt="image" src="https://github.com/user-attachments/assets/180fc563-2f3c-4ded-8e08-a776d40e8004" />

## 📊 Visão Geral do Dashboard

Este dashboard desenvolvido em Streamlit fornece uma interface web para monitoramento e controle em tempo real do sistema de estufa *in situ* para conservação de filamentos de PLA.

## 🎯 Funcionalidades Principais

### 1. **Painel de Última Leitura**
- Exibe os valores mais recentes de temperatura e umidade
- Mostra o timestamp da última medição
- Atualização em tempo real

**Exemplo:**
```
Última Leitura
• Temperatura: 35.6°C
• Umidade: 33.0%
• 2025-10-06 10:41:54
```

### 2. **Gráfico de Monitoramento Interativo**
- **Linha Vermelha**: Temperatura (°C) ao longo do tempo
- **Linha Azul**: Umidade (%) ao longo do tempo
- **Interatividade**: Clique em qualquer ponto do gráfico para ver os valores exatos de temperatura e umidade naquele momento específico

### 3. **Sidebar - Filtros e Controles**

#### 📅 **Selecionar Período**
Opções pré-definidas:
- **1 Dia** - Visualização das últimas 24 horas
- **7 Dias** - Histórico da última semana
- **30 Dias** - Histórico do último mês
- **Tudo** - Todo o histórico disponível no banco de dados

#### 📆 **Selecionar Intervalo de Datas Personalizado**
- **Data Inicial**: Selecionar data de início
- **Data Final**: Selecionar data de término
- **Botão "Buscar"**: Aplicar o filtro personalizado

#### 🔧 **Controle de Variáveis**
- **"Escolher variável"**: Dropdown para selecionar qual variável visualizar:
  - Ambas (temperatura e umidade)
  - Apenas temperatura
  - Apenas umidade

#### ⚡ **Painel de Controle**
- **Setpoint de Temperatura**: Define a temperatura alvo (ex: 40.00°C)
  - Controles `+` e `-` para ajuste fino
- **Histerese**: Define a faixa de tolerância (ex: 2.00°C)
  - Ativa/desativa com checkbox
- **Botão "Enviar Setpoint/Histerese"**: Aplica as novas configurações ao sistema

### 4. **Status do Sistema**
- **Relé**: Indica o estado atual do sistema de aquecimento
  - **"Ligado"**: Placa de aquecimento ativa
  - **"Desligado"**: Sistema em repouso

## 🛠️ Como Usar

### Visualização de Dados
1. **Acesse o dashboard** através do link fornecido pelo Ngrok
2. **Verifique a última leitura** no topo da página
3. **Analise o gráfico** para tendências de temperatura e umidade
4. **Use os filtros** no sidebar para focar em períodos específicos
5. **Clique no gráfico** para detalhes pontuais

### Controle do Sistema
1. **Navegue até a aba de controle** no sidebar
2. **Ajuste o setpoint** conforme necessário para o material
3. **Defina a histerese** para evitar ciclagem muito frequente
4. **Clique em "Enviar"** para aplicar as configurações

## 🔄 Fluxo de Dados em Tempo Real

```
Sensor DHT11 → ESP32 → MQTT → Raspberry Pi → MariaDB → Streamlit Dashboard
```

## 📱 Acesso
- **Local**: `http://localhost:8501` (quando executado localmente)
- **Remoto**: URL única fornecida pelo Ngrok (ex: `https://abc123.ngrok.io`)

## ⚙️ Requisitos Técnicos

- Streamlit 1.28+
- Python 3.8+
- Conexão com banco MariaDB
- Broker MQTT ativo
- Acesso à internet (para Ngrok)

---

**💡 Dica**: Para melhor conservação do PLA, mantenha a temperatura entre 35-45°C e umidade abaixo de 45%!
