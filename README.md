# Construindo-um-Esquema-Conceitual-para-Banco-De-dados
**Esquema Conceitual para Controle de Ordens de Serviço em Oficina Mecânica**

Criando um esquema conceitual para o sistema de controle e gerenciamento de execução de ordens de serviço em uma oficina mecânica. Abaixo estão as entidades, relacionamentos e atributos relevantes:

1. **Cliente**:
    - Representa os clientes que levam seus veículos à oficina.
    - Atributos:
        - **ID do Cliente** (chave primária)
        - **Nome**
        - **Endereço**
        - **E-mail**
        - **Tipo de Cliente** (PF ou PJ)

2. **Veículo**:
    - Representa os veículos trazidos pelos clientes.
    - Atributos:
        - **Placa do Veículo** (chave primária)
        - **Modelo**
        - **Ano**
        - **Tipo de Serviço** (conserto ou revisão periódica)
        - **ID do Cliente** (chave estrangeira referenciando o cliente)

3. **Equipe de Mecânicos**:
    - Representa as equipes responsáveis por executar os serviços nos veículos.
    - Atributos:
        - **ID da Equipe** (chave primária)
        - **Nome da Equipe**
        - **Especialidade** (por exemplo, motor, elétrica, suspensão)

4. **Ordem de Serviço (OS)**:
    - Representa cada serviço solicitado por um cliente para um veículo específico.
    - Atributos:
        - **Número da OS** (chave primária)
        - **Data de Emissão**
        - **Valor Total**
        - **Status** (por exemplo, "Em Processamento", "Concluída", etc.)
        - **Data de Conclusão**
        - **ID do Veículo** (chave estrangeira referenciando o veículo)

5. **Mão-de-Obra**:
    - Tabela de referência para calcular o valor dos serviços.
    - Atributos:
        - **ID da Mão-de-Obra** (chave primária)
        - **Descrição do Serviço**
        - **Valor por Hora**

6. **Peça**:
    - Representa as peças utilizadas nos serviços.
    - Atributos:
        - **ID da Peça** (chave primária)
        - **Descrição da Peça**
        - **Valor Unitário**

Relacionamentos:

- Um cliente pode ter vários veículos (relação 1:N).
- Um veículo pertence a uma equipe de mecânicos (relação N:1).
- Uma ordem de serviço está associada a um veículo (relação N:1).
- Uma ordem de serviço pode ter várias peças e mão-de-obra (relações N:M).
