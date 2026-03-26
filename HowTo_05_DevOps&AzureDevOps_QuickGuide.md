# DevOps & Azure DevOps Quick Guide

>**Assuntos abordados nesse Quick Guide**
>>1. Fluxo do DevOps
>>2. Detalhamento das 8 Fases do Ciclo DevOps
>>3. Azure DevOps
>>4. Azure DevOps: Mapeamento de Proprietários vs. Ferramentas
>>5. Azure DevOps: Do Backlog à Produção

---

<font color="#4169E1" size=5px><b>1. Fluxo do DevOps</b></font>

<figure align="center">
  <img src="imgs/DevOps.jpeg" alt="DevOps" width="800">
  <figcaption>Figura 1: Representação do Fluxo do DevOps</figcaption>
</figure>

---
<font color="#4169E1" size=5px><b>2. Detalhamento das 8 Fases do Ciclo DevOps</b></font>

|Fase|O que acontece na prática (Detalhamento)|Ferramentas Conceito|Exemplos Populares|
|:--|:--|:--|:--|
|**1. Planejar (Plan)**|Definição de requisitos, criação de user stories e organização do backlog. É onde o time decide o que será feito no próximo sprint e como o sucesso será medido|Gestão de tarefas, backlog, colaboração e roadmaps.|Jira, Trello, Azure Boards, Slack.|
|**2. Codificar (Code)**|O desenvolvimento do código propriamente dito. Inclui o uso de branches (como GitFlow) para organizar o trabalho em equipe e revisões de código (Code Reviews) para garantir qualidade|IDEs, Controle de Versão (VCS) e Repositórios|Git (GitHub/GitLab), VS Code, IntelliJ|
|**3. Construir (Build)**|O código é compilado e transformado em um artefato executável (como um arquivo .jar, .exe ou uma imagem Docker). Aqui, as dependências externas são resolvidas e validadas|Compilação, gerenciamento de dependências e artefatos|Maven, Gradle, Docker (Build), npm|
|**4. Testar (Test)**|Execução automatizada de testes (unitários, integrados e de UI). O objetivo é encontrar bugs antes que cheguem à produção. Se um teste falha, o processo para imediatamente|Testes unitários, integrados, de carga e segurança (SAST)|JUnit, Selenium, SonarQube, PyTest|
|**5. Liberar (Release)**|Fase de "empacotamento" final. O artefato aprovado nos testes recebe uma versão (Ex: v1.2.0) e é armazenado em um repositório pronto para ser enviado ao ambiente de destino|Orquestração de CI/CD e aprovação de entrega|Jenkins, GitHub Actions, GitLab CI, CircleCI|
|**6. Implantar (Deploy)**|A infraestrutura é preparada (via IaC) e o código é instalado nos servidores ou clusters. É aqui que aplicamos estratégias como Blue-Green ou Canary para evitar quedas|Infraestrutura como Código (IaC) e Gerenciamento de Configuração|Terraform, Ansible, Kubernetes, Helm|
|**7. Operar (Operate)**|Gestão da aplicação em execução. Inclui o auto-escalonamento (subir mais servidores se houver muito acesso) e a gestão de patches de segurança e backups em tempo real|Orquestração de containers e manutenção em produção|Kubernetes (K8s), Docker Swarm, AWS ECS|
|**8. Monitorar (Monitor)**|Coleta de logs e métricas (Uso de CPU, memória, tempo de resposta). Se algo sai do esperado, o sistema gera alertas para que o ciclo recomece na fase de Planejamento|Coleta de logs, métricas de performance e alertas|Prometheus, Grafana, ELK Stack (Elasticsearch), Datadog|

----

<font color="#4169E1" size=5px><b>3. Azure DevOps</b></font>

>O Azure DevOps é uma das plataformas mais robustas do mercado justamente por ser "ponta a ponta", mas ele adota uma postura de plataforma aberta. Isso significa que, embora ele tenha ferramentas nativas para quase tudo, ele é desenhado para se integrar com o que há de melhor no mercado (best-of-breed).
>
>O Azure DevOps cobre tecnicamente todas as 8 fases, porém a profundidade varia. Nas fases de Operar e Monitorar, ele atua mais como um orquestrador que se integra profundamente ao Azure Monitor e ao Azure Portal (que fazem parte do ecossistema Microsoft Cloud, mas são serviços separados do "Azure DevOps" propriamente dito).

**Azure DevOps x As 8 Fases do DevOps**

|As 8 Fases DevOps|Azure DevOps (Ferramenta Interna)|Considerações Azure DevOps|Integração Externa|
|:--|:--|:--|:--|
|**1. Planejar (Plan)**|Azure Boards (Backlogs, Sprints, Kanban)|**Fases 1 a 6:** O Azure DevOps é soberano.<br> Você consegue fazer tudo dentro da ferramenta sem sair dela, usando o Boards, Repos e Pipelines.|Jira, Trello, Slack, Microsoft Teams.|
|**2. Codificar (Code)**|Azure Repos (Git/TFVC)||GitHub, GitLab, Bitbucket, VS Code.|
|**3. Construir (Buld)**|Azure Pipelines (Build agents)||Jenkins, Maven, Gradle, Docker Hub.|
|**4. Testar (Test)**|Azure Test Plans (Manuais/Exploratórios)||Selenium, JUnit, SonarQube, Playwright.|
|**5. Liberar (Release)**|Azure Pipelines (Release management)||Octopus Deploy, GitHub Actions.|
|**6. Implantar (Deploy)**|Azure Pipelines / Environments||Terraform, Ansible, Kubernetes (Helm).|
|**7. Operar (Operate)**|Azure Pipelines (via Gates/Checks)|**Fase 7 (Operar):**<br>O Azure DevOps não "roda" a aplicação. <br>Ele gerencia o processo de implantação e a infraestrutura. <br>A operação real acontece no provedor de nuvem (Azure, AWS) ou servidores locais.|Kubernetes, Azure App Service, AWS, GCP.|
|**8. Monitorar (Monitor)**|Integrado ao Azure Monitor/Insights|**Fase 8 (Monitorar):**<br> O Azure DevOps exibe painéis de qualidade e sucesso de deploy, mas a monitoração de telemetria (se o site está lento ou caiu) é geralmente feita pelo Azure Monitor ou Application Insights, que enviam dados de volta para o Azure DevOps para gerar novos itens no Boards.|Grafana, Datadog, New Relic, Splunk.|

---

<font color="#4169E1" size=5px><b>4. Azure DevOps: Mapeamento de Proprietários vs. Ferramentas</b></font>

|Proprietário (Dono)|Ferramentas Correspondentes|
|:--|:--|
|Microsoft|Azure DevOps (Boards, Repos, Pipelines, Test Plans), <br>GitHub, VS Code, MS Teams, Azure App Service.|
|Atlassian|Jira, Trello, Bitbucket.|
|Salesforce|Slack.|
|GitLab Inc.|GitLab.|
|CloudBees / Comunidade|Jenkins.|
|Apache Software Foundation|Maven, Gradle (Comunidade), JMeter.|
|Docker (Mirantis/Docker Inc.)|Docker Hub.|
|Software Freedom Conservancy|Selenium.|
|Sonarsource|SonarQube.|
|Google|Kubernetes (K8s), GCP (Google Cloud Platform).|
|Octopus Deploy|Octopus Deploy.|
|HashiCorp|Terraform.|
|Red Hat (IBM)|Ansible.|
|Cloud Native Computing (CNCF)|Kubernetes, Helm, Prometheus.|
|Amazon|AWS (Amazon Web Services).|
|Grafana Labs|Grafana.|
|Datadog Inc.|Datadog.|
|Cisco|Splunk (adquirida recentemente).|
|New Relic Inc.|New Relic.|

>|**Consolidação**|**Open Source**|**O Conceito de "Lock-in"**|
>|:--|:--|:--|
>|Note que a Microsoft possui uma presença massiva, cobrindo desde o planejamento até o monitoramento, especialmente após a aquisição do GitHub.|Muitas ferramentas como Kubernetes e Terraform nasceram dentro de grandes empresas (Google e HashiCorp, respectivamente), mas hoje são mantidas por fundações ou comunidades globais, o que garante maior neutralidade na integração.|Um ponto importante ao escolher ferramentas proprietárias como o Azure DevOps é o Vendor Lock-in. Isso significa que, quanto mais usa funcionalidades exclusivas da Microsoft, mais difícil (e caro) será migrar para outro fornecedor no futuro. Em contrapartida, ferramentas baseadas em padrões abertos (como o Terraform para infraestrutura) permitem que mude de nuvem (da Azure para a AWS, por exemplo) com muito menos esforço.|

---
<font color="#4169E1" size=5px><b>5. Azure DevOps: Do Backlog à Produção</b></font>

| Ordem | Fase DevOps | Atividade no Azure DevOps | Opção no Azure DevOps | Descrição |Destaques Estratégicos|
| :--- | :--- | :--- | :--- |:--|:--|
| **1** | Plan | Criar o Projeto e selecionar **SCRUM** |Organization Settings => Projects | Configuração inicial do ambiente e definição do modelo de trabalho.<br>Definição do contêiner do projeto e do *Work Item Process* como Scrum. |* ***Rastreabilidade Total:*** Ao usar o processo SCRUM, cada linha de código (Fase Code) está conectada a uma Task (Fase Plan), que por sua vez está monitorada em produção (Fase Monitor).|
| **2** | Plan | Definir o **Product Backlog** (Epics/Features) |Boards => Backlogs| Cadastro das grandes necessidades do negócio no **Azure Boards**.<br>Inserção de *Epics* e *Features* que representam o valor de negócio. |
| **3** | Plan | Realizar a **Sprint Planning** (Stories/Tasks) | Boards => Sprints|Quebra dos itens de backlog em tarefas menores para o ciclo atual.<br>Distribuição de *Product Backlog Items* e criação de *Tasks* para o time. |
| **4** | Code | Criar o Repositório no **Azure Repos** | Repos => Files|Inicialização do controle de versão (Git) para receber o código.<br>Criação do repositório Git para versionamento do código-fonte. |
| **5** | Code | Criar **Branches** a partir de Work Items | Boards => Work Items (dentro do item)|Vinculação direta entre a tarefa do Board e o código sendo escrito.<br>Uso do link "Create branch" dentro da Task para manter a rastreabilidade. |* ***Rastreabilidade (O "Pulo do Gato"):***, ao criar a branch de dentro do *Work Item*, o Azure DevOps vincula automaticamente o código ao requisito. Isso permite que, na fase de **Monitor**, você saiba exatamente qual tarefa gerou um eventual erro em produção.|
| **6** | Code | Realizar o **Pull Request (PR)** | Repos => Pull Requests|Revisão de código por pares antes de integrar na branch principal.<br>Criação do PR para que outros desenvolvedores validem a implementação. |
| **7** | Build | Configurar o **Azure Pipeline (CI)** | Pipelines => Pipelines|Criação do arquivo `azure-pipelines.yml` para automação.<br>Configuração do arquivo YAML que automatiza a compilação do código. |
| **8** | Build | Executar a Compilação e Gerar Artefato |Pipelines => Runs |Transformação do código em um pacote pronto para execução.<br>Visualização do log de execução e download do pacote (drop) gerado. |
| **9** | Test | Executar **Testes Unitários** no Pipeline |Pipelines => Tests |Verificação automática da lógica do código durante o Build.<br>Aba de resultados dentro do Pipeline que mostra o sucesso dos testes unitários. |
| **10** | Test | Criar e rodar **Azure Test Plans** | Test Plans => Test Plans|Execução de testes manuais ou exploratórios de interface e aceitação.<br>Criação de suítes de teste para validação humana ou exploratória. |* ***A "Mágica" do Gatilho:*** No Azure DevOps, o fim da fase de **Test** dispara automaticamente a fase de **Release**, garantindo que apenas código validado siga adiante.|
| **11** | Release | Definir o **Pipeline de Release** (CD) |Pipelines => Releases |Mapeamento dos estágios (Dev, Homolog, Prod) e aprovações.<br>Configuração visual das etapas de aprovação e promoção entre ambientes. |
| **12** | Release | Armazenar o Artefato no **Azure Artifacts** |Artifacts => Feeds |Gestão de versões de pacotes e dependências de forma segura.<br>Armazenamento de pacotes NuGet, NPM ou Maven de forma versionada. |
| **13** | Deploy | Configurar **Service Connections** | Project Settings => Service connections|Autorização para o Azure DevOps "falar" com a nuvem (Azure/AWS).<br>Cadastro das credenciais de acesso ao Azure, AWS ou Kubernetes. |
| **14** | Deploy | Executar a Implantação nos **Environments** |Pipelines => Environments |Entrega do código nos servidores usando estratégias de deploy.<br>Definição e monitoramento dos servidores de destino (Dev, QA, Prod). |* ***Ambientes:*** Utilize o recurso **Environments** para criar aprovações manuais. Assim, o código só chega em Produção se um "Dono do Produto" (Product Owner) clicar em "Aprovar" dentro do Azure DevOps.|
| **15** | Operate | Configurar **Post-deployment Gates** |Pipelines => Releases (Gates) |Verificações automáticas de saúde logo após a aplicação subir.<br>Configuração de alertas do Azure Monitor como "travas" para o deploy. |
| **16** | Operate | Gerenciar Infraestrutura (IaC/Scale) | Pipelines => Library|Ajuste de recursos e escalonamento conforme a demanda de uso.<br>Uso de *Variable Groups* e *Secure Files* para gerenciar scripts Terraform/Ansible. |
| **17** | Monitor | Configurar o **Application Insights** | Azure Monitor => App Insights **(via Portal Azure)**|Coleta de telemetria, erros e performance do sistema em tempo real.<br>Monitoramento de performance e exceções integradas à aplicação. |
| **18** | Monitor | Gerar **Dashboards** no Azure DevOps | Overview => Dashboards|Visualização de métricas de saúde que alimentam o próximo **Plan**.<br>Criação de widgets que mostram a saúde do projeto e velocidade do time. |* ***O Ciclo se Fecha:*** O feedback gerado no **Application Insights** (Monitor) vira automaticamente um "Bug" ou uma "User Story" no **Azure Boards** (Plan), reiniciando o roteiro de forma contínua.<BR>* ***Dashboards:*** Você pode configurar um dashboard que mostre tanto o "Burndown Chart" (Scrum) quanto a taxa de sucesso dos deploys (DevOps) em uma única tela.|