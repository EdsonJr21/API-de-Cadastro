# API de Cadastro de Médicos

> **Status do Projeto**: Em desenvolvimento 🚧

Este projeto é uma API construída com Spring Boot para gerenciar o cadastro de médicos e seus dados pessoais, como endereço e especialidade médica.

## Estrutura do Projeto

- `MedicoController`: Controlador responsável pelo cadastro de médicos.
- `MedicoRepository`: Interface de repositório que utiliza Spring Data JPA para persistir dados médicos.
- `Medico`: Entidade que representa um médico.
- `DadosCadastroMedico`: Classe que define os dados de entrada para o cadastro de um médico, com validações.
- `Endereco`: Classe embutida que define os dados de endereço do médico.
- `DadosEndereco`: Classe de entrada de dados de endereço com validações.
- `Especialidade`: Enum que define especialidades médicas disponíveis.

## Endpoints

### Cadastro de Médicos
- **POST `/medicos`**
    - Cadastra um novo médico com as informações fornecidas.
    - Parâmetro JSON no corpo da requisição:
      ```json
      {
        "nome": "Nome do Médico",
        "email": "email@exemplo.com",
        "telefone": "123456789",
        "crm": "123456",
        "especialidade": "CARDIOLOGIA",
        "endereco": {
          "logradouro": "Rua Exemplo",
          "bairro": "Bairro Exemplo",
          "cep": "12345678",
          "cidade": "Cidade Exemplo",
          "uf": "UF",
          "complemento": "Apartamento X",
          "numero": "123"
        }
      }
      ```
    - Validações:
        - `nome`: Obrigatório.
        - `email`: Formato de e-mail válido.
        - `telefone`: Obrigatório.
        - `crm`: Entre 4 e 6 dígitos.
        - `especialidade`: Deve ser uma das opções definidas em `Especialidade`.
        - `endereco`: Dados obrigatórios para o logradouro, bairro, cep, cidade e uf.

## Tecnologias Utilizadas

- **Java 17**
- **Spring Boot**
- **Spring Data JPA**
- **Jakarta Validation** para validações de dados de entrada
- **Jakarta Transactional** para controle de transações

## Pré-requisitos

1. **Java 17** instalado.
2. **Spring Boot** configurado no ambiente.
3. **Banco de Dados**: Este projeto utiliza um banco de dados relacional (especifique o SGBD em seu `application.properties`).

## Configuração

1. Clone o repositório:
   ```bash
   git clone https://github.com/EdsonJr21/API-de-Cadastro.git
