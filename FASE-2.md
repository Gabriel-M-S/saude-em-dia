# Especificação e Análise de Requisitos de Software

## 1. Modelo de Processo de Software
**Desenvolvimento Incremental**

- Utiliza uma abordagem ágil que favorece a adaptabilidade e a resposta rápida a mudanças durante o desenvolvimento.
- Implementa funcionalidades em pequenos ciclos, com entregas frequentes e iterações.
- Garante um fluxo constante de feedback dos usuários para aprimoramento contínuo do sistema.

## 2. Stakeholders do Software
A plataforma proposta tem como foco facilitar a comunicação e o acesso a serviços de saúde, contando com a participação de:

- **Pacientes:** Os principais usuários que buscam serviços de saúde acessíveis.
- **Laboratórios e Clínicas:** Provedores que oferecem uma gama de exames e consultas.
- **Equipes de Faturamento e Auditoria:** Responsáveis pela gestão financeira e conformidade regulatória.
- **Atendimento ao Cliente:** Equipe dedicada a prestar suporte e resolver dúvidas dos usuários.
- **Gestores e Diretores:** Tomadores de decisão que asseguram a qualidade e a eficácia dos serviços prestados.

## 3. Técnica de Coleta de Requisitos
**Análise Documental:**

- Estudo de legislações relevantes para o setor de saúde.
- Análise de processos de negócio já existentes e identificação de melhores práticas.

## 4. Requisitos do Software

### Requisitos Funcionais
- **RF1:** O sistema deve facilitar o agendamento de exames e consultas de forma prática para os pacientes.
- **RF2:** Os usuários devem poder comparar preços e serviços oferecidos por diferentes clínicas e laboratórios.
- **RF3:** Confirmações automáticas de agendamentos devem ser enviadas aos pacientes.
- **RF4:** O sistema deve permitir que os usuários gerenciem seus dados pessoais e histórico de agendamentos.
- **RF5:** Informações sobre documentação necessária para cada serviço devem ser disponibilizadas.
- **RF6:** Um canal de atendimento ao cliente deve ser acessível para suporte e esclarecimento de dúvidas.
- **RF7:** Laboratórios e clínicas devem ter a capacidade de atualizar seus preços e disponibilidades em tempo real.
- **RF8:** A gestão de dados financeiros dos usuários deve seguir rigorosamente as normas de segurança e privacidade.

### Requisitos Não Funcionais
- **RNF1:** Os dados pessoais e financeiros devem ser protegidos com criptografia forte.
- **RNF2:** A comunicação entre a aplicação e os provedores de serviços de saúde deve ser realizada por meio de HTTPS.
- **RNF3:** O sistema deve suportar no mínimo 500 agendamentos simultâneos com uma latência média de resposta inferior a 1 segundo.
- **RNF4:** A plataforma deve ser compatível com as versões mais recentes dos navegadores principais (Chrome, Firefox, Edge).
- **RNF5:** O sistema deve garantir uma disponibilidade mensal de 99,5%.
- **RNF6:** Todos os registros de transações devem ser auditáveis e mantidos por, no mínimo, 5 anos.

### Regras de Negócio
- **RN1:** Somente usuários registrados podem realizar agendamentos de serviços de saúde.
- **RN2:** Os preços exibidos devem ser atualizados diariamente pelos provedores.
- **RN3:** Todos os agendamentos devem ser confirmados por meio de um e-mail automático.
- **RN4:** Pacientes devem apresentar a documentação necessária no momento do atendimento.
- **RN5:** O suporte ao cliente deve estar disponível durante o horário comercial, com uma resposta garantida em até 24 horas.




## 6. Histórias de Usuário 

<table border="1" cellpadding="10" cellspacing="0">
  <thead>
    <tr>
      <th>História</th>
      <th>Quem (Who)</th>
      <th>O quê (What)</th>
      <th>Por quê (Why)</th>
      <th>Critérios de Aceitação</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Agendamento de Exames</td>
      <td>Como um <strong>paciente</strong></td>
      <td>Eu quero <strong>agendar exames</strong> de forma fácil</td>
      <td>Para que eu possa <strong>acessar os serviços de saúde</strong> sem complicações</td>
      <td>
        <ul>
          <li>O paciente deve poder selecionar data e horário para o exame.</li>
          <li>O sistema deve enviar uma confirmação por e-mail após o agendamento.</li>
          <li>O paciente deve ter a opção de cancelar ou alterar o agendamento.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>Comparação de Preços</td>
      <td>Como um <strong>paciente</strong></td>
      <td>Eu quero <strong>comparar preços</strong> de diferentes clínicas</td>
      <td>Para que eu possa <strong>escolher a melhor opção</strong> para meu exame</td>
      <td>
        <ul>
          <li>O sistema deve apresentar uma lista de clínicas e preços dos exames.</li>
          <li>Os preços devem ser atualizados diariamente pelos provedores.</li>
          <li>O paciente deve poder filtrar resultados por tipo de exame e localização.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>Acesso a Documentação Necessária</td>
      <td>Como um <strong>paciente</strong></td>
      <td>Eu quero <strong>ter acesso à documentação necessária</strong> para os exames</td>
      <td>Para que eu possa <strong>me preparar adequadamente</strong> para o atendimento</td>
      <td>
        <ul>
          <li>O sistema deve listar a documentação necessária para cada tipo de exame.</li>
          <li>As informações devem ser acessíveis na área do paciente.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>Suporte ao Cliente</td>
      <td>Como um <strong>paciente</strong></td>
      <td>Eu quero <strong>ter acesso ao suporte</strong> em caso de dúvidas</td>
      <td>Para que eu possa <strong>resolver problemas rapidamente</strong></td>
      <td>
        <ul>
          <li>O sistema deve disponibilizar um canal de atendimento via chat ou telefone.</li>
          <li>O tempo de resposta para dúvidas deve ser inferior a 24 horas.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>Integração com Laboratórios</td>
      <td>Como um <strong>gestor de laboratório</strong></td>
      <td>Eu quero <strong>integrar meu sistema</strong> com a plataforma de saúde</td>
      <td>Para que eu possa <strong>atualizar preços e disponibilidades</strong> em tempo real</td>
      <td>
        <ul>
          <li>A plataforma deve permitir a atualização de dados de forma segura.</li>
          <li>As informações devem ser refletidas em tempo real para os pacientes.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td>Acompanhamento de Agendamentos</td>
      <td>Como um <strong>paciente</strong></td>
      <td>Eu quero <strong>acompanhar meus agendamentos</strong> na plataforma</td>
      <td>Para que eu possa <strong>gerenciar melhor minha saúde</strong></td>
      <td>
        <ul>
          <li>O paciente deve ter uma lista de todos os agendamentos futuros.</li>
          <li>O sistema deve enviar lembretes de agendamento 24 horas antes do exame.</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

