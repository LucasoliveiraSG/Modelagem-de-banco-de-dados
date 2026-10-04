# Entrega 1 — Modelo Conceitual (DER)
### Modelagem de um sistema de gestão de informações para uma organização de pequeno porte

> Este arquivo é o esqueleto do **README.md** do repositório GitHub do seu grupo.
> Preencha cada seção abaixo. Não apague os títulos — apenas substitua as instruções em *itálico* pelo conteúdo do seu projeto.
> O **DER** é anexado separadamente ao repositório (em imagem), mas sua justificativa entra neste README.
>
> **A organização escolhida pode ser de qualquer natureza:** empresa com fins lucrativos (livraria, lanchonete, pet shop), ONG, associação comunitária, cooperativa, instituições religiosas/comunitárias como igrejas, terreiros de religiões de matriz africana (candomblé, umbanda) ou outras. O que muda de um tipo para outro são os processos e as regras específicas — a estrutura do trabalho (levantamento de requisitos, modelagem conceitual, DER) é a mesma para todas. Termos como "empresa" e "negócio" usados abaixo devem ser lidos de forma ampla, no sentido técnico de modelagem de dados (ex.: "regras de negócio" = regras de funcionamento da organização, seja ela comercial, religiosa ou social).
>
> **Importante:** a organização precisa **existir de fato** — não é permitido inventar uma organização fictícia. O levantamento de requisitos e regras de negócio deve ser feito por meio de **pesquisa de campo na própria organização** (visitas, entrevistas com responsáveis, observação dos processos reais), então o grupo só deve escolher uma organização à qual **realmente tenha acesso**. Ao escolher, tomem cuidado com o porte: **nem tão pequena** que não gere dados suficiente para o trabalho (poucos processos, poucas entidades), **nem tão grande/complexa** que fique inviável de modelar nesta primeira etapa do curso.

---

## Metadados

| Nome do Aluno(a) | RGM |
| :--- | :---: |
|  *Carolina Ayumi Kawakami Faria*  | *47927470* |
| *Lucas Oliveira da Silva* | *48323667* |
| *Lucas Silva de Morais* | *48040843* |
| *Alex Christini dos Santos* | *47919833* |

## 1. Caracterização da Organização

- **Nome e natureza da organização:** O objeto de estudo selecionado para esta modelagem relacional é a **Forno Lusitano**, uma empresa de pequeno/médio porte pertencente ao setor de alimentação e gastronomia, operando sob o regime de fins lucrativos. Localizada estrategicamente no bairro Lajeado, a instituição acumula funções híbridas de panificadora, confeitaria e restaurante na modalidade de *self-service*. Para assegurar a eficiência no atendimento ao público, o estabelecimento possui o espaço físico compartimentado em setores funcionais bem delimitados, compreendendo: área de copa, balcão de bebidas, seção especializada de pães e doces, e o setor de laticínios e frios.
- **Contexto e porte:** A operação comercial ocorre de forma intensiva e contínua, funcionando de segunda a segunda, das 07:00h às 22:00h. Para suportar essa jornada de alta demanda, a empresa conta com um quadro efetivo de 25 colaboradores distribuídos em turnos de revezamento. O fluxo de clientes é expressivo, registrando uma circulação diária estimada entre 500 pessoas, das quais aproximadamente 350 realizam consumo ou aquisição direta de produtos, gerando um volume considerável de transações diárias.
- **Problemas e necessidades identificados:** Conforme levantamento realizado no local por meio de entrevista com o gerente operacional (Sr. Severino), a organização padece de limitações estruturais em seus fluxos de informação. O processo de atendimento utiliza primariamente comandas físicas para o registro de consumo, sendo os acertos consolidados e liquidados manualmente no caixa ao término do atendimento. A escassez crônica de mão de obra — evidenciada por jornadas exaustivas e momentos em que o próprio gerente precisa acumular funções de atendimento no balcão — resulta em forte gargalo operacional. A dependência de registros em papel e planilhas descentralizadas compromete a integridade e a rastreabilidade dos dados, abrindo margem para inconsistências no controle de estoque, dificuldades na apuração gerencial de faturamento e sobrecarga humana decorrente da ausência de automação transacional.
- **Justificativa da escolha:** A Forno Lusitano revelou-se um caso de estudo ideal para a engenharia de dados devido à complexidade inerente ao seu modelo de negócio misto (varejo de balcão e serviço de alimentação). O ecossistema transacional — que envolve gestão de múltiplos setores de produtos, controle rigoroso de comandas individuais, fechamento de caixa e dimensionamento de fluxo de clientes — fornece a massa crítica e a diversidade relacional necessárias para justificar a construção de um banco de dados relacional robusto, escalável e normalizado.
- **Evidências da organização:** 

  -  **Localização:** 
  Estr. do Lageado Velho, 1012 - Guaianases, São Paulo - SP, 08451-000
  - **Fontes de Dados Primárias (Pesquisa de Campo):** Entrevista semiestruturada conduzida presencialmente com o gerente responsável, Sr. Severino.
  - **Telefone:** 
  (11) 91858-4285
  - **Instagram:**  https://www.instagram.com/padarialusitano/
  - **Registros da visita:**
  - <img width="500" height="350" alt="Image" src="https://github.com/user-attachments/assets/87c7f6da-d2e8-4344-928c-506bfa7a1d4f" />



---

## 2. Processos de Negócio
*(vale 10% — Dimensão Procedimental)*

- **Principais processos mapeados:** *ex.: cadastro de clientes/beneficiários/fiéis, controle de estoque ou doações, vendas ou arrecadação, emissão de pedidos ou solicitações, entregas ou distribuição, organização de eventos/rituais/mutirões.*
- **Fluxogramas:** (Opcional) *represente visualmente pelo menos os processos-chave (imagens anexadas). Deve ficar claro o fluxo de cada processo e como eles se integram entre si.*

---

## 3. Requisitos do Sistema
Nesta seção
### 3.1 Requisitos Funcionais
- **RF01- Cadastrar o cliente:** O sistema deve permitir que haja o cadastro de informações dos clientes, com CPF, endereço, nome. 
- **RF02- Cadastrar produtos:** O sistema deve permitir que haja o cadastro dos produtos com informações dos preços, quantidade e categoria. 
- **RF03- Verificar o estoque:** O sistema deve notificar quando um produto chega a sua quantidade mínima. 
- **RF04- Alterar produtos**- O sistema deve permitir a alteração de preços e quantidade dos produtos.
- **RF05- Registrar comandas**- O sistema deve conter o registro de produtos em comandas.  
- **RF06- Registrar vendas**- O sistema deve permitir que sejam geradas as informações da compra e recibos comprovados.  
- **RF07**-
### 3.2 Requisitos Não Funcionais
- **RFN01- Desempenho:** O sistema deve apresentar um tempo de resposta rápido e garantir que funcione sob uma larga escala de usuários dentro do sistema. 
- **RFN02- Usabilidade:** O sistema deve garantir que sua interface seja clara e objetiva a quem utiliza.
- **RFN03- Segurança:** O sistema deve garantir a criptografia das informações para proteger a privacidade dos consumidores. 
- **RFN04- Portabilidade:** O sistema deve ser compatível aos navegador utilizado. 
- **RFN05- Disponibilidade:** O sistema deve funcionar em horários comerciais e em caso de manutenções exibir informações prévias aos usuários. 
- **RFN06- :**

---

## 4. Regras de Negócio
*(esta seção DIVIDE com a Seção 3 "Requisitos do Sistema" os mesmos 7,5% da dimensão conceitual — juntas valem 7,5%, não 7,5% cada — + 4% exclusivos desta seção na documentação. "Regras de negócio" é o termo técnico usado em modelagem de dados para as regras de funcionamento de qualquer organização, com ou sem fins lucrativos)*

- **Regras operacionais:** *condições que a organização impõe (ex.: "um pedido só pode ser fechado se houver estoque disponível", "uma doação só pode ser registrada com identificação do doador", "um ritual só pode ser agendado se o espaço estiver disponível").*
- **Restrições organizacionais:** *limitações que afetam o modelo (ex.: políticas internas, prazos, exigências legais, normas religiosas ou estatutárias) — e por que elas importam.*

---

## 5. Dicionário de Dados Conceitual (Preliminar)

Os exemplos de valores são fictícios, apenas para ilustrar o tipo de informação.

### [Link para visualização do site de dicionário de dados.](https://hilarious-gumdrop-9fbbc4.netlify.app)

### Entidade: Funcionario

| Atributo | Descrição | Regra de negócio associada |
| :--- | :--- | :--- |
| id_funcionario | Identificador único do funcionário | Obrigatório, chave primária, gerado pelo sistema |
| nome | Nome completo do funcionário | Obrigatório |
| telefone | Telefone de contato do funcionário | Obrigatório; dado sensível, deve ser protegido |
| data_nascimento | Data de nascimento do funcionário | Obrigatório; dado sensível, deve ser protegido |
| CPF | Cadastro de Pessoa Física do funcionário | Obrigatório, único; dado sensível, deve ser protegido |
| cargo | Cargo ou função exercida pelo funcionário | Obrigatório |

### Entidade: Cliente

| Atributo | Descrição | Regra de negócio associada |
| :--- | :--- | :--- |
| id_cliente | Identificador único do cliente | Obrigatório, chave primária (PK), gerado pelo sistema |
| nome | Nome completo do cliente | Obrigatório |
| telefone | Telefone principal para contato | Obrigatório; dado sensível, deve ser protegido |
| id_endereço | Identificador do endereço associado ao cliente | Obrigatório, chave estrangeira (FK) associada ao endereço |
| CPF | Cadastro de Pessoa Física do cliente | Obrigatório, único; dado sensível, deve ser protegido |

### Entidade: Endereco

| Atributo | Descrição | Regra de negócio associada |
| :--- | :--- | :--- |
| id_endereco | Identificador único do endereço | Obrigatório, chave primária, gerado pelo sistema |
| bairro | Nome do bairro | Obrigatório |
| cep | Código de Endereçamento Postal | Obrigatório |
| cidade | Nome da cidade | Obrigatório |

### Entidade: Caixa

| Atributo | Descrição | Regra de negócio associada |
| :--- | :--- | :--- |
| id_caixa | Identificador único do registro de caixa | Obrigatório, chave primária, gerado pelo sistema |
| id_compra | Identificador da compra registrada no caixa | Obrigatório, chave estrangeira associada à compra |
| id_funcionario | Identificador do funcionário responsável pelo caixa | Obrigatório, chave estrangeira associada ao funcionário |
| hora_abertura | Data e hora de abertura do caixa | Obrigatório, gerado automaticamente |
| hora_fechamento | Data e hora de fechamento do caixa | Preenchido no encerramento do expediente/turno |

### Entidade: Pedido

| Atributo | Descrição | Regra de negócio associada |
| :--- | :--- | :--- |
| id_pedido | Identificador único do pedido | Obrigatório, chave primária, gerado pelo sistema |
| id_cliente | Identificador do cliente que realizou o pedido | Obrigatório, chave estrangeira associada ao cliente |
| id_produto | Identificador do produto incluído no pedido | Obrigatório, chave estrangeira associada ao produto |
| horario | Horário em que o pedido foi realizado | Obrigatório, gerado automaticamente |
| id_comanda | Identificador da comanda associada ao pedido | Obrigatório, chave estrangeira associada à comanda |

### Entidade: Produto

| Atributo | Descrição | Regra de negócio associada |
| :--- | :--- | :--- |
| id_produto | Identificador único do produto | Obrigatório, chave primária, gerado pelo sistema |
| nome_produto | Nome comercial do produto | Obrigatório |
| preço | Valor unitário de venda do produto | Obrigatório, deve ser maior que zero |
| categoria_produto | Identificador da categoria à qual o produto pertence | Obrigatório, chave estrangeira associada à categoria |

### Entidade: Categoria

| Atributo | Descrição | Regra de negócio associada |
| :--- | :--- | :--- |
| categoria_produto | Identificador único da categoria do produto | Obrigatório, chave primária, gerado pelo sistema |
| descrição | descrição da categoria | Obrigatório |

### Entidade: Estoque

| Atributo | Descrição | Regra de negócio associada |
| :--- | :--- | :--- |
| id_estoque | Identificador único do registro de estoque | Obrigatório, chave primária, gerado pelo sistema |
| id_produto | Identificador do produto movimentado no estoque | Obrigatório, chave estrangeira associada ao produto |
| tipo_movimentacao | Tipo de movimentação realizada (ex: entrada ou saída) | Obrigatório |
| data | Data em que a movimentação ocorreu | Obrigatório, gerado automaticamente |

### Entidade: Comanda

| Atributo | Descrição | Regra de negócio associada |
| :--- | :--- | :--- |
| id_comanda | Identificador único da comanda | Obrigatório, chave primária, gerado pelo sistema |
| hora_abertura | Data e hora de abertura da comanda | Obrigatório, gerado automaticamente |
| hora_fechamento | Data e hora de fechamento da comanda | Preenchido ao encerrar a conta/comanda |

### Entidade: Compra

| Atributo | Descrição | Regra de negócio associada |
| :--- | :--- | :--- |
| id_compra | Identificador único da compra/pagamento | Obrigatório, chave primária, gerado pelo sistema |
| data_compra | Data de realização da compra | Obrigatório, gerado automaticamente |
| id_comanda | Identificador da comanda paga na compra | Obrigatório, chave estrangeira associada à comanda |
| valor_compra | Valor financeiro total da compra | Obrigatório, calculado a partir dos itens da comanda |
| forma_pagamento | Método de pagamento utilizado (PIX, cartão, dinheiro, etc.) | Obrigatório |
---

## 6. Modelagem Conceitual (Entidades, Atributos, Relacionamentos)
*(vale 7,5% na dimensão conceitual)*

- **Entidades reconhecidas:** *liste e justifique brevemente cada uma.*
- **Atributos e classificações:** *quais atributos pertencem a cada entidade.*
- **Relacionamentos pertinentes:** *como as entidades se conectam.*
- **Restrições e políticas organizacionais aplicadas ao modelo.**

---

## 7. Diagrama Entidade-Relacionamento (DER)
*(vale 20% — é o item de maior peso da entrega)*

- Anexe o DER (em imagem).
- O diagrama deve representar corretamente:
  - Entidades
  - Atributos
  - Relacionamentos
  - **Cardinalidades**
- O modelo deve ser **consistente** e já demonstrar potencial de **escalabilidade e integração** (pensando nas próximas etapas do projeto).

---

## 8. Justificativa Técnica
*(vale 7,5% — sozinho, é o subcritério de maior peso dentro da Dimensão Conceitual)*

*Explique e defenda as decisões de abstração e modelagem tomadas: por que essas entidades, esses atributos, esses relacionamentos e essas cardinalidades — e não outras alternativas possíveis?*

---

## 9. Uso de Inteligência Artificial
*(documentação obrigatória — não é opcional se o grupo usou IA em qualquer etapa: pesquisa, escrita, organização de ideias ou revisão de texto)*

Se o grupo usou alguma ferramenta de IA (ChatGPT, Claude, Gemini, Perplexity etc.) em qualquer parte do trabalho, registre **para cada uso relevante**:

| Item | O que registrar |
|------|------------------|
| **Ferramenta e etapa** | Claude (Anthropic), foi usada para correção do modelo lógico |
| **Motivação** | O grupo buscou melhorar a qualidade do modelo lógico através da correção de possíveis inconsistências. |
| **Prompt(s) utilizados** | "[Imagem do nosso diagrama] Verifique se esse modelo lógico apresenta as informações corretas, caso incorreta explique oque devemos alterar". |
| **Resposta recebida** | Houveram algumas sugestões de melhoria envolvendo algumas entidades como Cliente, produto, caixa e compra. A IA também gerou uma imagem de um modelo lógico revisado. |
| **Fontes consultadas e verificadas** | A IA não citou nenhuna fonte específica. |
| **Trechos rejeitados ou corrigidos** | A IA sugeriu por unir as tabelas de caixa e compra, porem optamos por manter as tabelas separadas, ja que a função da tabela compra serve para armazenar informações sobre as compras realizadas por um cliente e o valor gasto. |
| **Justificativa da escolha final** | Decidimos usar algumas mudanças propostas pela IA, mas mantivemos a estrutura original para garantir a integridade dos dados. |
| **Reflexão crítica** | A IA atuou como um "par revisor" útil para sanar dúvidas pontuais sobre o modelo lógico. No entanto, restringimos seu uso no restante do projeto para evitar dependência tecnológica, garantindo o protagonismo do grupo e o desenvolvimento do nosso raciocínio analítico. |

*Se o grupo não usou nenhuma ferramenta de IA, declare isso explicitamente nesta seção.*

---

## Critérios Atitudinais (20%)
**Estes critérios NÃO constam explicitamente como item de entrega no README.** Eles são avaliados por meio de **Avaliação 360º entre os integrantes do grupo** (cada membro avalia os colegas de equipe) e, no caso da Colaboração, também pela **colaboração equilibrada no histórico de commits** do repositório GitHub — não pela leitura do restante do repositório nem pela apresentação:

- **Participação (5%):** envolvimento nas discussões técnicas e nas decisões do grupo.
- **Comprometimento (5%):** cumprimento de prazos e responsabilidades assumidas.
- **Colaboração (5%):** respeito às contribuições dos colegas, cooperação na construção do projeto e colaboração equilibrada no histórico de commits do repositório GitHub.
- **Autonomia (5%):** busca independente de soluções e proposta de melhorias.

---

## Resumo dos Pesos

| Dimensão | Peso total |
|----------|-----------|
| Conceitual (contexto, requisitos/regras, modelagem, justificativa técnica) | 30% |
| Procedimental (requisitos, fluxogramas, dicionário de dados, DER) | 50% |
| Atitudinal (participação, comprometimento, colaboração, autonomia) | 20% |

**Entrega final:** README.md completo + DER + Dicionário de Dados em HTML (com exceção dos cursos GTI) anexado no repositório GitHub do grupo.
