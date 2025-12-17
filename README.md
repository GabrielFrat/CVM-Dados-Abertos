# CVMetrics API - Dados Abertos CVM

## Sumário
1. [Visão e Escopo do Projeto](#visão-e-escopo-do-projeto)  
2. [Plano do Projeto](#plano-do-projeto)  
3. [Requisitos de Software](#requisitos-de-software)  
4. [Diagramas](#diagramas)  

---

## Visão e Escopo do Projeto

### 1.1. Descrição do problema  
Este projeto tem como objetivo a criação de uma API para consulta de dados financeiros e contábeis extraídos do portal de dados abertos da CVM (dados.cvm.gov.br).

### 1.2. Stakeholders  
Qualquer pessoa ligada à economia ou mercado financeiro.

### 1.3. Usuários  
Qualquer pessoa ligada à economia ou mercado financeiro.

### 1.4. Riscos  
- Instabilidades ou mudanças na estrutura dos dados do portal da CVM  
- Alto volume de requisições pode sobrecarregar banco e servidor  
- Possíveis falhas ou indisponibilidade do Firebase  
- Riscos de ataques hackers visando roubo ou corrupção de dados  
- Custos maiores do que o esperado com Cloudflare, Firebase e servidores  

### 1.5. Premissas  
- Extração periódica dos dados do portal da CVM  
- Armazenamento em banco MySQL  
- API em Python (FastAPI), hospedada com SSL para segurança  
- Autenticação via Basic Auth gerenciada pelo Firebase  
- Infraestrutura protegida com Cloudflare e NGINX para proxy reverso  

### 1.6. Visão da solução  
Reunir e flexibilizar a consulta de dados contábeis e indicadores financeiros para investidores e instituições, possibilitando futuras análises e classificações de desempenho das empresas.

---

## Plano do Projeto

### 2.1. Declaração de trabalho  
**Features do produto:**  
| Feature               | Descrição                                |
|-----------------------|------------------------------------------|
| Dados contábeis       | Consulta de Passivos e Ativos da empresa listada |
| Indicadores Financeiros | Consulta de dados como ROE, PL, EBITDA, etc. |

**Produtos de trabalho:**  
- Requisitos Funcionais e Não Funcionais  
- Casos de Uso  
- Diagramas de Caso de Uso e Sequência  
- Documentação Final  
- Produto  

### 2.2. Recursos materiais

#### 2.2.1. Recursos de Hardware  
- Máquina Oracle Server para banco de dados: 2 OCPUs, 12GB RAM  
- Máquina Ubuntu para API: 1 OCPU, 6GB RAM  

#### 2.2.2. Recursos de Software  
| Aplicação | Descrição | Versão | Impacto |
|-----------|------------|---------|---------|
| MySQL     | Banco de dados dedicado | 8.0.1 | Alto |
| Python (FastAPI) | API desenvolvida em Python com FastAPI | 3.10 | Alto |
| NGINX     | Proxy reverso e comunicação com servidor | - | Alto |
| Cloudflare | Domínio e segurança contra bots | - | Alto |
| CloudPanel | Ambiente visual do servidor | - | Médio |
| Firebase  | Autenticação e gerenciamento de usuários | - | Médio |
| PuTTy     | Acesso via terminal aos servidores | - | Baixo |

---

## Requisitos de Software

### 3.1. Casos de Uso  
- **CSU001**: Consulta de empresas listadas com indicadores financeiros e contábeis por período anual ou trimestral.  
- **CSU002**: Consulta de indicadores financeiros específicos, como ROA, ROE, PL, por período anual ou trimestral.

### 3.2. Regras de Negócio  
*(Não incluídas neste README conforme solicitado)*

### 3.3. Requisitos Funcionais  
| Nº   | Descrição                                                    | Caso de Uso |
|------|--------------------------------------------------------------|-------------|
| RF001 | Consulta dados brutos como DRE, DRA, BPA etc.                | CSU001      |
| RF002 | Consulta por períodos anuais                                  | CSU001      |
| RF003 | Consulta por períodos trimestrais                            | CSU001      |
| RF004 | Consulta indicadores financeiros como ROE, EBITDA, PL etc.   | CSU001      |
| RF005 | Consulta informações gerais como Setor, Segmento, CNPJ       | CSU001      |

### 3.4. Requisitos Não Funcionais  
| Nº     | Descrição                                  | Categoria      |
|--------|--------------------------------------------|----------------|
| RNF001 | API disponível 24/7                         | Disponibilidade |
| RNF002 | Domínio com proteção contra ataques DDoS   | Segurança      |
| RNF003 | Dados retornados em formato JSON            | Usabilidade    |
| RNF004 | Validação de login do usuário               | Segurança      |
| RNF005 | Resposta da API em até 20ms                  | Disponibilidade |
| RNF006 | Logs de consulta armazenados em banco       | Segurança      |
| RNF007 | Banco acessado somente via chave SSL         | Segurança      |

---

## Diagramas

### 4.1. Topologia da API  
<p align="center">
  <img src="./Imagens/Diagrama Topologia-Topologia-Topologia.drawio (1).png" alt="Topologia Dados CVM" width="900">
</p>


### 4.2. Diagrama de Classes

---

## Contato  
Para dúvidas, sugestões ou caso queira testar a API, entre em contato com gabrierfrat@gmail.com;

---

*Projeto desenvolvido para consulta de dados abertos da CVM, facilitando acesso a indicadores financeiros e contábeis por meio de API segura e eficiente.*
