# Gov Hub PoC - Extração de Dados Governamentais com IA

## Descrição

Este projeto é uma **Prova de Conceito (PoC)** que demonstra como utilizar diferentes técnicas avançadas de **prompt engineering** com modelos de IA para extrair dados estruturados de textos do setor governamental de forma automatizada e precisa.

O projeto está estruturado em **múltiplas versões**, cada uma explorando abordagens e técnicas distintas para comparação de eficácia e robustez.

## Objetivos

- Demonstrar técnicas avançadas de prompt engineering
- Comparar diferentes abordagens de extração de dados
- Extrair dados específicos de textos governamentais
- Retornar informações em formato JSON estruturado
- Garantir robustez no tratamento de campos ausentes
- Avaliar performance e precisão entre diferentes metodologias

## Versões Disponíveis

### PoC v1 - Prompt Engineering Clássico (Google Gemini 2.5 Flash)
**Arquivo:** `poc_v1.ipynb`

**Técnicas implementadas:**
- Definição Clara de Papel (Role-Playing)
- Instruções Explícitas e Detalhadas
- Especificação do Formato de Saída
- Uso de Exemplos (Few-Shot Prompting)
- Uso de Delimitadores
- Preparar a Saída (Prefilling)

### PoC v2 - Chain of Thought + Reasoning (Planejado)
**Arquivo:** `poc_v2.ipynb`

**Técnicas a implementar:**
- Chain of Thought (CoT) Prompting
- Step-by-step reasoning
- Self-consistency decoding
- Validation prompts

### PoC v3 - Multi-Agent Approach (Planejado)
**Arquivo:** `poc_v3.ipynb`

**Técnicas a implementar:**
- Multiple specialized agents
- Consensus-based extraction
- Error detection and correction
- Confidence scoring


- **Python 3.8+** instalado
- **pip** (gerenciador de pacotes Python)
- **Conta Google** com acesso à API Gemini
- **Chave da API Google Gemini** ([obter aqui](https://aistudio.google.com/))

### Pré-requisitos Adicionais (para versões futuras):
- **OpenAI API Key** (para versões com GPT)
- **Anthropic API Key** (para versões com Claude)
- **Hugging Face Token** (para modelos open-source)

## Configuração do Ambiente

### 1. Clone ou baixe o projeto
```bash
# Se usando git:
git clone <url-do-repositório>
cd gov-hub-PoC

# Ou simplesmente navegue até a pasta do projeto
cd C:\Users\seu-usuario\Documents\faculdade\gov-hub-PoC
```

### 2. Criar Virtual Environment

#### No Windows (PowerShell/CMD):
```bash
# Criar a virtual environment
python -m venv gov-hub-env

# Ativar a virtual environment
# Opção 1 - PowerShell (se permitido):
.\gov-hub-env\Scripts\Activate.ps1

# Opção 2 - CMD ou se PowerShell bloquear:
.\gov-hub-env\Scripts\activate.bat

# Opção 3 - Command Prompt:
gov-hub-env\Scripts\activate
```

#### No macOS/Linux:
```bash
# Criar a virtual environment
python3 -m venv gov-hub-env

# Ativar a virtual environment
source gov-hub-env/bin/activate
```

### 3. Instalar Dependências

#### Método 1 - Usar requirements.txt (Recomendado):
```bash
# Atualizar pip
pip install --upgrade pip

# Instalar todas as dependências
pip install -r requirements.txt

# Registrar kernel no Jupyter
python -m ipykernel install --user --name=gov-hub-env --display-name="Gov Hub PoC"
```

#### Método 2 - Instalação manual:
```bash
# Atualizar pip
pip install --upgrade pip

# Dependências base
pip install google-generativeai

# Dependências para versões futuras (opcional)
pip install openai anthropic transformers torch

# Instalar suporte para Jupyter
pip install ipykernel jupyter

# Registrar kernel no Jupyter
python -m ipykernel install --user --name=gov-hub-env --display-name="Gov Hub PoC"
```

### 4. Verificar Instalação
```bash
# Verificar se as dependências foram instaladas
pip list | grep google  # Linux/macOS
pip list | findstr google  # Windows

# Listar todos os pacotes instalados
pip list
```

## Configuração da API

### 1. Obter Chave da API Gemini
1. Acesse [Google AI Studio](https://aistudio.google.com/)
2. Faça login com sua conta Google
3. Crie uma nova API key
4. Copie a chave gerada

### 2. Configurar a Chave no Projeto

**IMPORTANTE:** Por segurança, substitua a chave da API no arquivo do notebook pela sua própria chave:

```python
# Localize esta linha no notebook e substitua pela sua chave:
GEMINI_API_KEY = "SUA_CHAVE_AQUI"
```

**Dica de Segurança:** Para projetos em produção, use variáveis de ambiente:
```python
import os
GEMINI_API_KEY = os.getenv('GEMINI_API_KEY')
```

## Como Executar

### Escolhendo a Versão
Cada versão da PoC está em um notebook separado:
- **`poc_v1.ipynb`** - Versão atual com prompt engineering clássico
- **`poc_v2.ipynb`** - (Futuro) Chain of Thought
- **`poc_v3.ipynb`** - (Futuro) Multi-Agent
- **etc...**

### Opção 1 - Jupyter Notebook (Recomendado)
```bash
# Com a virtual environment ativada:
jupyter notebook

# Ou jupyter lab:
jupyter lab
```

1. Abra o arquivo da versão desejada (ex: `poc_v1.ipynb`)
2. Selecione o kernel "Gov Hub PoC" 
3. Execute as células sequencialmente (Shift + Enter)

### Opção 2 - VS Code
1. Abra o VS Code na pasta do projeto
2. Instale a extensão "Python" e "Jupyter"
3. Abra o arquivo da versão desejada
4. Selecione o interpretador Python da virtual environment
5. Execute as células

### Opção 3 - Google Colab
1. Faça upload do arquivo da versão desejada para o Colab
2. Execute a primeira célula para instalar dependências
3. Configure sua API key
4. Execute as demais células

## Estrutura do Projeto

```
gov-hub-PoC/
├── README.md                 # Este arquivo
├── poc_v1.ipynb             # PoC v1 - Prompt Engineering Clássico
├── poc_v2.ipynb             # PoC v2 - Chain of Thought (Planejado)
├── poc_v3.ipynb             # PoC v3 - Multi-Agent (Planejado)
├── poc_v4.ipynb             # PoC v4 - Fine-tuning + RAG (Planejado)
├── poc_v5.ipynb             # PoC v5 - Hybrid Ensemble (Planejado)
├── requirements.txt         # Lista de dependências
├── .gitignore              # Arquivos a serem ignorados pelo Git
├── results/                # Resultados e comparações entre versões
│   ├── v1_results.json     # Resultados da v1
│   ├── v2_results.json     # Resultados da v2
│   └── comparison.md       # Análise comparativa
└── gov-hub-env/            # Virtual environment (criada após setup)
```

## Técnicas de IA e Prompt Engineering por Versão

### Versão 1 - Prompt Engineering Clássico
O projeto demonstra **6 técnicas avançadas** de prompt engineering:

#### 1. Definição Clara de Papel (Role-Playing)
- Define a IA como "especialista em extração de dados"
- Estabelece contexto e comportamento esperado

#### 2. Instruções Explícitas e Detalhadas
- Especifica exatamente quais campos extrair
- Define como tratar campos ausentes
- Usa palavras-chave como "SEMPRE" e "obrigatoriamente"

#### 3. Especificação do Formato de Saída
- Exige formato JSON válido
- Garante estrutura consistente de chaves

#### 4. Uso de Exemplos (Few-Shot Prompting)
- Fornece exemplo concreto de entrada e saída
- Demonstra tratamento de campos encontrados e ausentes

#### 5. Uso de Delimitadores
- Seções claramente marcadas (**Campos para Extração:**, etc.)
- Separação visual das instruções

#### 6. Preparar a Saída (Prefilling)
- Inicia a resposta com formato esperado
- Guia o modelo para seguir o padrão correto

### Versões Futuras - Técnicas Planejadas

#### Versão 2 - Chain of Thought
- **CoT Prompting:** Força o modelo a mostrar seu raciocínio
- **Step-by-step reasoning:** Decomposição do problema em etapas
- **Self-consistency:** Múltiplas execuções para validação
- **Meta-prompting:** Prompts que geram prompts

#### Versão 3 - Multi-Agent
- **Agente Extrator:** Especializado em encontrar informações
- **Agente Validador:** Verifica a consistência dos dados
- **Agente Corretor:** Corrige erros identificados
- **Orquestrador:** Coordena a comunicação entre agentes

#### Versão 4 - RAG + Fine-tuning
- **Vector Store:** Base de conhecimento de documentos governamentais
- **Semantic Search:** Busca por contexto relevante
- **Fine-tuned Model:** Modelo especializado no domínio
- **Context Injection:** Injeção de contexto relevante

#### Versão 5 - Ensemble
- **Model Ensemble:** Combinação de múltiplos modelos
- **Voting Mechanism:** Sistema de votação para decisões
- **Confidence Weighting:** Peso baseado na confiança
- **Fallback Strategy:** Estratégias de recuperação

## Campos Extraídos

O sistema extrai os seguintes campos de textos governamentais:

- `num_transf` - Número de transferência
- `contrato_num` - Número do contrato
- `contrato_licitacao` - Número da licitação
- `instrumento_numero` - Número do instrumento jurídico
- `nc_aux` - Nota de crédito auxiliar
- `nc_prefix` - Prefixo da nota de crédito
- `nc_posfix` - Sufixo da nota de crédito
- `nc` - Nota de crédito principal

## Roadmap de Desenvolvimento

### Fase 1 (Concluída)
- ✅ PoC v1 - Prompt Engineering Clássico
- ✅ Estrutura base do projeto
- ✅ Documentação inicial

### Fase 2 (Planejada)
- 🔄 PoC v2 - Chain of Thought Prompting
- 🔄 Sistema de comparação de resultados
- 🔄 Métricas de avaliação

### Fase 3 (Planejada)
- 📋 PoC v3 - Multi-Agent Approach
- 📋 PoC v4 - RAG + Fine-tuning
- 📋 Dashboard de comparação

### Fase 4 (Planejada)
- 📋 PoC v5 - Hybrid Ensemble
- 📋 Análise estatística comparativa
- 📋 Recomendações de uso

## Troubleshooting

### Problema: Erro de execução de scripts no PowerShell
**Solução:**
```bash
# Use o arquivo .bat em vez do .ps1:
.\gov-hub-env\Scripts\activate.bat

# Ou habilite scripts temporariamente:
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```

### Problema: Conflitos de dependências
**Solução:**
- Use sempre a virtual environment
- Não instale globalmente se houver conflitos

### Problema: Erro na API Gemini
**Soluções:**
- Verifique se a chave da API está correta
- Confirme se a API está habilitada na sua conta Google
- Verifique limites de uso da API

### Problema: Kernel não aparece no Jupyter
**Solução:**
```bash
# Registre novamente o kernel:
python -m ipykernel install --user --name=gov-hub-env --display-name="Gov Hub PoC"

# Reinicie o Jupyter:
jupyter notebook --reload
```

## Exemplo de Uso

### Entrada:
```
Processo de Transferência n. TRF2024/001. 
Contrato Administrativo CA-5678. 
Referente à Licitação Contratual LCT-034/2023. 
Instrumento Jurídico IJ-990. 
Nota de Crédito principal: NC12345.
```

### Saída Esperada:
```json
{
  "num_transf": "TRF2024/001",
  "contrato_num": "CA-5678",
  "contrato_licitacao": "LCT-034/2023",
  "instrumento_numero": "IJ-990",
  "nc_aux": "",
  "nc_prefix": "",
  "nc_posfix": "",
  "nc": "NC12345"
}
```

## Contribuições

Este é um projeto de prova de conceito desenvolvido para fins acadêmicos e de pesquisa. Contribuições são bem-vindas, especialmente:

- **Implementação de novas versões** (v2, v3, etc.)
- **Melhoria das técnicas existentes**
- **Novos datasets de teste**
- **Métricas de avaliação**
- **Documentação e exemplos**

Para contribuir:
1. Fork o repositório
2. Crie uma branch para sua feature
3. Implemente as mudanças
4. Teste thoroughly
5. Submeta um pull request

## Licença

Este projeto é desenvolvido para fins educacionais e de demonstração.

## Avisos Importantes

- **Não compartilhe sua chave da API publicamente**
- **Monitore os custos de uso das APIs**
- **Este é um projeto de demonstração, adapte para uso em produção**
- **Mantenha a virtual environment ativada durante o desenvolvimento**
- **Cada versão pode ter requisitos específicos de hardware/software**

---

## Suporte

Se encontrar problemas durante a configuração ou execução, verifique se:

1. Python 3.8+ está instalado corretamente
2. Virtual environment está ativada
3. Dependências foram instaladas sem erros
4. Chave da API está configurada corretamente
5. Kernel correto está selecionado no Jupyter

Para problemas específicos, consulte a seção de Troubleshooting acima ou crie uma issue no repositório. 