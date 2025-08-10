# 🇧🇷 ZucaSeek - IA Brasileira

**ZucaSeek** é uma inteligência artificial genuinamente brasileira, desenvolvida com personalidade calorosa e conhecimento cultural do Brasil. Integra o poder do TinyLLaMA local com a versatilidade do Gemini remoto, oferecendo uma experiência de chat única e autenticamente brasileira.

## ✨ Características Principais

### 🧠 **Personalidade Brasileira Autêntica**
- **Caloroso e Acolhedor** (90% warmth)
- **Extremamente Amigável** (95% friendliness)
- **Orgulho Cultural Brasileiro** (85% cultural pride)
- **Comunicativo e Expressivo** (85% expressiveness)
- **Empático e Compreensivo** (90% empathy)

### 🗣️ **Expressões Brasileiras Naturais**
- "Opa!", "Beleza!", "Que legal!", "Massa!", "Show de bola!"
- "Valeu!", "Obrigadão!", "De boa!", "Tranquilo!", "Suave!"
- "Pode crer!", "Com certeza!", "Sem dúvida!", "Imagina!"

### 🇧🇷 **Conhecimento Cultural Brasileiro**
- **Culinária**: feijoada, brigadeiro, coxinha, açaí, tapioca
- **Lugares**: Cristo Redentor, Copacabana, Amazônia, Pantanal
- **Música**: samba, bossa nova, forró, MPB, axé, funk carioca
- **Esportes**: futebol, vôlei, capoeira, surf, Fórmula 1
- **Festivais**: Carnaval, Festa Junina, Rock in Rio, Oktoberfest

## 🚀 Tecnologias Utilizadas

### **Frontend**
- **React 18** com Vite
- **Tailwind CSS** para estilização
- **shadcn/ui** para componentes
- **Lucide React** para ícones

### **Backend**
- **Flask** com Python 3.11
- **Flask-CORS** para integração frontend-backend
- **SQLAlchemy** para banco de dados
- **python-dotenv** para configurações

### **Modelos de IA**
- **TinyLLaMA 1.1B** (modelo local)
- **Google Gemini** (modelo remoto)
- **llama-cpp-python** para execução local

### **Extensões Integradas**
- **LLM_Web_search** - Busca na web
- **Memoir+** - Sistema de memória
- **AllTalk_v2_TTS** - Text-to-Speech
- **Twinbook** - Chat e notebook
- **Playground** - Notebook para escritores
- **ad_discordbot** - Bot Discord
- **telegram_bot** - Interface Telegram
- **tavernai_charas** - Gerenciador de personagens

## 📁 Estrutura do Projeto

```
ZucaSeek/
├── zucaseek-backend/          # Backend Flask
│   ├── src/
│   │   ├── routes/           # Rotas da API
│   │   │   ├── zucaseek.py   # Rotas principais
│   │   │   └── personality.py # Rotas de personalidade
│   │   ├── services/         # Serviços
│   │   │   ├── llama_cpp_service.py
│   │   │   ├── gemini_service.py
│   │   │   └── personality_service.py
│   │   └── main.py          # Aplicação principal
│   └── requirements.txt     # Dependências Python
├── zucaseek-frontend/        # Frontend React
│   ├── src/
│   │   ├── components/      # Componentes React
│   │   │   ├── Chat.jsx
│   │   │   ├── Sidebar.jsx
│   │   │   ├── ModelsPanel.jsx
│   │   │   ├── ExtensionsPanel.jsx
│   │   │   └── MemoryPanel.jsx
│   │   └── App.jsx         # Aplicação principal
│   └── package.json        # Dependências Node.js
├── extensoes/              # Extensões integradas
├── modelos/               # Modelos de IA
│   └── TinyLlama/        # Modelo TinyLLaMA
└── .env                  # Configurações de ambiente
```

## 🛠️ Instalação e Configuração

### **Pré-requisitos**
- Python 3.11+
- Node.js 20+
- Git

### **1. Clonar o Repositório**
```bash
git clone <repository-url>
cd ZucaSeek
```

### **2. Configurar Backend**
```bash
cd zucaseek-backend
python -m venv venv
source venv/bin/activate  # Linux/Mac
# ou
venv\Scripts\activate     # Windows
pip install -r requirements.txt
```

### **3. Configurar Frontend**
```bash
cd zucaseek-frontend
pnpm install
# ou
npm install
```

### **4. Configurar Variáveis de Ambiente**
Crie um arquivo `.env` na raiz do projeto:
```env
# Configurações TinyLLaMA
TINYLLAMA_MODEL_PATH=/path/to/tinyllama-model.gguf
TINYLLAMA_CONTEXT_SIZE=2048
TINYLLAMA_MAX_TOKENS=512
TINYLLAMA_TEMPERATURE=0.7

# Configurações Gemini (opcional)
GEMINI_API_KEY=sua_chave_api_aqui
GEMINI_MODEL=gemini-pro
GEMINI_TEMPERATURE=0.7
GEMINI_MAX_TOKENS=1024
```

### **5. Baixar Modelo TinyLLaMA**
```bash
mkdir -p modelos/TinyLlama
cd modelos/TinyLlama
wget https://huggingface.co/TheBloke/TinyLlama-1.1B-Chat-v1.0-GGUF/resolve/main/tinyllama-1.1b-chat-v1.0.Q4_K_M.gguf
```

## 🚀 Executando o Sistema

### **1. Iniciar Backend**
```bash
cd zucaseek-backend
source venv/bin/activate
python src/main.py
```
O backend estará disponível em: `http://localhost:5000`

### **2. Iniciar Frontend**
```bash
cd zucaseek-frontend
pnpm run dev --host
```
O frontend estará disponível em: `http://localhost:5173`

## 📚 API Endpoints

### **Endpoints Principais**
- `GET /api/zucaseek/status` - Status do sistema
- `POST /api/zucaseek/chat` - Chat com a IA
- `GET /api/zucaseek/modelos` - Lista modelos disponíveis
- `POST /api/zucaseek/modelos/teste` - Testa modelos
- `GET /api/zucaseek/extensoes` - Lista extensões

### **Endpoints de Personalidade**
- `GET /api/zucaseek/personalidade/stats` - Estatísticas da personalidade
- `GET /api/zucaseek/personalidade/traits` - Traços de personalidade
- `PUT /api/zucaseek/personalidade/traits` - Atualizar traços
- `GET /api/zucaseek/personalidade/expressions` - Expressões brasileiras
- `POST /api/zucaseek/personalidade/generate-response` - Gerar resposta contextual

### **Exemplo de Uso da API**

#### **Chat com ZucaSeek**
```bash
curl -X POST "http://localhost:5000/api/zucaseek/chat" \
  -H "Content-Type: application/json" \
  -d '{"mensagem": "Oi ZucaSeek! Como você está?"}'
```

**Resposta:**
```json
{
  "resposta": "Oi! Tudo bem? Sou o ZucaSeek, sua IA brasileira! Como posso te ajudar hoje? 😊",
  "modelo": "TinyLLaMA-1.1B-Simulação-Brasileira",
  "personalidade": {
    "emotion_detected": "happy",
    "cultural_elements": true
  },
  "status": "sucesso"
}
```

#### **Status do Sistema**
```bash
curl -X GET "http://localhost:5000/api/zucaseek/status"
```

**Resposta:**
```json
{
  "status": "ativo",
  "config": {
    "nome": "ZucaSeek",
    "versao": "1.0.0",
    "idioma": "pt-br",
    "personalidade": {
      "estilo": "brasileiro_amigavel"
    }
  },
  "modelos": {
    "tinyllama": {
      "nome": "TinyLLaMA-1.1B-Chat-v1.0",
      "carregado": true,
      "modo": "simulacao"
    },
    "gemini": {
      "nome": "gemini-pro",
      "configurado": false
    }
  }
}
```

## 🎯 Funcionalidades

### **Interface Web**
- **Chat Interativo** com personalidade brasileira
- **Painel de Modelos** para gerenciar TinyLLaMA e Gemini
- **Painel de Extensões** com filtros e categorização
- **Painel de Memória** para sistema Memoir+
- **Sidebar Dinâmica** com status em tempo real

### **Sistema de Personalidade**
- **Detecção de Emoções** automática
- **Respostas Contextuais** baseadas na entrada
- **Expressões Brasileiras** integradas naturalmente
- **Referências Culturais** do Brasil
- **Traços Configuráveis** de personalidade

### **Modelos de IA**
- **TinyLLaMA Local** para respostas rápidas
- **Gemini Remoto** para tarefas complexas
- **Fallback Inteligente** entre modelos
- **Modo Simulação** quando modelos não estão disponíveis

## 🔧 Configuração Avançada

### **Personalizar Traços de Personalidade**
```bash
curl -X PUT "http://localhost:5000/api/zucaseek/personalidade/traits" \
  -H "Content-Type: application/json" \
  -d '{"trait": "humor", "value": 0.9}'
```

### **Adicionar Referência Cultural**
```bash
curl -X POST "http://localhost:5000/api/zucaseek/personalidade/cultural-references" \
  -H "Content-Type: application/json" \
  -d '{"category": "food", "reference": "pão de açúcar"}'
```

### **Configurar Gemini**
1. Obtenha uma chave da API do Google Gemini
2. Adicione no arquivo `.env`:
```env
GEMINI_API_KEY=sua_chave_aqui
```
3. Reinicie o backend

## 🧪 Testes

### **Testar API**
```bash
# Testar status
curl -X GET "http://localhost:5000/api/zucaseek/status"

# Testar chat
curl -X POST "http://localhost:5000/api/zucaseek/chat" \
  -H "Content-Type: application/json" \
  -d '{"mensagem": "Olá!"}'

# Testar personalidade
curl -X GET "http://localhost:5000/api/zucaseek/personalidade/stats"
```

### **Testar Interface**
1. Acesse `http://localhost:5173`
2. Digite uma mensagem no chat
3. Teste diferentes painéis (Modelos, Extensões, Memória)
4. Verifique a personalidade brasileira nas respostas

## 🤝 Contribuindo

1. Fork o projeto
2. Crie uma branch para sua feature (`git checkout -b feature/AmazingFeature`)
3. Commit suas mudanças (`git commit -m 'Add some AmazingFeature'`)
4. Push para a branch (`git push origin feature/AmazingFeature`)
5. Abra um Pull Request

## 📄 Licença

Este projeto está licenciado sob a Licença MIT - veja o arquivo [LICENSE](LICENSE) para detalhes.

## 🙏 Agradecimentos

- **OpenManus-RL** pela base de agentes de IA
- **text-generation-webui** pelas extensões
- **TinyLLaMA** pelo modelo local eficiente
- **Google Gemini** pelo modelo remoto avançado
- **Comunidade brasileira** pela inspiração cultural

## 📞 Suporte

Para suporte, abra uma issue no GitHub ou entre em contato:
- **Email**: alfasec77@gmail.com
- **Discord**: ZucaSeek Community em Breve
- **Telegram**: @ZucaSeekBot Em breve

---

**ZucaSeek v1.0.0** - IA Brasileira • OpenManus-RL • 2025

*"Sua IA brasileira de confiança! 🇧🇷"*

