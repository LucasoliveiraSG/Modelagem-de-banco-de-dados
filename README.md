# Entrega 1 — Modelo Conceitual (DER)
### Modelagem de um sistema de gestão de informações para uma organização de pequeno porte


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
  - [registro da visita.](comprovante_visita.jpeg)



---

## 2. Processos de Negócio

Nesta seção, descrevem-se os principais fluxos operacionais mapeados na rotina da **Forno Lusitano**, os quais servem como base empírica para a modelagem relacional do banco de dados:

1. **Atendimento e Gestão de Comanda:**
   Processo central de atendimento no salão e balcão. Ao ingressar no estabelecimento, o cliente recebe uma comanda física numerada. A equipe de atendimento anota manualmente todos os itens consumidos (seja na seção de pães e doces, balcão de bebidas, frios ou restaurante *self-service*). A comanda atua como o documento transacional primário que acompanha o cliente até o acerto final.

2. **Controle de Acesso pela Comanda:**
   Mecanismo de controle físico e operacional que regula o fluxo de circulação. A comanda numerada serve como credencial de permanência no salão, sendo exigida obrigatoriamente para a liberação da saída do cliente nas catracas ou portas, atestando que o ciclo de atendimento foi devidamente finalizado.

3. **Abertura e Operação do Caixa:**
   Rotina financeira diária que compreende a inicialização do terminal com o fundo de troco, o registro contínuo das vendas e o fechamento/conciliação ao término do expediente. O operador de caixa recolhe a comanda física, valida os registros, calcula o montante devido e efetua a liquidação financeira (em dinheiro, cartão ou PIX), encerrando o ciclo de venda.

4. **Cadastro de Produtos no Sistema:**
   Processo administrativo e logístico para inserção e atualização do catálogo de mercadorias da padaria e restaurante. Cada item recebe uma descrição, categoria e um código de identificação, permitindo tanto a digitação manual quanto o escaneamento rápido no momento do registro do consumo.

5. **Controle de Estoque:**
   Rotina de gerenciamento e verificação periódica dos insumos e produtos prontos estocados nos diferentes setores (copa, bebidas, pães, doces e laticínios). O processo visa monitorar a disponibilidade de mercadorias para assegurar o abastecimento contínuo e evitar rupturas durante as 15 horas diárias de funcionamento (das 07:00h às 22:00h).

6. **Cadastro de Clientes para Entregas:**
   Processo voltado para o atendimento na modalidade de *delivery* ou encomendas externas. Quando o cliente solicita um pedido fora do salão, a equipe realiza o registro dos dados cadastrais essenciais: **nome, telefone de contato e endereço completo**, garantindo a rastreabilidade logística e o histórico de atendimento.

---

## 3. Requisitos do Sistema
### 3.1 Requisitos Funcionais
- **RF01- Cadastrar o cliente:** O sistema deve permitir que haja o cadastro de informações dos clientes, com CPF, endereço, nome. 
- **RF02- Cadastrar produtos:** O sistema deve permitir que haja o cadastro dos produtos com informações dos preços, quantidade e categoria. 
- **RF03- Verificar o estoque:** O sistema deve notificar quando um produto chega a sua quantidade mínima. 
- **RF04- Alterar produtos**- O sistema deve permitir a alteração de preços e quantidade dos produtos.
- **RF05- Registrar comandas**- O sistema deve conter o registro de produtos em comandas.  
- **RF06- Registrar vendas**- O sistema deve permitir que sejam geradas as informações da compra e recibos comprovados.  

### 3.2 Requisitos Não Funcionais
- **RFN01- Desempenho:** O sistema deve apresentar um tempo de resposta rápido e garantir que funcione sob uma larga escala de usuários dentro do sistema. 
- **RFN02- Usabilidade:** O sistema deve garantir que sua interface seja clara e objetiva a quem utiliza.
- **RFN03- Segurança:** O sistema deve garantir a criptografia das informações para proteger a privacidade dos consumidores. 
- **RFN04- Portabilidade:** O sistema deve ser compatível aos navegador utilizado. 
- **RFN05- Disponibilidade:** O sistema deve funcionar em horários comerciais e em caso de manutenções exibir informações prévias aos usuários. 

---

## 4. Regras de Negócio

- **Regras operacionais:** 

  - Um cliente só pode entrar no estabelecimento se estiver com a comanda em mãos, e só pode pagar a comanda no caixa.
  - O caixa só pode ser aberto por um funcionário autorizado, e só pode ser fechado quando não houver nenhum cliente dentro da loja.
  - Todas as comandas devem ser registradas no sistema, e só podem ser fechadas quando o cliente for pagar a comanda.
  - Um produto só pode ser registrado no sistema se estiver cadastrado no estoque, e só pode ser vendido se houver quantidade suficiente em estoque.
  - Uma comanda só pode ser liberada para um novo cliente após o pagamento total dos itens consumidos.
- **Restrições organizacionais:** 

  - Política de Controle de Acesso e Auditoria: O sistema deve implementar um mecanismo de autenticação robusto, garantindo que apenas funcionários autorizados possam acessar funcionalidades críticas, como abertura e fechamento de caixa, registro de vendas e alterações de estoque.
  - Política de Liquidação Integral (Bloqueio de Reuso de Comanda): O sistema deve impedir que uma comanda seja reutilizada ou reaberta para um novo cliente até que o pagamento integral de todos os itens registrados tenha sido confirmado e processado, assegurando a integridade financeira das transações.
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

### Entidade: pedido

| Atributo | Descrição | Regra de negócio associada |
| :--- | :--- | :--- |
| id_pedido | Identificador único do item do pedido | Obrigatório, chave primária, gerado pelo sistema |
| id_produto | Identificador do produto incluído no item do pedido | Obrigatório, chave estrangeira associada ao produto |
| id_cliente | Identificador do cliente que fez o pedido | Obrigatório, chave estrangeira associada ao cliente |
| horario | Horário do pedido | Obrigatório, gerado automaticamente |

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
| id_pedido | Identificador único do pedido | Obrigatório, chave estrangeira, gerado pelo sistema |
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



- **cliente** - A pessoa que adquire os produtos ou serviços que são oferecidos pelo estabelecimento.
- **funcionário** - Quem trabalha no estabelecimento e atende aos clientes, são responsáveis pelo registro das comandas e do caixa.
- **caixa** - Recebe pagamentos, registra quem operou e confere tudo oque foi recebido no turno.
- **comanda** - Registra oque foi consumido pelo cliente, a comanda é aberta na entrada e é mantida até o pagamento.
- **compra** - Registro financeiro do consumo com o valor total, data de pagamento e forma de pagamento. 
- **produto** - Item vendido pelo estabelecimento, possui preço, cadastro e categoria.
- **categoria** - Classifica os produtos por tipo, como bebidas, sobremesas e salgados.
- **estoque** - Controla a quantidade de produtos disponiveis, e alerta quando um atinge o número minimo.
- **endereco** - Informações de localização de um cliente,sendo utilizado para entregas.

  ### **Relacionamentos pertinentes** 
 - **pedido tem comanda** (1,N) - Todo pedido pertence a uma comanda(1,1),  e uma comanda pode ter vários pedidos (0,N).
 - **funcionário registra comanda** (1,N) - Um funcionário pode registrar várias comandas (0,N), toda comanda e registrada por um funcionário (1,1)
 


- ### **Restrições e políticas organizacionais aplicadas ao modelo.**
   Apenas um funcionário pode operar o caixa por vez sendo obrigatório o registro do fechamento.

  


---

## 7. Diagrama Entidade-Relacionamento (DER).
[DER conceitual.](DER_Conceitual.png)

<img width="500" height="350" alt="Image" src="DER_Conceitual.png"/>

---

## 8. Justificativa Técnica
A criação das entidades, atributos e demais características foram designadas a partir do mapeamento dos processos que ocorrem na Padaria Forno Lusitano. Houveram alterações em alguns campos como, separação e criação de entidades e adição de  atributos com intuito de promover melhorias ao sistema tornando o mais prático e robusto como por exemplo a separação entidades: caixa, compra e comanda.

A entidade forte (independente) **caixa** foi criada com a função de registrar de forma separada todo o lucro que o estabelecimento obteve no turno, com informações de quem foi o responsável por recebê-lo (ID do funcionário), as formas de pagamento utilizadas e  registro da abertura e fechamento do caixa. 

A entidade **compra** foi criada separadamente como forma de registrar o pagamento diferentemente do consumo que é registrado na entidade comanda, a compra só e gerada quando o cliente paga, armazenando os dados de valor, data e a forma que o pagamento foi feito.

A entidade **comanda** foi criada separadamente como forma de registrar o consumo dos clientes, distringuindo-se do pagamento. a comanda é administrada pelos funcionários e possui status que identificam horario de abertura e fechamento como uma forma de controle.


## 9. Uso de Inteligência Artificial

| Item | O que registrar |
|------|------------------|
| **Ferramenta e etapa** | Claude (Anthropic), foi usada para correção do modelo conceitual |
| **Motivação** | O grupo buscou melhorar a qualidade do modelo conceitual através da correção de possíveis inconsistências. |
| **Prompt(s) utilizados** | "[Imagem do nosso diagrama] Verifique se esse modelo conceitual apresenta as informações corretas, caso incorreta explique oque devemos alterar". |
| **Resposta recebida** | Houveram algumas sugestões de melhoria envolvendo algumas entidades como Cliente, produto, caixa e compra. A IA também gerou uma imagem de um modelo conceitual revisado. |
| **Fontes consultadas e verificadas** | A IA não citou nenhuna fonte específica. |
| **Trechos rejeitados ou corrigidos** | A IA sugeriu por unir as tabelas de caixa e compra, porem optamos por manter as tabelas separadas, ja que a função da tabela compra serve para armazenar informações sobre as compras realizadas por um cliente e o valor gasto. |
| **Justificativa da escolha final** | Decidimos usar algumas mudanças propostas pela IA, mas mantivemos a estrutura original para garantir a integridade dos dados. |
| **Reflexão crítica** | A IA atuou como um "par revisor" útil para sanar dúvidas pontuais sobre o modelo conceitual. No entanto, restringimos seu uso no restante do projeto para evitar dependência tecnológica, garantindo o protagonismo do grupo e o desenvolvimento do nosso raciocínio analítico. |


---



## Resumo dos Pesos

| Dimensão | Peso total |
|----------|-----------|
| Conceitual (contexto, requisitos/regras, modelagem, justificativa técnica) | 30% |
| Procedimental (requisitos, fluxogramas, dicionário de dados, DER) | 50% |
| Atitudinal (participação, comprometimento, colaboração, autonomia) | 20% |

**Entrega final:** README.md completo + DER + Dicionário de Dados em HTML (com exceção dos cursos GTI) anexado no repositório GitHub do grupo.
