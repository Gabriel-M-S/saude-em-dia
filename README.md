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

# Detalhamento do Padrão MVC no Projeto Saúde em Dia

O padrão **Model-View-Controller (MVC)** organiza o sistema em três componentes principais para melhorar a separação de responsabilidades e facilitar a manutenção. Abaixo estão os detalhes de como cada componente será implementado no contexto do projeto:

---

## 1. Modelo (Model)
O **Modelo** é responsável por gerenciar os dados e as regras de negócio da aplicação. Ele encapsula as funcionalidades principais e garante a integridade dos dados.

### Responsabilidades no Projeto
- Definir a estrutura dos dados (pacientes, médicos, consultas, etc.).
- Implementar as regras de negócio, como validações de agendamentos ou restrições de horários.
- Comunicar-se com a camada de acesso a dados para persistência.

### Exemplo no Projeto
#### Classes Principais:
1. **Paciente**
   - **Atributos**: `id`, `nome`, `cpf`, `dataNascimento`, `contato`, `historicoMedico`.
   - **Métodos**: `cadastrar()`, `editarDados()`.

2. **Consulta**
   - **Atributos**: `id`, `paciente`, `medico`, `data`, `horario`, `status`.
   - **Métodos**: `agendar()`, `cancelar()`, `confirmar()`.

3. **Notificacao**
   - **Atributos**: `id`, `tipo`, `mensagem`, `paciente`.
   - **Métodos**: `enviar()`, `gerarNotificacaoConsulta()`.

### Exemplo de Função:
```javascript
class Consulta {
    static agendar(pacienteId, medicoId, data, horario) {
        if (!this.validarHorario(horario)) {
            throw new Error('Horário inválido');
        }
        return db.consultas.insert({ pacienteId, medicoId, data, horario, status: 'Agendada' });
    }
    static validarHorario(horario) {
        return horario >= '08:00' && horario <= '18:00';
    }
}

## 2. Visão (View)

A **Visão** é responsável por apresentar os dados ao usuário de maneira amigável e acessível. Ela não contém lógica de negócio, apenas exibe as informações que recebe do controlador.

### Responsabilidades no Projeto
- Renderizar telas da aplicação (web ou mobile) com dados provenientes do Modelo.
- Atualizar a interface do usuário conforme as interações.
- Implementar acessibilidade e design responsivo para dispositivos variados.

### Exemplo no Projeto
#### Telas Principais:
1. **Tela de Login**: Formulário para entrada de e-mail/CPF e senha.
2. **Tela de Cadastro de Pacientes**: Formulário para inserir dados do paciente.
3. **Tela de Agendamento**: Interface com calendário e opções de médicos disponíveis.
4. **Tela de Prontuário**: Exibição de informações médicas do paciente.

### Exemplo de Código Front-End (React.js):
```javascript
function Agendamento({ consultas }) {
    return (
        <div>
            <h1>Agendamentos</h1>
            <ul>
                {consultas.map(consulta => (
                    <li key={consulta.id}>
                        {consulta.data} - {consulta.horario} com Dr. {consulta.medico}
                    </li>
                ))}
            </ul>
        </div>
    );
}

## 3. Controlador (Controller)

O **Controlador** gerencia a interação do usuário e é responsável por processar os eventos de entrada. Ele funciona como um intermediário entre a Visão e o Modelo.

### Responsabilidades no Projeto
- Receber eventos do usuário (cliques, entradas de dados).
- Validar as solicitações e decidir como interagir com o Modelo.
- Enviar os dados adequados para a Visão apresentar.

### Exemplo no Projeto
#### Endpoints Principais:
1. **`/login`**: Valida credenciais do usuário e inicia uma sessão.
2. **`/cadastrarPaciente`**: Recebe dados do formulário e chama o método `cadastrar()` no modelo.
3. **`/agendarConsulta`**: Recebe dados do agendamento e verifica disponibilidade no modelo.

### Exemplo de Código Back-End (Node.js/Express):
```javascript
const express = require('express');
const router = express.Router();
const Consulta = require('./models/Consulta');

router.post('/agendarConsulta', async (req, res) => {
    const { pacienteId, medicoId, data, horario } = req.body;
    try {
        const consulta = await Consulta.agendar(pacienteId, medicoId, data, horario);
        res.status(200).json(consulta);
    } catch (error) {
        res.status(400).json({ error: error.message });
    }
});

module.exports = router;

