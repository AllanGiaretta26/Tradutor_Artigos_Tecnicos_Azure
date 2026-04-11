# Tradutor de Artigos Técnicos com Azure AI

Tradutor inteligente de artigos técnicos e documentos utilizando **Python**, **Azure AI Translator** e **Azure OpenAI**, executado no Google Colab.

## 📋 Sobre o Projeto

Projeto desenvolvido como atividade prática, com adaptações e implementação própria para:

- **Tradução de artigos técnicos** via web scraping + Azure OpenAI
- **Tradução de arquivos DOCX** via Azure AI Translator

---

## 🚀 Funcionalidades

### Notebook 1: `tdt_artigos_técnicos.ipynb`

| Funcionalidade | Descrição |
|---|---|
| Web Scraping | Extração de texto de artigos em URLs usando `BeautifulSoup` |
| Tradução com IA | Tradução contextual via **Azure OpenAI** (`langchain-openai`) |
| Preservação de Markdown | Mantém formatação e estrutura do artigo original |

### Notebook 2: `tdt_arquivos.ipynb`

| Funcionalidade | Descrição |
|---|---|
| Upload de arquivos | Upload direto pelo Google Colab |
| Tradução DOCX | Processamento de documentos `.docx` com `python-docx` |
| API Translator | Tradução rápida via **Azure AI Translator API** |

---

## 🛠️ Tecnologias Utilizadas

- **Python 3**
- **Azure AI Translator** — API de tradução rápida
- **Azure OpenAI** — Tradução contextual com IA generativa
- **BeautifulSoup4** — Web scraping
- **python-docx** — Manipulação de arquivos Word
- **LangChain OpenAI** — Integração com modelos Azure OpenAI
- **Google Colab** — Ambiente de execução gratuito

---

## 📦 Dependências

```bash
pip install requests beautifulsoup4 openai langchain-openai python-docx
```

---

## 🔧 Configuração

### Variáveis de Ambiente Necessárias

Antes de executar os notebooks, configure suas credenciais Azure:

```python
import os

os.environ["AZURE_TRANSLATOR_KEY"] = "SUA_CHAVE_TRANSLATOR"
os.environ["AZURE_TRANSLATOR_ENDPOINT"] = "SEU_ENDPOINT"
os.environ["AZURE_TRANSLATOR_REGION"] = "SUA_REGIAO"
```

Para o notebook de artigos com OpenAI:

```python
from langchain_openai.chat_models.azure import AzureChatOpenAI

client = AzureChatOpenAI(
    azure_endpoint="SEU_ENDPOINT",
    api_key="SUA_CHAVE",
    api_version="VERSÃO_DA_API",
    deployment_name="NOME_DO_DEPLOYMENT",
    max_retries=0
)
```

> ⚠️ **Nunca compartilhe suas chaves.** Substitua os placeholders pelas suas credenciais reais.

---

## 📖 Como Usar

### Tradução de Artigos

1. Abra o notebook `tdt_artigos_técnicos.ipynb` no Google Colab
2. Execute todas as células em ordem
3. Cole a URL do artigo desejado
4. Informe o idioma de destino (ex: `portugues`, `english`, `spanish`)
5. Aguarde a tradução gerada pelo Azure OpenAI

### Tradução de Arquivos DOCX

1. Abra o notebook `tdt_arquivos.ipynb` no Google Colab
2. Execute as células de configuração
3. Faça upload do arquivo `.docx`
4. Informe o idioma de destino (ex: `en`, `pt`, `es`, `fr`)
5. Baixe o arquivo traduzido gerado automaticamente

---

## 🌐 Idiomas Suportados

A tradução suporta diversos idiomas, incluindo:

| Código | Idioma |
|---|---|
| `en` | Inglês |
| `pt` / `portugues` | Português |
| `es` | Espanhol |
| `fr` | Francês |
| `de` | Alemão |

---

## 📁 Estrutura do Projeto

```
tradutor-azure-openai/
├── README.md                     # Documentação do projeto
├── tdt_artigos_técnicos.ipynb    # Notebook: Tradutor de artigos via URL + OpenAI
└── tdt_arquivos.ipynb            # Notebook: Tradutor de arquivos DOCX
```

---

## 📝 Exemplo de Uso

```python
# Tradução de texto simples
texto = "Digite o texto para traduzir: "
idioma = input("Idioma de destino (ex: en, pt, es, fr): ")
traducao = traduzir_texto(texto, idioma)
print(traducao)

# Tradução de artigo web
url = 'https://dev.to/exemplo/artigo-tecnico'
texto = extract_text_from_url(url)
artigo_traduzido = translate_article(texto, "portugues")
```

---

## ⚠️ Notas Importantes

- Este projeto roda exclusivamente no **Google Colab**
- É necessária uma conta **Azure** com chaves válidas para os serviços de Translator e OpenAI
- As credenciais devem ser configuradas diretamente nas células de configuração

---

## 👤 Autor
Desenvolvido por Allan Giaretta
