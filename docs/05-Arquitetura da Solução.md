# Arquitetura da Solução

## Introdução

Nesta seção, vamos descrever a arquitetura da solução para o sistema financeiro, incluindo os principais componentes do sistema, as tecnologias utilizadas, o ambiente de hospedagem e as diretrizes de qualidade de software.

## Componentes da Solução

O sistema financeiro será composto pelos seguintes componentes:

- **Frontend Web**: Interface de usuário acessível por navegadores web. Desenvolvido utilizando Angular.
- **Frontend Mobile**: Interface de usuário acessível por dispositivos móveis. Desenvolvido utilizando React Native.
- **Backend API**: Responsável por fornecer os dados para o frontend e executar a lógica de negócios. Desenvolvido em C# utilizando ASP.NET Core.
- **Banco de Dados**: Armazenará os dados do sistema. Utilizaremos o MongoDB, um banco de dados NoSQL.

## Tecnologias Utilizadas

- **Linguagens**: C# para a API, Script para o frontend (web e mobile).
- **Frameworks**: ASP.NET Core para o backend, Angular para o frontend web, React Native para o frontend mobile.
- **Banco de Dados**: MongoDB
- **Ferramentas de Desenvolvimento**: Visual Studio para C#, Visual Studio Code para Script.
- **Ferramentas de Versionamento**: Git e GitHub.
 
## Arquitetura Distribuída

A arquitetura distribuída adotada para o sistema financeiro permite que cada microsserviço, como Sistema Financeiro, Categoria, Receita, Despesa e Usuário, seja desenvolvido, implantado e escalado independentemente. Essa abordagem facilita a manutenção e a evolução contínua do sistema. A API de Gateway atua como uma camada de abstração entre os clientes e os microsserviços, simplificando o acesso aos recursos e garantindo a segurança e o controle das solicitações. Além disso, cada microsserviço possui seu próprio banco de dados, garantindo a segregação de dados e permitindo uma melhor escalabilidade e desempenho.

![Diagrama de Arquitetura](img/apibackend.png)

## Hospedagem

A aplicação será hospedada em um servidor na nuvem, como o Azure para a API e o GitHub Pages para o frontend web.

## Qualidade de Software

Considerando as diretrizes da norma ISO/IEC 25010, nossa equipe selecionou as seguintes subcaracterísticas de qualidade para nortear o desenvolvimento do projeto do sistema financeiro:

1. **Confiabilidade**:
   - Métricas: Taxa de falhas, tempo médio entre falhas.

2. **Manutenibilidade**:
   - Métricas: Tempo médio para correção de bugs, facilidade de extensão do código.

3. **Desempenho**:
   - Métricas: Tempo de resposta da API, tempo de carregamento das páginas web e mobile.

4. **Usabilidade**:
   - Métricas: Tempo de aprendizado do usuário, taxa de conclusão de tarefas.

5. **Segurança**:
   - Métricas: Nível de vulnerabilidades identificadas, tempo médio para correção de vulnerabilidades.
     
## Considerações Finais

A arquitetura da solução foi cuidadosamente planejada para atender às necessidades do sistema financeiro, garantindo um alto padrão de qualidade, desempenho e segurança. A utilização de tecnologias modernas e práticas recomendadas garantirá a eficiência e escalabilidade do sistema.

## Modelo ER

Entidades:
- Despesa
- Categoria
- SistemaFinanceiro
- UsuarioSistemaFinanceiro
- **Receita**

Relacionamentos:
- Uma Despesa pertence a uma Categoria
- Uma Receita pertence a uma Categoria
- Uma Categoria é associada a um SistemaFinanceiro
- Um UsuarioSistemaFinanceiro é associado a um SistemaFinanceiro

## Esquema Relacional

Tabelas:
- Despesa (Id, Nome, Valor, Mes, Ano, TipoDespesa, DataCadastro, DataAlteracao, DataPagamento, DataVencimento, Pago, DespesaAtrasada, CategoriaId)
- Categoria (Id, Nome, SistemaId)
- Receita (Id, Nome, Valor, Mes, Ano, TipoReceita, DataCadastro, DataAlteracao, DataRecebimento, CategoriaId)
- SistemaFinanceiro (Id, Nome, Mes, Ano, DiaFechamento, GerarCopiaDespesa, MesCopia, AnoCopia)
- UsuarioSistemaFinanceiro (Id, EmailUsuario, Administrador, SistemaAtual, SistemaId)
