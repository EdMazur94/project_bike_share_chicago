# Como Transformar Usuários Casuais em Assinantes: Uma Análise de Dados do Sistema de Bicicletas Compartilhadas em Chicago

*Pensar em texto introdutório aqui*

## 1. Cenário
  
Uma empresa fictícia de compartilhamento de bicicletas que opera 24 horas por dia na cidade de Chicago, oferecendo diferentes tipos de bicicleta e modalidades de  contratação do seu serviço. Com o objetivo de analisar o comportamento de seus usuários, a empresa disponiblizou os dados de suas viagens entre os meses de **abril de 2024 e abril de 2025** 

Este projeto busca gerar insights que ajudem a equipe de marketing da empresa a compreender as diferenças no comportamento de uso entre usuários casuais e membros anuais, e propor estratégias de marketing que incentivem a conversão de usuários eventuais em assinantes.

## 2. Objetivo do projeto

Embasado na análise dos dados, as seguintes perguntas de negócio devem ser respondidas aos *stakeholders*

- Como os membros anuais e os usuários casuais utilizam as bicicletas?
- Por que os usuários casuais comprariam assinaturas anuais?
- Como se pode usar a mídia digital para influenciar os usuários casuais a se tornarem membros?

## 3. Base de dados

**Fonte** https://divvy-tripdata.s3.amazonaws.com/index.html;

**Período de Análise:** abril de 2024 e abril de 2025;

**Total de Registros** 6.150.909 viagens; 

**Formato** arquivos separados mensalmente em CSV

**Campos utilizdos para análise**: Os seguintes campos foram utilizados para as análises efetuadas neste projeto:

```
- rideable_type: modelo da bicicleta utilizada; 
- started_at: hora e data de ínicio do uso da bicicleta;
- ended_at: hora e data de finalização do uso da bicicleta;
- start_lat: latitude de ínicio do uso da bicicleta; 
- start_lng: longitide de ínicio do uso da bicicleta;
- end_lat: latitude de finalização de uso da bicicleta;
- end_lng: longitude de finalização de uso da bicicleta; 
- member_casual: tipo de usuário da bicicleta.
```
## 4. Metodologia

**Compreensão do Desafio de Negócio**

Entender o impacto que gera cada tipo de cliente foi importante, além de reunir todas as informações e 

### 4.1 Estruturação da Abordagem Analítica

Seguindo o proposto no curso *Google Data Analytics Certificate*, o estudo do projeto foi estruturado em  seis etapas principais:

**Perguntar:** Quais são os 

**Tratamento e Preparação dos Dados**
**Análise Exploratória**
**Visualização**
**Ações Recomendadas**

