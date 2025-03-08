# Azure AI Search: Indexação e Consulta Inteligente de Dados

## Sobre este repositório
Este repositório contém recursos, tutoriais e insights sobre a implementação do Azure AI Search (anteriormente conhecido como Azure Cognitive Search) para indexação e consulta eficiente de dados. Os conteúdos aqui apresentados são baseados no módulo "Utilizando AI Search para indexação e consulta de Dados" e incluem um guia passo a passo para configurar uma solução de pesquisa inteligente na plataforma Microsoft Azure.

## Introdução ao Azure AI Search

O Azure AI Search é um serviço de pesquisa-como-serviço (SaaS) da Microsoft que permite criar experiências de pesquisa avançadas em aplicações web, móveis e empresariais. Utilizando inteligência artificial e processamento de linguagem natural, o Azure AI Search vai além da simples correspondência de palavras-chave, oferecendo:

- **Pesquisa Semântica**: Entendimento do significado e intenção das consultas
- **Indexação Multi-Formato**: Capacidade de indexar conteúdo de diferentes tipos e fontes
- **Enriquecimento com IA**: Extração de insights, entidades e sentimentos de dados não estruturados
- **Integração com Azure OpenAI**: Suporte para RAG (Retrieval-Augmented Generation) para melhorar respostas de modelos como GPT
- **Classificação Inteligente**: Algoritmos avançados para priorizar resultados mais relevantes

## Passo a Passo: Configuração do Azure AI Search

### 1. Provisionamento do Serviço

- **Acesse o Portal Azure**: Navegue até [portal.azure.com](https://portal.azure.com)
- **Crie um novo recurso**: Pesquise por "Azure AI Search" e selecione "Criar"
- **Configure os detalhes básicos**:
  - Selecione assinatura e grupo de recursos
  - Defina um nome único para o serviço
  - Escolha uma região (preferencialmente próxima dos seus usuários)
  - Selecione o nível de preço adequado às suas necessidades (Free, Basic, Standard ou Storage Optimized)

### 2. Criação de Origem de Dados

- **Prepare seus dados**: Armazene-os em um serviço compatível como:
  - Azure Blob Storage
  - Azure SQL Database
  - Azure Cosmos DB
  - Azure Table Storage
  - Azure Data Lake Storage Gen2

- **No serviço de pesquisa**: Vá para "Importar dados" e selecione sua fonte de dados
- **Configure as credenciais de conexão** para permitir que o Azure AI Search acesse seus dados

### 3. Criação de Skillsets (Conjunto de Habilidades)

- **Defina um skillset de IA**: Conjunto de habilidades cognitivas para enriquecer seus dados durante a indexação
- **Selecione habilidades cognitivas** como:
  - Extração de entidades e frases-chave
  - Detecção de idioma
  - Reconhecimento de texto em imagens (OCR)
  - Tradução
  - Análise de sentimento
  - Detecção de informações pessoais (PII)

### 4. Definição de Índices

- **Crie um esquema de índice**: Defina a estrutura dos dados pesquisáveis
- **Configure campos e atributos**:
  - Defina quais campos são pesquisáveis, filtráveis, facetáveis, etc.
  - Configure analisadores de texto específicos para diferentes idiomas
  - Defina campos para armazenar os dados enriquecidos pelo skillset

### 5. Configuração de Indexadores

- **Crie um indexador**: Defina como os dados serão extraídos da fonte, processados e carregados no índice
- **Configure programação de execução**: Defina se a indexação será única ou recorrente
- **Mapeie campos**: Defina como os campos da fonte de dados e saídas do skillset serão mapeados para os campos do índice

### 6. Execução e Monitoramento da Indexação

- **Execute o indexador**: Inicie o processo de indexação
- **Monitore o status**: Verifique erros, avisos e estatísticas de processamento
- **Ajuste conforme necessário**: Refine o processo com base nos resultados iniciais

### 7. Implementação da Interface de Busca

- **Desenvolva endpoints de API REST**: Para comunicação com o serviço
- **Implemente consultas básicas e avançadas**:
  - Pesquisa simples de termos
  - Pesquisa com filtros e facetas
  - Pesquisa semântica
  - Pesquisa híbrida (keyword + vetorial)

### 8. Configuração de Pesquisa Semântica

- **Habilite a pesquisa semântica**: Configure o serviço para compreensão contextual das consultas
- **Crie configurações semânticas**: Defina quais campos serão usados para correspondência semântica
- **Configure resposta de legendas**: Permita que o serviço retorne trechos relevantes dos documentos

### 9. Otimização e Monitoramento

- **Configure métricas e logs**: Monitore o desempenho do serviço
- **Analise consultas populares**: Identifique padrões e otimize para casos de uso comuns
- **Ajuste sinônimos e stopwords**: Melhore a qualidade da pesquisa com customizações linguísticas
- **Escale o serviço conforme necessário**: Ajuste o nível de serviço com base no volume de dados e consultas

## Recursos e Capacidades

### Tipos de Pesquisa Suportados

| Tipo de Pesquisa | Descrição | Quando Usar |
|------------------|-----------|-------------|
| Full-text | Busca por correspondência de palavras com suporte a operadores boolianos | Pesquisa geral de conteúdo textual |
| Semântica | Entende o significado da consulta, não apenas palavras-chave | Consultas em linguagem natural complexa |
| Vetorial | Pesquisa por similaridade semântica usando embeddings | Encontrar documentos conceitualmente similares |
| Híbrida | Combina busca por palavras-chave e vetorial | Balancear precisão e recall |
| Filtros e Facetas | Restringe resultados com base em metadados | Refinamento de resultados por categoria, data, etc. |
| Autosugestão | Completa termos enquanto o usuário digita | Melhorar a experiência de usuário e descoberta |

### Recursos de IA para Enriquecimento de Conteúdo

- **Reconhecimento Óptico de Caracteres (OCR)**: Extrai texto de imagens e documentos digitalizados
- **Reconhecimento de Entidades**: Identifica pessoas, locais, organizações, etc.
- **Extração de Frases-Chave**: Determina os principais temas em um documento
- **Detecção de Idioma**: Identifica automaticamente o idioma do texto
- **Análise de Sentimento**: Avalia o tom emocional do texto
- **Tradução**: Converte texto entre idiomas
- **Detecção de PII**: Identifica informações pessoais sensíveis

### Integrações com Ecossistema Azure

- **Azure Blob Storage**: Para indexar documentos, imagens e outros arquivos
- **Azure SQL/Cosmos DB**: Para dados estruturados e semiestruturados
- **Azure Form Recognizer**: Para extração avançada de dados de documentos
- **Azure Computer Vision**: Para análise de imagens
- **Azure OpenAI Service**: Para geração de texto e RAG
- **Azure Active Directory**: Para autenticação e autorização
- **Azure Monitor**: Para telemetria e alertas

## Casos de Uso e Aplicações

### Cenários Empresariais

1. **Portais de Conhecimento Corporativo**
   - Pesquisa unificada em múltiplas fontes de dados
   - Descoberta rápida de documentos e políticas internas
   - Mapeamento automático de conhecimento e especialistas

2. **Atendimento ao Cliente**
   - Sistemas de autoatendimento com pesquisa inteligente
   - Recomendação de artigos relevantes para resolução de problemas
   - Suporte aos agentes com informações contextuais

3. **Comércio Eletrônico**
   - Busca de produtos com compreensão de intenção
   - Recomendações personalizadas baseadas em comportamento
   - Navegação por facetas e filtros intuitivos

4. **Análise de Contratos e Documentos Legais**
   - Extração automática de cláusulas e termos
   - Identificação de inconsistências e riscos
   - Pesquisa rápida em grandes repositórios de documentos

5. **Pesquisa em Dados Médicos**
   - Busca contextual em prontuários e literatura médica
   - Identificação de padrões em dados clínicos
   - Suporte à decisão baseada em evidências

### Exemplos de Projetos Reais

- **Petrobras**: Utilizou Azure AI Search para indexar mais de 1 milhão de documentos técnicos, reduzindo o tempo de pesquisa de horas para segundos
- **Bradesco**: Implementou um assistente virtual utilizando Azure AI Search com RAG para consulta em políticas internas
- **Hospital Sírio-Libanês**: Criou um sistema de busca em prontuários médicos utilizando Azure AI Search com recursos de PII para proteger dados sensíveis

## Insights e Aprendizados

### Desafios e Soluções

| Desafio | Solução |
|---------|---------|
| Dados em múltiplos formatos | Utilize os diferentes indexadores e habilidades cognitivas para normalizar os dados |
| Qualidade dos resultados | Configure a pesquisa semântica e ajuste os parâmetros de relevância |
| Desempenho com grandes volumes | Otimize partições e replicas; considere níveis superiores do serviço |
| Custos crescentes | Monitore e otimize o uso de habilidades cognitivas; use camada de cache |
| Privacidade de dados | Configure encriptação em repouso e chaves gerenciadas pelo cliente |

### Melhores Práticas

1. **Comece com um escopo bem definido**
   - Identifique um caso de uso específico com alto valor de negócio
   - Expanda gradualmente para outros casos de uso

2. **Planeje sua estrutura de dados cuidadosamente**
   - Defina os campos do índice considerando os padrões de consulta
   - Considere campos facetáveis para melhorar a navegação

3. **Otimize o processo de enriquecimento**
   - Use apenas as habilidades cognitivas necessárias para cada caso
   - Armazene dados processados para evitar repetição de análise

4. **Teste exaustivamente com dados reais**
   - Avalie a qualidade dos resultados com consultas típicas
   - Ajuste pesos e configurações com base no feedback

5. **Monitore e ajuste continuamente**
   - Analise logs de consulta para identificar padrões
   - Refine sinônimos e stopwords com base no uso real

### Aprendizados adquiridos

- **Qualidade dos dados de origem é fundamental**: Dados inconsistentes ou mal estruturados afetam diretamente a qualidade da pesquisa
- **Investir tempo na definição do esquema compensa**: Um bom design de índice facilita a manutenção e expansão futura
- **A pesquisa é subjetiva**: A relevância percebida varia entre usuários e contextos; teste com usuários reais
- **Balancear precisão e desempenho**: Mais enriquecimento nem sempre significa melhores resultados, especialmente considerando os custos
- **Hibridismo geralmente supera abordagens puras**: Combinar busca por palavras-chave, filtros e recursos semânticos geralmente oferece os melhores resultados

## Recursos Adicionais

### Documentação Oficial

- [Documentação do Azure AI Search](https://learn.microsoft.com/azure/search/)
- [Quickstarts do Azure AI Search](https://learn.microsoft.com/azure/search/search-get-started-portal)
- [Tutoriais de Indexação e Enriquecimento](https://learn.microsoft.com/azure/search/cognitive-search-tutorial-blob)
- [Referência da API REST](https://learn.microsoft.com/rest/api/searchservice/)

---

## Licença

Este projeto está licenciado sob a licença MIT - veja o arquivo [LICENSE](LICENSE) para detalhes.
