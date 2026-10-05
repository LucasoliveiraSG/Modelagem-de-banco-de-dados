# Entrega 1 — Modelo Conceitual (DER)
### Modelagem de um sistema de gestão de informações para uma organização de pequeno porte


---

## Metadados

- **Nomes dos alunos e RGM**
- Carolina Ayumi Kawakami Faria - RGM: 47927470

- Lucas Oliveira da Silva - RGM: 48323667

- Lucas Silva de Morais - RGM: 48040843

- Alex Christini dos Santos - RGM: 47919833


## 1. Caracterização da Organização


- **Nome e natureza da organização:**
  Padaria Forno Lusitano, organização com fins lucrativos.
- **Contexto e porte:** Organização com fins lucrativos, de médio porte, recebe diariamente em torno de 500 clientes onde 350 consumem algo do estabelecimento.
- **Problemas e necessidades identificados:** *qual é a "crise operacional" — o que está desorganizado hoje (planilhas soltas, papel, falta de controle de estoque/doações/cadastros, etc.)?*
- **Justificativa da escolha:** A padaria forno Lusitano se mostrou extremamente receptiva para a realização da pesquisa de campo, sua estrutura de porte médio é de tamanho ideal para a realização da modelagem de banco de dados. O responsável pelo estabelecimento, Severino, concordou em participar da entrevista pessoalmente e permitiu que o grupo coletasse as informações necessárias para fins acadêmicos. 
- **Evidências da organização:** 

  -  **Localização:** 
  Estr. do Lageado Velho, 1012 - Guaianases, São Paulo - SP, 08451-000
  - **Telefone:** 
  (11) 91858-4285
  - **Instagram:**  https://www.instagram.com/padarialusitano/
  - **Registros da visita:**



---

## 2. Processos de Negócio
*(vale 10% — Dimensão Procedimental)*

- **Principais processos mapeados:** *ex.: cadastro de clientes/beneficiários/fiéis, controle de estoque ou doações, vendas ou arrecadação, emissão de pedidos ou solicitações, entregas ou distribuição, organização de eventos/rituais/mutirões.*
- **Fluxogramas:** (Opcional) *represente visualmente pelo menos os processos-chave (imagens anexadas). Deve ficar claro o fluxo de cada processo e como eles se integram entre si.*

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
*(esta seção DIVIDE com a Seção 3 "Requisitos do Sistema" os mesmos 7,5% da dimensão conceitual — juntas valem 7,5%, não 7,5% cada — + 4% exclusivos desta seção na documentação. "Regras de negócio" é o termo técnico usado em modelagem de dados para as regras de funcionamento de qualquer organização, com ou sem fins lucrativos)*

- **Regras operacionais:** *condições que a organização impõe (ex.: "um pedido só pode ser fechado se houver estoque disponível", "uma doação só pode ser registrada com identificação do doador", "um ritual só pode ser agendado se o espaço estiver disponível").*
- **Restrições organizacionais:** *limitações que afetam o modelo (ex.: políticas internas, prazos, exigências legais, normas religiosas ou estatutárias) — e por que elas importam.*

---

## 5. Dicionário de Dados Conceitual (Preliminar)
*(vale 10% — Dimensão Procedimental - Segue o modelo do arquivo 02-03g_Exemplo_Dicionario_Dados.pdf)*

Para cada entidade identificada, liste:

| Atributo | Descrição | Regra de negócio associada |
|----------|-----------|------------------------------|
| *nome do atributo* | *o que ele representa* | *se houver alguma regra (obrigatoriedade, valores possíveis, etc.)* |

*Mantenha o dicionário organizado e padronizado (mesmo formato de tabela para todas as entidades).*

**Atenção à privacidade:** se forem usados exemplos de valores para ilustrar os atributos, esses exemplos devem ser **fictícios** — não utilize dados reais de clientes, fiéis, beneficiários, doadores ou funcionários da organização (nomes, CPFs, contatos etc.), mesmo que tenham sido observados durante a pesquisa de campo. Os exemplos devem apenas ser **coerentes com as operações reais** observadas.

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
A criação das entidades, atributos e demais características foram designadas a partir do mapeamento dos processos que ocorrem na Padaria Forno Lusitano. Houveram alterações em alguns campos como, separação e criação de entidades e adição de  atributos com intuito de promover melhorias ao sistema tornando o mais prático e robusto como por exemplo a separação entidades: caixa, compra e comanda.

A entidade forte (independente) **caixa** foi criada com a função de registrar de forma separada todo o lucro que o estabelecimento obteve no turno, com informações de quem foi o responsável por recebê-lo (ID do funcionário), as formas de pagamento utilizadas e  registro da abertura e fechamento do caixa. 

A entidade **compra** foi criada separadamente como forma de registrar o pagamento diferentemente do consumo que é registrado na entidade comanda, a compra só e gerada quando o cliente paga, armazenando os dados de valor, data e a forma que o pagamento foi feito.

A entidade **comanda** foi criada separadamente como forma de registrar o consumo dos clientes, distringuindo-se do pagamento. a comanda é administrada pelos funcionários e possui status que identificam horario de abertura e fechamento como uma forma de controle.


## 9. Uso de Inteligência Artificial
*(documentação obrigatória — não é opcional se o grupo usou IA em qualquer etapa: pesquisa, escrita, organização de ideias ou revisão de texto)*

Se o grupo usou alguma ferramenta de IA (ChatGPT, Claude, Gemini, Perplexity etc.) em qualquer parte do trabalho, registre **para cada uso relevante**:

| Item | O que registrar |
|------|------------------|
| **Ferramenta e etapa** | Qual IA foi usada e em qual parte do trabalho (ex.: pesquisa sobre o setor da organização, redação do README, organização dos requisitos, revisão ortográfica/gramatical). |
| **Motivação** | Por que o grupo recorreu à IA nesse ponto específico. |
| **Prompt(s) utilizados** | Texto exato (ou muito próximo) do que foi perguntado/pedido à IA. |
| **Resposta recebida** | Resumo ou trecho relevante da resposta da IA. |
| **Fontes consultadas e verificadas** | Se a IA citou fontes/dados, quais foram checadas pelo grupo e como (ex.: comparação com o que foi observado na visita de campo). |
| **Trechos rejeitados ou corrigidos** | O que da resposta da IA foi descartado, editado ou corrigido manualmente, e por quê. |
| **Justificativa da escolha final** | Por que o grupo manteve, adaptou ou rejeitou o que a IA sugeriu. |
| **Reflexão crítica** | Limites, vieses ou erros identificados no uso da IA nessa etapa (ex.: informação desatualizada, alucinação, generalização incorreta sobre o tipo de organização). |

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
