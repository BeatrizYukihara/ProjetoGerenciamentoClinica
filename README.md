## 📋 Projeto: Gestão de Clínicas Médicas

Este projeto é uma plataforma desenvolvida para facilitar o agendamento e o gerenciamento de consultas em clínicas e consultórios médicos. O sistema foi projetado para melhorar a experiência dos pacientes e aumentar a eficiência operacional dos profissionais de saúde, garantindo segurança e confidencialidade dos dados sensíveis.

- Funcionalidades:

    * Para Pacientes:
        - Agendamento Online: Interface intuitiva para marcação de consultas com os profissionais disponíveis.
        - Histórico de Consultas: Visualização das consultas passadas e futuras, com detalhes básicos.
      
    * Para Profissionais de Saúde:
        - Gestão de Horários: Controle total sobre a disponibilidade para consultas e bloqueio de horários específicos.
        - Prontuários Eletrônicos Básicos: Registro e acesso rápido a informações essenciais sobre os pacientes.
      
    * Segurança:
        - Proteção de Dados: Implementação de criptografia para garantir a confidencialidade das informações sensíveis.
        - Autenticação Segura: Login seguro para profissionais e pacientes, garantindo acesso apenas a usuários autorizados.
        - Conformidade com LGPD: Alinhado às diretrizes da Lei Geral de Proteção de Dados para proteger a privacidade dos usuários.
      
    * Tecnologias Utilizadas:
      - Utilizamos tanto de frontend quanto de backend, integrando com banco de dados para registrar nome e email e outras informações do paciente e profissional.


## ⌨️ Pré-requisitos

* Pré-requisitos para rodar o projeto:

```
-> IDEs que rodam Python 3.12.22 (ex: Visual Studio, Google Colab, Spyder, etc)
```


## 🔧 Instalação

Para o programa rodar, é necessário possuir as seguintes bibliotecas de Python:

```
-> cryptography.fernet;
-> abstractmethod;
-> re;
-> sqlite;
-> Flask e suas importações: flash, render_template, request, redirect, url_for, session, jsonify, g
```

* **O back_end do projeto está dividido em 3 partes instaladas separadamente:**
   - -> Uma voltada para as classes (classes.py);
   - -> Uma para o DAO, que faz a conexão com o banco de dados (DAO_BD.py);
   - -> última parte para rodar o código em si, sendo nosso "__main__" (app.py)
 


* **O código do front-end possui várias seções diferentes, tanto em CSS quanto em HTML, listadas:**
   - -> Cadastrar profissional/paciente: cadastrar_paciente.html - cadastrar_profissional.html - cadastrar.css
   - -> Fazer o login: login.html - login.css
   - -> Agendamento de consultas: agendar_consulta.html - agendar_consulta.css
   - -> Mostrar as consultas agendadas para o profissional: consultas_agendadas.html - consultas_agendadas.css
   - -> Mostrar consultas agendadas para o paciente: minhas_consultas.html - minhas_cunsultas.css
   - -> Dashboard do profissional: profissional_dashboard.html - profissional_dashboard.css
   - -> Dashboard do paciente: paciente_dashboard.html - paciente_dashboard.css
   - -> Prontuários: prontuarios.html - prontuarios.css


## ⚙️ Descrição da arquitetura


```
1. Estrutura Geral
Flask: O código utiliza o Flask como framework web, que facilita a criação de aplicações web e APIs.
Modularidade: O código é dividido em diferentes módulos (ou arquivos), cada um responsável por uma parte específica da aplicação, como rotas, lógica de negócio, acesso a dados e validações.
2. Camadas da Arquitetura
a. Camada de Apresentação (View)
Templates: As views são representadas por arquivos HTML que são renderizados pelo Flask. O código utiliza render_template para retornar páginas HTML, como login.html, paciente_dashboard.html, etc.
Rotas: As rotas do Flask (@app.route) definem os endpoints da aplicação, que respondem a requisições HTTP (GET, POST, etc.) e controlam a lógica de renderização das views.
b. Camada de Controle (Controller)
Funções de Rota: As funções decoradas com @app.route atuam como controladores, recebendo requisições, processando dados e retornando respostas. Elas realizam a lógica necessária para autenticar usuários, cadastrar pacientes e profissionais, agendar consultas, etc.
Gerenciamento de Sessão: O Flask gerencia a sessão do usuário, permitindo que informações sobre o usuário autenticado sejam armazenadas e acessadas durante a navegação na aplicação.
c. Camada de Modelo (Model)
Classes de Modelo: As classes de modelo, como Usuario, Consulta, e Prontuario, representam as entidades do sistema. Elas encapsulam os dados e comportamentos relacionados a essas entidades.
Data Access Objects (DAO): O código implementa o padrão DAO através das classes UsuarioDAO, ConsultasDAO, e ProntuarioDAO. Essas classes são responsáveis por interagir com o banco de dados, realizando operações CRUD (Create, Read, Update, Delete).
Banco de Dados: A conexão com o banco de dados SQLite é gerenciada pela classe ConexaoBD, que estabelece a conexão e fornece um cursor para executar consultas.
3. Validações e Lógica de Negócio
Funções de Validação: A lógica de validação, como verificar se um e-mail ou CRM já existe, é centralizada em funções específicas dentro do módulo verificacoes.
Autenticação: A autenticação de usuários é tratada na função autenticar_usuario, que verifica as credenciais do usuário e retorna um objeto Usuario se as credenciais forem válidas.
4. Interação entre Camadas
Fluxo de Dados: O fluxo de dados na aplicação geralmente segue este padrão:
O usuário faz uma requisição (ex: login).
A rota correspondente é acionada, chamando a função do controlador.
O controlador processa a requisição, possivelmente chamando métodos dos DAOs para acessar ou modificar dados no banco.
O controlador retorna uma resposta, que pode ser uma renderização de página ou um JSON, dependendo do tipo de requisição.
5. Segurança
Hash de Senhas: O código utiliza a biblioteca bcrypt para hash de senhas, garantindo que as senhas não sejam armazenadas em texto puro no banco de dados.
Gerenciamento de Sessões: O uso de session do Flask permite que a aplicação mantenha informações sobre o usuário autenticado de forma segura.
6. Escalabilidade e Manutenção
Separação de Preocupações: A separação clara entre as diferentes camadas (view, controller, model) facilita a manutenção e a escalabilidade do código.
Modularidade: A estrutura modular permite que novas funcionalidades sejam adicionadas com relativa facilidade, sem a necessidade de modificar grandes partes do código existente.
```

## 🧷 Medidas de segurança

- O código criptografa a senha do usuário ao registrar, fornecendo uma camada extra de segurança contra acesso indesejados à conta tanto do paciente quanto do profissional.


## ✒️ Autores

* **Beatriz Alves Martins Yukihara** - [Beatriz Yukihara](https://github.com/BeatrizYukihara)
* **Fabrício Kauan Wanderson Santos Alencar** - [Fabrício Alencar](https://github.com/Fabricio-Alencar)
* **Nicoli Cardoso Teles** - [Nicoli Teles](https://github.com/Nicoli-Teles)
* **Samuel Martinez** - [Samuel Martinez](https://github.com/SamuelRomi)


## 🎁 Agradecimentos

* Agradecemos ao [Prof. Nilton Cesar Furtado Canto](https://github.com/niltonmack) pelas aulas e tutoria ao longo da realização do projeto, contando com muita paciência conforme nos auxiliava em tanto períodos letivos como fora dos horários de aula, **MUITO OBRIGADO !! ❤️**

---
