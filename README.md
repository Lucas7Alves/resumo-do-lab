# Resumo do Lab Azure (AZ-900) + Azure Cognitive Search
Este repositório contém o resumo das lições aprendidas durante o desenvolvimento do lab da DIO sobre os conceitos básicos do Microsoft Azure, com foco no exame AZ-900.

---
### 📘 O que é Computação em Nuvem?
A computação em nuvem é o fornecimento de serviços de computação via Internet, oferecendo inovação mais rápida, escalabilidade, flexibilidade e economia de custos. Em vez de comprar e manter infraestrutura física, você acessa recursos de TI sob demanda.

---
### 🔐 Modelo de Responsabilidade Compartilhada
No modelo de nuvem, a responsabilidade pela segurança e conformidade é compartilhada entre o provedor (ex: Microsoft Azure) e o cliente, dependendo do tipo de serviço utilizado (IaaS, PaaS ou SaaS).

---
### ☁️ Modelos de Nuvem
**Nuvem Pública:** Serviços fornecidos por terceiros via Internet, acessíveis ao público. Exemplo: Microsoft Azure.
**Nuvem Privada:** Infraestrutura exclusiva da organização, maior controle e segurança.
**Nuvem Híbrida:** Combinação das duas anteriores, permitindo maior flexibilidade e controle.

---
### 💸 CapEx vs OpEx
**CapEx (Despesas de Capital):** Investimento inicial em hardware e infraestrutura.
**OpEx (Despesas Operacionais):** Pagamento conforme o uso, ideal para escalar serviços em nuvem.

---
### 📊 Modelo Baseado em Consumo
Os provedores de nuvem adotam um modelo de cobrança sob demanda. O usuário paga apenas pelo que consome, o que melhora a previsibilidade de custos e otimiza recursos.

---
### 🛅 Modelos de Serviço em Nuvem
**IaaS (Infrastructure as a Service):** Oferece infraestrutura básica (servidores, armazenamento, rede) como serviço virtualizado. O provedor gerencia hardware, rede e virtualização, enquanto o cliente é responsável por SO, middleware, aplicativos e dados. Exemplos: Azure Virtual Machines, AWS EC2.
**PaaS (Platform as a Service):** Fornece um ambiente pronto para desenvolvimento e implantação de aplicativos, sem gerenciar infraestrutura subjacente. O provedor cuida da infraestrutura, SO e middleware, e o cliente foca no desenvolvimento e gerenciamento de aplicativos. Exemplos: Azure App Services, Google App Engine.
**SaaS (Software as a Service):** Aplicativos completos hospedados e gerenciados pelo provedor, acessados via navegador. O provedor gerencia tudo (infraestrutura, atualizações, segurança), e o cliente apenas usa o software. Exemplos: Microsoft 365, Salesforce, Gmail.

---

#### 🤖 O que é Azure Cognitive Search?
Serviço de busca inteligente que usa IA para indexar e pesquisar dados estruturados/não estruturados.


### 🔍 Mineração do Conhecimento & Azure Cognitive Search
#### ❓ O que é Mineração do Conhecimento?
Processo de extrair padrões e insights de grandes volumes de dados usando IA.
**Importância:** Automatiza descobertas úteis para negócios (ex: tendências, fraudes).

### 📂 Fontes de Dados Suportadas
* Azure SQL Database
* Blob Storage Containers (PDFs, imagens)
* Data Lake Storage Gen2
* Table Storage
* Índice de IA (Dados enriquecidos com processamento de linguagem, OCR, etc.)


### 📄 Formato de Dados
O Azure Cognitive Search aceita JSON como formato primário para indexação.

---
### 🧠 Enriquecimento com IA
**Recursos básicos:**
* Extração de texto (OCR em imagens/PDFs)
* Reconhecimento de entidades (nomes, locais)
* Tradução automática


### 🚀 Passo a Passo: Criar um Recurso Azure Cognitive Search
1.  **Criar Conta Azure**
    * Acesse portal.azure.com.
    * Assine o plano FREE (cartão de crédito necessário, sem custo dentro do limite).
2.  **Criar Recurso**
    * **Grupo de Recursos:** Nomeie (ex: "rg-search-demo").
    * **Nome do Serviço:** Escolha um nome único (ex: "meu-search-ai").
    * **Localização:** East US.
    * **Tipo de Recurso:** AI + Machine Learning -> Azure AI Search.
3.  **Configurar Fonte de Dados**
    * No painel do serviço, vá para "Importar Dados", selecione a fonte (ex: Blob Storage).
    * Conecte-se ao container e mapeie os campos para o índice.
4.  **Enriquecimento com IA (Opcional)**
    * Habilite "Cognitive Skills" durante a importação.
    * Escolha habilidades como "Extração de Texto" ou "Detecção de Idioma".
5.  **Indexar e Consultar**
    * Após a criação do índice, use o "Search Explorer" para testar consultas.
    * **Exemplo de consulta simples:**
        ```json
        {
          "search": "termo_de_busca",
          "filter": "campo eq 'valor'"
        }
        ```


### 📌 Exemplo Prático
**Cenário:** Indexar PDFs de contratos no Blob Storage e buscar por "cláusula de confidencialidade".
* Upload dos PDFs no Blob Storage
* Criar índice com campos: titulo, conteudo, data
* Habilitar OCR para extrair texto dos PDFs.
* **Consultar no Search Explorer:**
    ```json
    { "search": "cláusula de confidencialidade" }
    ```

E prontoo!
Se tiver alguma dúvida pode consultar a documentação do Azure Search também: [Clicando aqui!](https://learn.microsoft.com/pt-br/azure/search/search-what-is-azure-search)
