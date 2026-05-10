# Tradutor de Artigos Técnicos com Azure AI

![Python](https://img.shields.io/badge/Python-3-blue)
![Azure](https://img.shields.io/badge/Azure-AI%20Services-0078D4)
![Azure OpenAI](https://img.shields.io/badge/Azure-OpenAI-10A37F)
![Google Colab](https://img.shields.io/badge/Google-Colab-F9AB00)
![Status](https://img.shields.io/badge/status-conclu%C3%ADdo-brightgreen)
![License](https://img.shields.io/badge/license-MIT-green)

> Tradutor inteligente de artigos técnicos e documentos `.docx` usando Python, Azure AI Translator e Azure OpenAI, executado no Google Colab.

## Descrição

Este projeto reúne dois notebooks Python que demonstram o uso de serviços de IA da Azure para tradução de conteúdo técnico. O primeiro extrai artigos diretamente de URLs e aplica tradução contextual via Azure OpenAI, preservando a formatação Markdown original. O segundo recebe arquivos `.docx` e realiza traduções rápidas através da API do Azure AI Translator.

Foi desenvolvido como atividade prática, com adaptações e implementação própria para explorar a integração entre web scraping, manipulação de documentos e modelos generativos.

## Status do Projeto

![Status](https://img.shields.io/badge/status-conclu%C3%ADdo-brightgreen)

Projeto concluído e funcional. Roda exclusivamente no Google Colab e requer conta Azure ativa com chaves válidas para Translator e OpenAI.

## Tecnologias

- ![Python](https://img.shields.io/badge/-Python%203-3776AB?logo=python&logoColor=white) — linguagem base
- ![Azure](https://img.shields.io/badge/-Azure%20AI%20Translator-0078D4?logo=microsoft-azure&logoColor=white) — API de tradução rápida
- ![OpenAI](https://img.shields.io/badge/-Azure%20OpenAI-10A37F?logo=openai&logoColor=white) — tradução contextual com IA generativa
- ![LangChain](https://img.shields.io/badge/-LangChain-1C3C3C?logo=langchain&logoColor=white) — integração com modelos Azure OpenAI
- ![BeautifulSoup](https://img.shields.io/badge/-BeautifulSoup4-43B02A) — web scraping
- ![python-docx](https://img.shields.io/badge/-python--docx-2B579A) — manipulação de arquivos Word
- ![Colab](https://img.shields.io/badge/-Google%20Colab-F9AB00?logo=googlecolab&logoColor=white) — ambiente de execução

## Funcionalidades

### Notebook 1 — `tdt_artigos_técnicos.ipynb`

| Funcionalidade | Descrição |
|---|---|
| Web Scraping | Extração de texto de artigos em URLs usando `BeautifulSoup` |
| Tradução com IA | Tradução contextual via Azure OpenAI (`langchain-openai`) |
| Preservação de Markdown | Mantém formatação e estrutura do artigo original |

### Notebook 2 — `tdt_arquivos.ipynb`

| Funcionalidade | Descrição |
|---|---|
| Upload de arquivos | Upload direto pelo Google Colab |
| Tradução DOCX | Processamento de documentos `.docx` com `python-docx` |
| API Translator | Tradução rápida via Azure AI Translator API |

## Como Instalar e Rodar

### Pré-requisitos

- Conta no [Google Colab](https://colab.research.google.com/)
- Conta Azure com os serviços **Azure AI Translator** e **Azure OpenAI** provisionados
- Chaves de API válidas dos dois serviços

### Passo a passo

1. Clone o repositório:

```bash
git clone https://github.com/AllanGiaretta26/tradutor-azure-openai.git
```

2. Abra um dos notebooks no Google Colab (`tdt_artigos_técnicos.ipynb` ou `tdt_arquivos.ipynb`).

3. Instale as dependências na primeira célula:

```bash
pip install requests beautifulsoup4 openai langchain-openai python-docx
```

4. Configure as variáveis de ambiente com suas credenciais Azure (ver seção abaixo).

5. Execute todas as células em ordem.

## Variáveis de Ambiente

Antes de executar os notebooks, configure suas credenciais Azure:

```python
import os

os.environ["AZURE_TRANSLATOR_KEY"] = ""
os.environ["AZURE_TRANSLATOR_ENDPOINT"] = ""
os.environ["AZURE_TRANSLATOR_REGION"] = ""
```

Para o notebook de artigos com Azure OpenAI:

```python
from langchain_openai.chat_models.azure import AzureChatOpenAI

client = AzureChatOpenAI(
    azure_endpoint="",
    api_key="",
    api_version="",
    deployment_name="",
    max_retries=0
)
```

> Nunca compartilhe suas chaves. Substitua os placeholders pelas suas credenciais reais antes de executar.

## Como Usar

### Tradução de artigos

1. Abra o notebook `tdt_artigos_técnicos.ipynb` no Google Colab.
2. Execute todas as células em ordem.
3. Cole a URL do artigo desejado.
4. Informe o idioma de destino (ex: `portugues`, `english`, `spanish`).
5. Aguarde a tradução gerada pelo Azure OpenAI.

### Tradução de arquivos DOCX

1. Abra o notebook `tdt_arquivos.ipynb` no Google Colab.
2. Execute as células de configuração.
3. Faça upload do arquivo `.docx`.
4. Informe o idioma de destino (ex: `en`, `pt`, `es`, `fr`).
5. Baixe o arquivo traduzido gerado automaticamente.

## Idiomas Suportados

| Código | Idioma |
|---|---|
| `en` | Inglês |
| `pt` / `portugues` | Português |
| `es` | Espanhol |
| `fr` | Francês |
| `de` | Alemão |

## Exemplo de Uso

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

## Estrutura do Projeto

```
tradutor-azure-openai/
├── README.md                     # Documentação do projeto
├── LICENSE                       # Licença MIT
├── tdt_artigos_técnicos.ipynb    # Notebook: tradutor de artigos via URL + OpenAI
└── tdt_arquivos.ipynb            # Notebook: tradutor de arquivos DOCX
```

## Licença

Distribuído sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

---

Desenvolvido por **[Allan Giaretta](https://github.com/AllanGiaretta26)**.
