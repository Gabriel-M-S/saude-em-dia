# Projeto de Arquitetura do Sistema Saúde em Dia

## Objetivo
Criar uma solução escalável, modular e de fácil manutenção para o gerenciamento de informações médicas, como cadastro de pacientes, agendamentos de consultas e geração de relatórios.

---

## Padrão Arquitetural
### Arquitetura em Camadas com Padrão MVC
1. **Camada de Apresentação (View)**:
   - **Descrição**: Responsável pela interface com o usuário, tanto em aplicações web quanto em aplicativos móveis.
   - **Ferramentas**: React.js para front-end, integração com APIs REST.
2. **Camada de Lógica de Negócios (Controller e Model)**:
   - **Descrição**: Implementação das regras de negócio e validação.
   - **Ferramentas**: Node.js/Express para gerenciamento de rotas e lógica de negócio.
3. **Camada de Acesso a Dados**:
   - **Descrição**: Gerenciamento da persistência e recuperação de dados.
   - **Ferramentas**: MongoDB para armazenamento de dados e Mongoose para comunicação com o banco.

---

## Casos de Uso

| Caso de Uso               | Ator             | Descrição                                                      |
|---------------------------|------------------|----------------------------------------------------------------|
| Cadastro de Pacientes     | Administrador    | Permitir o registro de pacientes com dados pessoais e médicos. |
| Agendamento de Consultas  | Paciente/Admin   | Agendar consultas com médicos disponíveis.                     |
| Consulta de Prontuários   | Médico           | Visualizar e editar informações do histórico médico.           |
| Notificações de Consulta  | Sistema          | Enviar lembretes automáticos sobre consultas.                  |
| Geração de Relatórios     | Administrador    | Gerar relatórios detalhados sobre consultas e desempenho.      |

---

## Protótipos (Telas do Sistema)

1. **Tela de Login**
   - **Entradas**: E-mail/CPF e senha.
   - **Saída**: Autenticação e acesso às funcionalidades do sistema.
   - **Componentes**: Formulário, botão de login e mensagens de erro.

2. **Tela de Dashboard**
   - **Descrição**: Resumo de consultas agendadas, notificações e atalhos para cadastro e relatórios.
   - **Componentes**: Cards de resumo, gráficos e botões.

3. **Tela de Cadastro de Pacientes**
   - **Descrição**: Formulário para dados pessoais e médicos.
   - **Campos**: Nome, CPF, Data de Nascimento, Contato, Histórico Médico.
   - **Componentes**: Botões de salvar e limpar.

4. **Tela de Agendamento**
   - **Descrição**: Seleção de médico, data e horário.
   - **Componentes**: Dropdowns, calendário e botões de confirmação.

5. **Tela de Relatórios**
   - **Descrição**: Filtros para selecionar período e tipo de relatório.
   - **Componentes**: Filtros, botões de exportação (PDF/Excel).

---

## Modelo de Domínio

### Diagrama UML de Classes
As classes principais do sistema e suas relações são representadas abaixo:

1. **Paciente**
   - **Atributos**: `id`, `nome`, `cpf`, `dataNascimento`, `contato`, `historicoMedico`.
   - **Métodos**: `cadastrar()`, `editarDados()`.

2. **Consulta**
   - **Atributos**: `id`, `paciente`, `medico`, `data`, `horario`, `status`.
   - **Métodos**: `agendar()`, `cancelar()`, `confirmar()`.

3. **Médico**
   - **Atributos**: `id`, `nome`, `especialidade`, `crm`, `agenda`.
   - **Métodos**: `atualizarAgenda()`, `consultarProntuario()`.

4. **Administrador**
   - **Atributos**: `id`, `nome`, `permissoes`.
   - **Métodos**: `gerarRelatorios()`.

5. **SistemaNotificacao**
   - **Atributos**: `tipo`, `data`, `paciente`.
   - **Métodos**: `enviarNotificacao()`.

---

## Classificação de Padrões de Arquitetura

O projeto utiliza uma **Arquitetura em Camadas** com **MVC** para segmentação e **Cliente-Servidor** para distribuição:

1. **Camada de Apresentação**:
   - Interface do usuário via web ou mobile.
2. **Camada de Negócios**:
   - API REST que processa as requisições.
3. **Camada de Dados**:
   - Banco de dados centralizado para persistência.

---

## Implementação na Wiki

1. **Página 1**: Introdução ao projeto e escolha dos padrões.
2. **Página 2**: Casos de uso detalhados.
3. **Página 3**: Protótipos das telas (com imagens/screenshot).
4. **Página 4**: Diagrama UML do modelo de domínio.
5. **Página 5**: Estrutura arquitetural detalhada.

---

Se precisar de ajuda para ajustar o conteúdo, adicionar imagens ou gerar mais diagramas, entre em contato!
