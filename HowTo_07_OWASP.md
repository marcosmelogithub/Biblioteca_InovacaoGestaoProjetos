# OWASP Quick Guide


>**Assuntos abordados nesse Quick Guide**
>>1. O que é OWASP
>>2. O acrônimo de OWASP
>>3. OWASP Top 10: Vulnerabilidades Críticas
>>4. Os Pilares de Atuação
>>5. Além do OWASP Top 10
-----
<font color="blue" size=6px><b>1. O que é OWASP</b></font>´

> - Fundação sem fins lucrativos que funciona como uma comunidade aberta e colaborativa.
> - Imagine uma "enciclopédia viva" de segurança, onde especialistas do mundo todo compartilham metodologias, ferramentas e documentações gratuitamente.
> - O diferencial deles é a neutralidade: eles não vendem softwares de segurança, por isso as diretrizes são consideradas o padrão mais honesto e imparcial da indústria.
> - O objetivo principal é ajudar organizações a conceber, desenvolver, adquirir, operar e manter aplicações que possam ser confiadas.

----
<font color="blue" size=6px><b>2. O acrônimo de OWASP</b></font>´

|Acrônimo|O que significa|Descrição|
|:--:|:--|:--|
|**O**|Open| Tudo o que produzem é gratuito e acessível a qualquer pessoa.|
|**W**|Web| O foco histórico e principal são aplicações e tecnologias baseadas na web (embora hoje cubram mobile, API e cloud).|
|**A**|Application| O alvo é a camada de software, não apenas a rede ou o hardware.|
|**S**|Security| O núcleo de todas as atividades.|
|**P**|Project| A fundação é organizada em centenas de projetos individuais (como o "Top 10", o "ZAP" e o "SAMM").|

----

<font color="blue" size=6px><b>3. OWASP Top 10: Vulnerabilidades Críticas</b></font>

>Padrão ouro para entender as vulnerabilidades mais críticas em aplicações web

|Rank|Recomendação|Descrição Breve|
|:--|:--|:--|
|A01|Controle de Acesso Quebrado|Falhas que permitem a usuários acessar dados ou funções fora de suas permissões (ex: acessar conta de outro usuário).|
|A02|Falhas Criptográficas|Exposição de dados sensíveis (senhas, cartões) devido à falta de criptografia ou uso de algoritmos fracos/antigos.|
|A03|Injeção|Ocorre quando dados não confiáveis são enviados a um interpretador (SQL, NoSQL, OS) como parte de um comando ou consulta.|
|A04|Design Inseguro|Foca em falhas de arquitetura. É o risco de não implementar controles de segurança desde a fase de desenho do software.|
|A05|Configuração|Incorreta	Falta de endurecimento (hardening) do sistema, como manter senhas padrão ou mensagens de erro detalhadas demais.|
|A06|Componentes Vulneráveis|Uso de bibliotecas, frameworks ou dependências desatualizadas que possuem buracos de segurança conhecidos.
A07|Falhas de Identificação|Problemas na confirmação da identidade do usuário, como permitir ataques de força bruta ou gestão de sessão ineficiente.|
|A08|Falhas de Integridade|Softwares que não verificam a procedência de atualizações ou dados serializados, permitindo a execução de código malicioso.|
|A09|Falhas de Monitoramento|A falta de logs e alertas eficientes que impede a detecção e a resposta rápida a um ataque em andamento.|
|A10|SSRF|Falsificação de Solicitação do Lado do Servidor, onde o atacante induz a aplicação a fazer requisições para URLs internas ou externas.

---

<font color="blue" size=6px><b>4. Os Pilares de Atuação</b></font>

|Pilar|Descrição|
|:--|:--|
|Conscientização|Através do famoso Top 10, que educa desenvolvedores sobre os riscos mais comuns.|
|Ferramentas|Eles mantêm softwares de código aberto, como o OWASP ZAP (um scanner de vulnerabilidades), para ajudar nos testes de segurança.|
|Padrões e Documentação|Oferecem guias profundos como o ASVS (Padrão de Verificação de Segurança em Aplicações), que serve como um manual técnico detalhado para auditores e desenvolvedores.|

---
<font color="blue" size=6px><b>5. Além do OWASP Top 10</b></font>

>Embora o "Top 10" seja o projeto mais famoso, o OWASP tem mais de 250 projetos ativos que cobrem desde segurança em Inteligência Artificial até segurança em Internet das Coisas (IoT).
