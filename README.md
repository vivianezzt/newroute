## Sistema de gerenciamento de veículos de entrega

- [x] Sistema de rastreamento de veículos (backend/frontend)
- [x] Cálculos de frete das viagens
- [x] Simulação dos veículos
## Casos de Uso

1. **Dinâmica de funcionamento**

- criação de novas rotas
- Frontend (Next.js)
- Backend (Nest.js) 
- Envio de evento (quando uma rota for criada) para Apache Kafka pelo Backend
- Simulador (Golang - microsserviço) armazenar informação de rota com todos as posições dos veículos.

2. **Cálculo do frete**
- (Simulador Golang) RotaCriada com cálculo do frete
- Disparo de um evento para o Apache Kafka sobre o valor do frete da rota
- Armazenada informação de frete no Backend (Nest.js)
  
3. **Processo de entrega**
- FrontEnd (Next.js) iniciar uma nova entrega, escolher uma rota cadastrada
- Informação enviada para o Backend enviada um evento para o Apache Kafka sobre início de processo de entrega
- Simulador identifica a rota da entrega dispara evento ao Apache informando a posição dos veículos
  
4. Simulando a entrega 
- Simulador (rota iniciada) 
- Publicar de tempos em tempos a posição do veículo
- Informação recebida pelo Backend passando para o frontend as informações da localização dos veículos.
- Conexão aberta entre o Frontend e backend em tempo real com uso do websockets
  
### Tecnologias

- Docker
- Linguagem Go
- Next.js
- Nest.js
- Websockets
- Apache Kafka

## Desenvolvimento de microsserviços com Nest.js

Frontend : 

- [x] Typescript/Javscript
- [x] Nest.js
- [x] Prisma ORM e MongoDB
- [x] Rest 
- [x] Google Maps API

Iniciando o Desenvolvimento

1. Criar o projeto Nest.jsCriar o Banco de dados Mongo e integrar com Prisma ORM
2. Criar rotas REST 
3. Capturar o place_id de um lugar no google MapsColetar rotas cadastradas ou cadastrar novas rotas