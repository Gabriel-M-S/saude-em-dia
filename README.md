# Saúde em Dia

**Saúde em Dia** é um sistema de gerenciamento médico voltado para facilitar o cadastro de pacientes, agendamento de consultas, consulta de prontuários e geração de relatórios, oferecendo uma solução escalável, modular e de fácil manutenção.

---

## 📂 Veja mais detalhes do Projeto de Arquitetura (Fase 4) na Wiki do repositório:

https://github.com/Gabriel-M-S/saude-em-dia/wiki

## 📋 Funcionalidades

- **Cadastro de Pacientes**: Registro de informações pessoais e médicas dos pacientes.
- **Agendamento de Consultas**: Agendamento com médicos disponíveis, com verificação de horários.
- **Consulta de Prontuários**: Visualização e edição de históricos médicos pelos médicos.
- **Notificações de Consulta**: Lembretes automáticos para pacientes sobre consultas agendadas.
- **Geração de Relatórios**: Relatórios detalhados sobre consultas realizadas e desempenho médico.

---

## 🛠️ Arquitetura do Sistema

O sistema utiliza uma arquitetura em camadas baseada no padrão **Model-View-Controller (MVC)** para organização e escalabilidade:

1. **Camada de Apresentação (View)**:
   - Responsável por exibir os dados ao usuário.
   - Desenvolvido com **React.js** para front-end e design responsivo.
   
2. **Camada de Lógica de Negócio (Controller e Model)**:
   - Implementação de regras de negócio e validações.
   - Desenvolvido em **Node.js** com **Express** para gerenciar rotas e APIs REST.

3. **Camada de Acesso a Dados**:
   - Gerenciamento de persistência de dados.
   - Banco de dados **MongoDB** utilizando **Mongoose** para comunicação.

---

## 🚀 Casos de Uso

| **Caso de Uso**           | **Ator**          | **Descrição**                                                  |
|---------------------------|------------------|----------------------------------------------------------------|
| Cadastro de Pacientes     | Administrador    | Registro de pacientes com dados pessoais e médicos.           |
| Agendamento de Consultas  | Paciente/Admin   | Agendamento com médicos disponíveis.                          |
| Consulta de Prontuários   | Médico           | Visualização e edição de históricos médicos dos pacientes.     |
| Notificações de Consulta  | Sistema          | Envio de lembretes automáticos sobre consultas agendadas.      |
| Geração de Relatórios     | Administrador    | Relatórios sobre consultas realizadas e desempenho médico.     |

---

## 🎨 Protótipos (Telas)

1. **Tela de Login**:
   - Autenticação do usuário com e-mail/CPF e senha.

2. **Dashboard**:
   - Resumo de consultas agendadas, notificações e atalhos para funcionalidades principais.

3. **Tela de Cadastro de Pacientes**:
   - Formulário para inserção de informações pessoais e médicas.

4. **Tela de Agendamento**:
   - Interface para selecionar médico, data e horário.

5. **Tela de Relatórios**:
   - Filtros para seleção de período e tipo de relatório, com gráficos e tabelas exportáveis.

---

## 🛠️ Tecnologias Utilizadas

- **Front-End**: React.js
- **Back-End**: Node.js com Express
- **Banco de Dados**: MongoDB com Mongoose
- **Ferramentas Auxiliares**: Docker para ambientes isolados, Postman para testes de API.

---

