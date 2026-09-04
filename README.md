# Deep Dive em Embeddings, LLMs e AI Agents

Repositório com materiais educacionais progressivos sobre Large Language Models, embeddings e agentes de IA.

## 📋 Conteúdo

- `lab/01_image_embeddings.ipynb` - Transformando imagens em vetores e comparando similaridade
- `lab/02_text_embeddings.ipynb` - Transformando texto em vetores e entendendo significado semântico

## 🚀 Executando os Notebooks

### Com repo2docker (recomendado - sem instalação local)

[repo2docker](https://repo2docker.readthedocs.io/) é uma ferramenta que automáticamente cria um ambiente Docker a partir de um repositório, instalando todas as dependências definidas em `requirements.txt`.

**Instalação:**
```bash
pip install repo2docker
```

**Executar:**
```bash
# No diretório do repositório
repo2docker --no-run .
docker run -p 8888:8888 <IMAGE_ID>

# Ou diretamente:
repo2docker -p 8888 .
```

Acesse `http://localhost:8888` no navegador. O token será exibido no terminal.

### Com Docker

```bash
# Build da imagem
docker build -t llm-study .

# Executar container
docker run -p 8888:8888 -v $(pwd):/workspace llm-study
```

Acesse `http://localhost:8888` no navegador e use o token mostrado no terminal.

### Desenvolvimento Local - Com UV

```bash
# Instalar dependências
uv sync

# Iniciar Jupyter
uv run jupyter notebook
```

### Desenvolvimento Local - Com Pip

```bash
pip install -r requirements.txt
jupyter notebook
```

## 📦 Dependências

As dependências estão listadas em `requirements.txt`:

- **torch** - Framework PyTorch para deep learning
- **transformers** - Modelos pré-treinados (CLIP, SentenceTransformers, etc)
- **sentence-transformers** - Modelos especializados em embeddings de texto
- **Pillow** - Processamento de imagens
- **matplotlib** - Visualizações e gráficos
- **jupyter** - Ambiente de notebooks interativos
- **numpy** - Computação numérica
- **ipywidgets** - Widgets interativos para Jupyter

## 🛠️ Desenvolvimento Local

### Com UV (recomendado)

```bash
# Instalar dependências
uv sync

# Adicionar nova dependência
uv add nome-do-pacote

# Atualizar lock file
uv lock
```

### Com Pip

```bash
python -m venv venv
source venv/bin/activate  # ou `venv\Scripts\activate` no Windows
pip install -r requirements.txt
```

## 📂 Estrutura do Repositório

```
intro-to-agents/
├── README.md                      # Este arquivo
├── requirements.txt               # Dependências Python
├── Dockerfile                     # Para execução containerizada
├── .dockerignore                  # Arquivos a ignorar no Docker
├── lab/                           # Laboratórios com notebooks
│   ├── 01_image_embeddings.ipynb
│   └── 02_text_embeddings.ipynb
└── pyproject.toml                # Configuração do projeto (opcional)
```

## 📝 Estrutura dos Notebooks

Os notebooks são progressivos e devem ser executados nesta ordem:

### 1. Image Embeddings (`lab/01_image_embeddings.ipynb`)
Aprenda como o modelo CLIP transforma imagens em vetores de alta dimensionalidade (embeddings) e use essas representações para:
- Calcular similaridade entre imagens
- Encontrar imagens similares sem treinamento
- Entender espaços latentes multidimensionais

### 2. Text Embeddings (`lab/02_text_embeddings.ipynb`)
Explore como modelos de linguagem transformam texto em vetores semânticos:
- Comparar significado entre palavras e frases
- Usar sentence-transformers para embeddings de qualidade
- Aplicações práticas de busca semântica

## 🎯 Próximos Tópicos

- Conectar embeddings com RAG (Retrieval Augmented Generation)
- Arquitetura e funcionamento de LLMs
- Construindo AI Agents que usam ferramentas externas
- Fine-tuning de modelos

## 📖 Recursos Adicionais

- [Documentação PyTorch](https://pytorch.org/)
- [Hugging Face Transformers](https://huggingface.co/docs/transformers/)
- [Sentence Transformers](https://www.sbert.net/)
