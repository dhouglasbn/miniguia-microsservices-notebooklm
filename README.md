# 🚀 Microsserviços com NotebookLM

<p align="center">
  <img src="https://img.shields.io/badge/Status-Concluído-success?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Foco-Arquitetura%20de%20Software-blue?style=for-the-badge" />
  <img src="https://img.shields.io/badge/IA-NotebookLM-purple?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Autor-Dhouglas%20Nóbrega-orange?style=for-the-badge" />
</p>

---

## 📌 Sobre o Projeto

Este projeto é um **Caderno Temático estruturado** sobre **Arquitetura de Microsserviços**, construído com apoio do NotebookLM.

Mais do que um resumo teórico, este repositório demonstra:

- 🧠 Pensamento crítico aplicado ao estudo técnico
- 📚 Curadoria de fontes confiáveis
- 🤖 Engenharia de prompts com IA
- 🔍 Capacidade de síntese e organização do conhecimento

---

## 🎯 Objetivos

- Entender os fundamentos de microsserviços
- Comparar com arquitetura monolítica
- Explorar padrões como **Idempotência** e **SAGA Pattern**
- Desenvolver habilidades práticas com IA aplicada ao aprendizado

---

## 📚 Curadoria de Fontes

### 📄 Artigos

- [Arquitetura de Microsserviços — Melissa Tidori](https://revista.fatectq.edu.br/interfacetecnologica/article/download/1186/669/5482)
- https://www.redhat.com/pt-br/topics/microservices/what-are-microservices
- https://aws.amazon.com/pt/microservices/
- https://www.ibm.com/br-pt/think/topics/microservices

### 🎥 Vídeos

- https://www.youtube.com/watch?v=3MmYWUIBHZM
- https://www.youtube.com/watch?v=eftbQXnR4Y0

---

## 🧠 Engenharia de Prompts

### 💬 Exemplo 1

**Pergunta:**

> Qual a diferença entre monólito e microsserviços?

**Resposta:**

> A principal diferença entre um sistema monolítico e um de microsserviços reside na forma como os componentes são estruturados, acoplados e gerenciados. Enquanto o monólito é construído como uma unidade única e indivisível, os microsserviços são uma coleção de serviços independentes que trabalham juntos.
> Abaixo, detalho as principais distinções baseadas nas fontes:
>
> 1. Estrutura e Acoplamento
>
> - Monolítico: Todos os processos são fortemente acoplados e executados como um único serviço. Se um componente precisar de atualização, todo o sistema deve ser reescrito ou reinplantado.
> - Microsserviços: A aplicação é desmembrada em componentes independentes e fracamente acoplados. Cada serviço foca em uma funcionalidade de negócio específica (como um carrinho de compras ou pesquisa) e comunica-se com os outros através de APIs leves ou mensageria.
>
> 2. Gerenciamento de Dados
>
> - Monolítico: Utiliza geralmente um único banco de dados centralizado para todas as funcionalidades.
> - Microsserviços: Cada serviço possui seu próprio banco de dados, o que garante total independência. Isso permite a "persistência poliglota", onde cada serviço usa a tecnologia de banco de dados mais adequada à sua tarefa.
>
> 3. Escalabilidade e Resiliência
>
> - Monolítico: Para lidar com um pico de demanda em uma função específica, toda a arquitetura deve ser escalada horizontalmente, o que pode gerar desperdício de recursos. Além disso, a falha de um único componente pode derrubar a aplicação inteira.
> - Microsserviços: Permitem a escalabilidade flexível, onde apenas o serviço sobrecarregado é replicado. Em termos de resiliência, se um serviço falhar, o restante da aplicação pode continuar funcionando normalmente, degradando apenas a funcionalidade afetada.
>
> 4. Ciclo de Desenvolvimento e Tecnologia
>
> - Monolítico: O time fica preso a uma única stack tecnológica (linguagem e framework) para todo o projeto. O deploy é feito como uma unidade única, o que se torna arriscado e lento à medida que o sistema cresce.
> - Microsserviços: Oferecem liberdade tecnológica, permitindo o uso de diferentes linguagens e frameworks para cada serviço. Os serviços podem ser desenvolvidos, testados e implantados de forma independente, acelerando o tempo de introdução de novos recursos no mercado.
>
> 5. Complexidade e Gestão
>
> - Monolítico: É mais simples de desenvolver, testar e implantar inicialmente, sendo recomendado para sistemas que ainda não atingiram um alto nível de complexidade.
> - Microsserviços: Introduzem uma complexidade significativamente maior na gestão. Exigem investimentos pesados em automação (DevOps), monitoramento centralizado, rastreamento de logs e tratamento de falhas de rede, já que se tornam sistemas distribuídos

---

### 💬 Exemplo 2

**Pergunta:**

> O que é idempotência?

**Resposta:**

> A idempotência é a capacidade de evitar que uma operação seja executada mais de uma vez caso ocorra uma falha durante o processamento e ela precise ser reexecutada. Em arquiteturas de microsserviços, esse conceito é fundamental porque as aplicações são projetadas para serem tolerantes a falhas, o que significa que, se um serviço ou banco de dados estiver offline, o sistema realizará retentativas automáticas. Sem a idempotência, essas retentativas poderiam causar efeitos colaterais graves, como gerar duas cobranças para o mesmo cliente por causa de uma falha de rede após o primeiro processamento bem-sucedido.
> </br></br> Para garantir que uma operação seja idempotente, geralmente utiliza-se um identificador único (ID) que acompanha a requisição. Na prática, funciona da seguinte forma:
>
> - Ao realizar um pagamento, o sistema envia para o provedor (como o Stripe) o ID do pedido correspondente.
> - Se o pagamento for processado, mas o sistema falhar antes de registrar o sucesso no banco de dados, uma nova tentativa será feita.
> - Ao receber a segunda requisição com o mesmo ID, o serviço reconhece que aquela transação já foi realizada e não a processa novamente, evitando a duplicidade.
>   </br></br> Dessa forma, a idempotência assegura a integridade dos dados em sistemas distribuídos, garantindo que o resultado final seja o mesmo, independentemente de quantas vezes a operação seja chamada devido a falhas técnicas.

---

### 💬 Exemplo 3

**Pergunta:**

> Explique o SAGA Pattern

**Resposta:**

> O **SAGA Pattern** é um padrão de projeto utilizado para gerenciar **transações distribuídas** que envolvem múltiplos microsserviços. Em arquiteturas de microsserviços, como cada serviço possui seu próprio banco de dados, não é possível utilizar transações ACID tradicionais (como em monólitos) para garantir a integridade dos dados entre diferentes sistemas.
> Abaixo estão os pontos principais para entender como o SAGA funciona:
>
> 1. **Divisão em Microtransações**
>    </br>O princípio básico do SAGA é que uma grande transação de negócio (ex: "Criar Pedido") é quebrada em uma sequência de pequenas transações locais, chamadas de microtransações. Cada uma dessas transações atualiza o banco de dados de um único serviço e dispara um evento ou mensagem para iniciar a próxima etapa.
> 2. **Funcionamento Baseado em Eventos**
>    </br>Diferente de uma abordagem síncrona, onde um serviço chamaria vários outros via API REST e esperaria a resposta, o SAGA geralmente utiliza uma comunicação **assíncrona e orientada a eventos**:
>
> - **Exemplo Prático**: Quando um usuário faz um pedido, o sistema cria o registro com o status **"Pendente"** em vez de "Criado".
> - Um evento (ex: "Pedido Preenchido") é enviado para um message broker.
> - O **Serviço de Estoque** ouve esse evento, verifica se há produtos e emite um novo evento (ex: "Estoque Disponível").
> - O Serviço de Pedidos ouve a confirmação e altera o status final para "Criado".
>
> 3. **Por que usar o SAGA?**
>
> - **Consistência Eventual**: Como não há uma transação única bloqueando todos os bancos de dados, o sistema garante que os dados estarão consistentes ao final do processo, o que é chamado de consistência eventual.
> - **Tolerância a Falhas**: Ele evita que o sistema fique travado caso um dos serviços esteja lento ou offline, permitindo que o fluxo seja processado conforme os serviços ficam disponíveis.
> - **Escalabilidade**: Permite que transações complexas ocorram em um ambiente distribuído sem gerar gargalos de performance que ocorreriam em transações síncronas pesadas.
>   </br></br>**Diferença Importante**
>   </br>É fundamental não confundir o **SAGA Pattern** com a **Idempotência**. Enquanto o SAGA gerencia o fluxo de uma transação entre vários serviços, a idempotência garante que, se uma dessas etapas falhar e precisar de uma retentativa, ela não seja processada duas vezes (evitando, por exemplo, cobrar o cliente duas vezes pelo mesmo pedido).

---

## ⚠️ Aprendizados Reais (Cicatrizes)

✔️ Respostas de IA precisam ser refinadas  
✔️ Nem sempre a primeira resposta é a melhor  
✔️ Prompt bem feito = resposta melhor  
✔️ Conceitos complexos exigem múltiplas fontes

---

## 📄 Resumo

> A arquitetura de software é o mapeamento dos componentes de um sistema, funcionando como o projeto de uma casa que garante desempenho, robustez e facilidade de manutenção. Atualmente, o mercado divide-se principalmente entre dois estilos: o **monolítico** e os microsserviços.
>
> 1. Monólito vs. Microsserviços
>    </br>**Arquitetura Monolítica:** É um modelo unificado onde todos os processos estão **fortemente acoplados** e executam como um único serviço. Embora seja simples de desenvolver, testar e implantar inicialmente, torna-se complexa e arriscada à medida que cresce, pois qualquer atualização exige que todo o sistema seja reinplantado.
>    </br>**Arquitetura de Microsserviços:** A aplicação é desmembrada em componentes **independentes e especializados**, que se comunicam via APIs leves (como REST) ou mensageria. Cada serviço foca em uma função de negócio e possui seu próprio banco de dados, permitindo a chamada persistência poliglota (uso de diferentes tecnologias de banco de dados para cada necessidade).
> 2. **Três Pilares da Resiliência**
>    </br>Para que um sistema distribuído funcione corretamente, três conceitos são fundamentais:
>
> - **Idempotência**: Garante que uma operação não seja processada mais de uma vez em caso de retentativas após falhas. É essencial para evitar erros como cobranças duplicadas em pagamentos.
> - **SAGA Pattern:** Resolve o desafio de transações que envolvem múltiplos serviços. Em vez de uma transação única, o fluxo é quebrado em **microtransações sequenciais** coordenadas por eventos, garantindo a consistência eventual dos dados.
> - **Circuit Breaker (Disjuntor):** Atua como uma proteção que detecta quando um serviço está lento ou offline. Ele "abre o circuito" para **falhar rapidamente**, evitando que a lentidão de um componente (como uma API externa) derrube todo o ecossistema em cascata.
>
> 3. **Vantagens e Desafios**
>
> - **Benefícios:** Oferece escalabilidade flexível (escalar apenas o que é necessário), liberdade tecnológica (usar diferentes linguagens) e maior agilidade para as equipes, que ganham autonomia sobre seus serviços.
> - **Desafios:** A complexidade aumenta drasticamente. Sistemas distribuídos exigem investimentos pesados em DevOps, monitoramento centralizado, rastreamento de logs e tratamento de falhas de rede.
>
> 4. **Boas Práticas de Implementação**
>    </br>As fontes recomendam **não começar um projeto diretamente com microsserviços**, mas sim evoluir para eles quando o monólito se tornar pesado demais para gerenciar. Para a transição, utiliza-se frequentemente o **Padrão Strangler**, onde novas funcionalidades são criadas como microsserviços que gradualmente "estrangulam" e substituem o sistema antigo. Além disso, o uso de **Containers (Docker) e Orquestradores (Kubernetes)** é considerado essencial para gerenciar a escala e a implantação desses serviços.

---

## 🔁 Prompts reutilizáveis

```
Quais são os pilares da arquitetura de microsserviços?
```

```
Como implementar idempotência?
```

```
Como implementar Pattern SAGA?
```

```
Como implementar Circuit Breaker?
```

```
Como configurar um API Gateway?
```

```
Quando é realmente desenvolver microsserviços ao invés de monolítico?
```

---

## 📈 Próximos Passos

- Implementar microsserviços na prática
- Usar Docker e Kubernetes
- Explorar Circuit Breaker e API Gateway
- Criar um projeto real baseado nesse estudo

---

## 👨‍💻 Autor

**Dhouglas Bandeira Nóbrega**

💡 Interessado em Arquitetura de Software, IA aplicada e Engenharia de Sistemas

---

<p align="center">
  Feito com 💻 + ☕ + curiosidade
</p>
