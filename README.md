# Cloud-na-IA
Serviços de Cloud na IA - Bootcamp JAVA - DIO bradesco


🎙️ Azure Speech Studio
O Azure Speech Studio é uma plataforma da Microsoft que permite criar, treinar e testar modelos de reconhecimento de voz, conversão de texto em fala (TTS), tradução de fala e diarização. Ele oferece uma interface visual para customizar vozes neurais, ajustar modelos de reconhecimento de fala e testar transcrição de áudio. É ideal para desenvolver aplicações com comandos de voz, legendas automáticas e assistentes virtuais.

🧠 Azure Language Studio
O Azure Language Studio permite explorar e criar modelos de Processamento de Linguagem Natural (NLP) da Azure AI. Com ele, é possível realizar análises de sentimentos, extração de entidades, categorização de textos, reconhecimento de PII (informações sensíveis) e criação de modelos personalizados para entender contextos específicos. Ele oferece uma interface intuitiva para testar APIs cognitivas e treinar modelos próprios sem necessidade de codificação complexa.

.

🚀 Como utilizar o Azure Speech Studio
🔗 Acesso
Acesse: https://speech.microsoft.com/
Faça login com sua conta da Microsoft/Azure.

🏗️ Criação e Configuração
- Crie um recurso de Speech no portal do Azure:
Portal: https://portal.azure.com/
Busque por “Speech” e clique em Criar.
Configure a região, grupo de recursos e nome.

- No Speech Studio, selecione uma das ferramentas:

Text to Speech (TTS) – Para gerar áudios a partir de textos.
Speech to Text (STT) – Para transcrever áudios em texto.
Custom Voice – Crie uma voz neural personalizada.
Custom Speech – Aprimore o reconhecimento de fala treinando modelos específicos.

🔧 Como usar na prática
Escolha, por exemplo, Text to Speech:
Insira o texto desejado.
Escolha a voz, idioma e estilo (neutro, alegre, empático, etc.).
Teste o áudio diretamente na interface.
Faça o download do arquivo de áudio gerado.

- Para Speech to Text:

Faça upload de um arquivo de áudio.
Execute a transcrição.
Visualize e exporte o texto reconhecido.

🧠 Como utilizar o Azure Language Studio
🔗 Acesso
Acesse: https://language.azure.com/
Faça login com sua conta da Microsoft/Azure.

🏗️ Criação e Configuração
Crie um recurso de Language no portal do Azure:

Busque por “Language” e clique em Criar.
Escolha a região, grupo de recursos e nome.

🔧 Funcionalidades disponíveis
- No Language Studio você pode escolher diferentes tarefas:

Análise de Sentimentos e Opiniões
Extração de Entidades Nomeadas
Reconhecimento de Informações Pessoais (PII)
Classificação de Texto
Resumos Automatizados
Custom Text Classification (treinar modelos personalizados)

📜 Como usar na prática

Escolha, por exemplo, Análise de Sentimento:
Insira o texto ou faça upload de documentos.
Execute a análise.
Veja o resultado com porcentagens de sentimento (positivo, neutro, negativo) e insights.

- Para Classificação Personalizada:

Crie um projeto.
Adicione categorias e exemplos de textos.
Treine o modelo na própria interface.
Teste e publique para consumo via API.

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Utilizando AI Search para indexação e consulta de Dados

1️⃣ Criar os Recursos Necessários
✅ Azure AI Search:

No portal https://portal.azure.com/, busque por “Azure AI Search”.
Clique em Criar.
Defina:
Nome do serviço
Região
SKU (Free para testes ou Standard para produção)

✅ Azure Blob Storage:

Crie um Storage Account.
No Storage, crie um Container (público ou privado).
Faça upload dos documentos (PDF, DOCX, TXT, JPEG, etc.).

2️⃣ Configurar um Data Source (Fonte de Dados)
Acesse o serviço Azure AI Search criado.
No painel lateral, clique em Data Sources > + Add.

Configure:

Data Source Type: Azure Blob Storage.
Conecte seu Storage usando a Connection String ou Managed Identity.
Informe o nome do container que contém os documentos.
Marque a opção de usar Cognitive Skills se quiser extrair texto de imagens, PDFs digitalizados, ou aplicar análise semântica.

3️⃣ Configurar um Skillset (opcional, mas recomendado)
Se seus documentos forem PDFs com imagens, JPEG, ou arquivos não estruturados, ative um Skillset para usar IA Cognitiva.

Adicione Skills, como:
OCR (Reconhecimento Óptico de Caracteres) – Ler texto de imagens.
Key Phrase Extraction – Extrair tópicos-chave.
Entity Recognition – Identificar entidades como nomes, locais, datas.
Language Detection, Sentiment Analysis, etc.
🔧 Se não quiser usar skills, ele apenas pega metadados e texto simples.

4️⃣ Criar um Index (Índice de Busca)
Vá em Indexes > + Add.

Defina:

Name: Nome do índice.
Fields: Campos extraídos, como:
id: chave única (obrigatório).
content: corpo do documento.
metadata_storage_name: nome do arquivo.
Outros campos extraídos automaticamente

Configure:

Searchable: Permitir busca textual.
Filterable: Permitir filtros.
Facetable: Para criar facetas (categorias).

Criar um Indexer (Processo de Indexação)
Vá em Indexers > + Add.

Configure:

Nome do indexador.
Fonte: o Data Source que você criou.
Destino: o Index que você criou.
Frequência: manual, agendado (diário, semanal).
Execute para começar a indexação dos documentos.

fazer Consultas (Search)
Acesse o painel Search Explorer no próprio Azure Search.

Teste buscas:

Simples: contabilidade
Com filtros: contabilidade AND metadata_storage_name eq 'documento1.pdf'
As buscas podem ser:
Full-Text Search – Busca textual.
Faceted Search – Com filtros por campos.
Semantic Search – Se ativado, usa compreensão semântica além da busca por palavra-chave.




