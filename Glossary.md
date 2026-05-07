### A
*   **API (Application Programming Interface):** É a parte de uma aplicação encarregada da comunicação com outras aplicações; em microsserviços, as APIs permitem que diferentes serviços compartilhem informações e funcionem de forma integrada.
*   **API Gateway:** Uma camada intermediária que atua como um proxy reverso para os clientes, gerenciando o roteamento de solicitações para diversos microsserviços, além de lidar com autenticação, segurança e cache.
*   **Arquitetura Monolítica:** Modelo unificado onde todos os processos de uma aplicação são **fortemente acoplados** e executados como um único serviço; alterações em um componente exigem a reintegração e implantação de todo o sistema.
*   **Arquitetura de Microsserviços:** Estilo arquitetural que decompõe uma aplicação em um conjunto de **serviços pequenos e independentes**, que se comunicam via protocolos leves (como HTTP/REST) e são organizados por capacidades de negócio.

### B
*   **Bounded Context (Contexto Delimitado):** Conceito originário do *Domain-Driven Design* (DDD) que define os limites de um serviço com base em domínios de negócio exclusivos, garantindo que cada serviço tenha uma responsabilidade clara.

### C
*   **Circuit Breaker (Disjuntor):** Mecanismo de proteção que detecta falhas ou lentidão excessiva em um serviço; ele "abre o circuito" para interromper chamadas a esse serviço, forçando uma falha rápida e evitando que o problema derrube outros sistemas em cascata.
*   **Consistência Eventual:** Modelo de consistência comum em sistemas distribuídos onde os dados podem não estar sincronizados instantaneamente em todos os lugares, mas o sistema garante que, após um tempo, todas as réplicas estarão consistentes.
*   **Containers (Docker):** Tecnologia que empacota o código e suas dependências em unidades leves, facilitando a execução de microsserviços em diferentes ambientes sem conflitos de infraestrutura.

### D
*   **DevOps:** Conjunto de práticas e cultura que une desenvolvimento e operações, sendo considerado essencial para gerenciar a complexidade, automação e monitoramento exigidos pelos microsserviços.

### E
*   **Escalabilidade:** Capacidade de um sistema lidar com o crescimento da demanda; em microsserviços, é possível escalar **individualmente** apenas os serviços que apresentam picos de carga, economizando recursos.

### I
*   **Idempotência:** Propriedade que garante que uma operação **não seja processada mais de uma vez**, mesmo que a requisição seja repetida devido a falhas ou retentativas (*retries*) no sistema.

### K
*   **Kubernetes:** Plataforma de orquestração de containers que automatiza o gerenciamento, a implantação e a escala de aplicações baseadas em microsserviços.

### P
*   **Padrão Strangler (Estrangulamento):** Estratégia de migração que consiste em substituir gradualmente as funcionalidades de um monólito por novos microsserviços, até que o sistema antigo seja completamente desativado.
*   **Persistência Poliglota:** Prática de permitir que cada microsserviço utilize a **tecnologia de banco de dados mais adequada** para sua função específica (ex: SQL para transações, NoSQL para buscas rápidas), em vez de forçar um único banco centralizado.

### R
*   **Regra das Duas Pizzas:** Diretriz de gerenciamento (popularizada pela Amazon) que sugere que as equipes de microsserviços devem ser pequenas o suficiente para serem alimentadas por duas pizzas grandes, garantindo agilidade e autonomia.
*   **Resiliência:** Capacidade de um sistema continuar operando ou se recuperar rapidamente de falhas parciais; microsserviços bem projetados evitam que a falha de um serviço interrompa a aplicação inteira.

### S
*   **SAGA Pattern:** Padrão para gerenciar transações distribuídas, dividindo uma grande operação de negócio em uma **sequência de microtransações locais** coordenadas por eventos ou mensagens.
*   **SOA (Arquitetura Orientada a Serviços):** Antecessor dos microsserviços focado na integração de sistemas em toda a empresa, geralmente utilizando tecnologias de integração pesadas como o Barramento de Serviços Corporativos (ESB).
