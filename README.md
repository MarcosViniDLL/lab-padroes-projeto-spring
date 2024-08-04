# Explorando Padrões de Projetos na Prática com Java

Bem-vindo ao repositório que apresenta implementações práticas dos padrões de projeto explorados no laboratório **"Explorando Padrões de Projetos na Prática com Java"**. Este projeto utiliza o Spring Framework para implementar e demonstrar diversos padrões de design. Os principais padrões explorados são:

- **Singleton**: Garantia de que uma classe tenha apenas uma instância e fornece um ponto global de acesso a ela.
- **Strategy**: Define uma família de algoritmos, encapsula cada um deles e torna-os intercambiáveis. No contexto do Spring, isso pode incluir a forma como os serviços são gerenciados e utilizados.
- **Repository**: Facilita o acesso e a manipulação de dados, abstraindo as operações de persistência em um repositório.
- **Facade**: Fornece uma interface unificada para um conjunto de interfaces em um subsistema, tornando o sistema mais fácil de usar e entender.

## Estrutura do Projeto

O projeto é estruturado da seguinte forma:

### Pasta `controller`

Contém os controladores REST responsáveis por expor a API da aplicação.

- **`ClienteRestController.java`**: Controlador REST para gerenciamento de clientes. Inclui endpoints para operações CRUD (Create, Read, Update, Delete).

### Pasta `model`

Define as entidades e os repositórios usados para persistência de dados.

- **`Cliente.java`**: Entidade representando um cliente, incluindo atributos como `id`, `nome`, e `endereco`.
- **`Endereco.java`**: Entidade representando um endereço, com atributos como `cep`, `logradouro`, `bairro`, etc.

### Pasta `repository`
- **`ClienteRepository.java`**: Repositório para a entidade `Cliente`, extendendo `CrudRepository`.
- **`EnderecoRepository.java`**: Repositório para a entidade `Endereco`, extendendo `CrudRepository`.

### Pasta `service`

Define a lógica de negócios da aplicação e a integração com outros serviços.

- **`ClienteService.java`**: Interface que define os métodos para operações com clientes.
- **`ViaCepService.java`**: Interface para comunicação com a API do ViaCEP usando OpenFeign.
- **`ClienteServiceImpl.java`**: Implementação da interface `ClienteService`, gerenciando a lógica de negócios e integração com a API do ViaCEP.

### Pasta `impl` (dentro de `service`)

Contém a implementação dos serviços.

- **`ClienteServiceImpl.java`**: Implementação dos métodos definidos na interface `ClienteService`.

### Pasta `gof`

Contém a aplicação principal do Spring Boot.

- **`Application.java`**: Classe principal para inicialização da aplicação Spring Boot.

## Como Executar o Projeto

1. **Clone o Repositório**
    ```bash
    git clone https://github.com/seu-usuario/seu-repositorio.git
    cd seu-repositorio
    ```

2. **Configure o Projeto**
    Certifique-se de que você tem o JDK 11 ou superior instalado. O projeto utiliza o Maven para gerenciar dependências.

3. **Execute o Projeto**
    ```bash
    ./mvnw spring-boot:run
    ```

4. **Acesse a API**
    Após iniciar a aplicação, você pode acessar a API nos endpoints definidos, por exemplo:
    - `GET /clientes` - Lista todos os clientes.
    - `POST /clientes` - Adiciona um novo cliente.
    - `PUT /clientes/{id}` - Atualiza um cliente existente.
    - `DELETE /clientes/{id}` - Remove um cliente.

## Dependências

O projeto utiliza as seguintes dependências principais:
- Spring Boot Starter Web
- Spring Data JPA
- H2 Database
- Spring Cloud OpenFeign
