# 📊 API Interna para Google Sheets com Apps Script

</br >
<div align="center">

[![JavaScript](https://img.shields.io/badge/JavaScript-Code-yellow?logo=javascript)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![Clasp](https://img.shields.io/badge/Clasp-Google%20Apps%20Script-blue?logo=google)](https://github.com/google/clasp)
[![Google Sheets](https://img.shields.io/badge/Google%20Sheets-Spreadsheet-green?logo=google-sheets)](https://developers.google.com/sheets)
[![Node.js](https://img.shields.io/badge/Node. js-Backend-339933?logo=node.js)](https://nodejs.org)
[![Apps Script](https://img.shields.io/badge/Google%20Apps%20Script-Docs-blue?logo=google)](https://developers.google.com/apps-script)

</div>
</br >

### 📝 Descrição

Este projeto implementa uma API interna robusta para Google Sheets, utilizando Google Apps Script e recursos modernos do JavaScript ES6 para executar operações completas de CRUD (criar, ler, atualizar e deletar dados). A arquitetura modular e expansível proporciona gerenciamento eficiente de dados diretamente no ambiente Apps Script, sendo uma solução ideal para automações avançadas em planilhas Google.

### Funcionalidades
#### Operações Disponíveis:
- **Leitura (GET)**: Recupere dados estruturados da planilha
- **Inserção (Push)**: Adicione novos registros à planilha
- **Atualização (updateRowById)**: Modifique dados específicos usando identificadores
- **Exclusão (deleteRowById)**: Remova registros baseando-se em IDs únicos

### Estrutura Central do Código

[![JavaScript](https://img.shields.io/badge/JavaScript-Code-yellow?logo=javascript)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![Apps Script](https://img.shields.io/badge/Google%20Apps%20Script-Docs-blue? logo=google)](https://developers.google.com/apps-script)

```javascript
// JavaScript - Métodos Disponíveis na Classe PlanilhaManager
PlanilhaManager(planilhaId, abaNome)
obterAba(id, name)
getDados(row, colinit, qtcol)
pushDados(array)
updateRowById(idCliente, updates)
deleteRowById(idCliente)
```

### 💡 Exemplos de Implementação

```javascript
// Exemplo 1: getDados(row, colinit, qtcol)
// Recupera dados de um intervalo específico da planilha
function getCliente() {
  const manager = new PlanilhaManager(planilhas.cadastro, abasClientes.clientes)
  const dados = manager.getDados(2, colunasClientes.ID, 6) 
  console.log(dados) // Retorna uma matriz com os dados do intervalo especificado
}
// Parâmetros: `row` (linha de início), `colinit` (coluna inicial), `qtcol` (número de colunas)
// Retorno:  Matriz bidimensional contendo os dados solicitados

// Exemplo 2: pushDados(array)
// Insere uma nova linha de dados na planilha
function pushCliente() {
  const manager = new PlanilhaManager(planilhas.cadastro, abasClientes.clientes)
  const novoCliente = ['1002', 'Carlos', 'Almeida', 'carlos@email.com', 'Male', '987-654-3210']
  manager.pushDados(novoCliente) // Adiciona novo registro ao final da planilha
}
// Parâmetros: `array` contendo os dados do novo cliente
// Ação: Anexa uma nova linha com as informações fornecidas

// Exemplo 3: updateRowById(idCliente, updates)
// Atualiza campos específicos de um registro existente
function editarCliente() {
  const manager = new PlanilhaManager(planilhas.cadastro, abasClientes.clientes)
  const idCliente = 1002
  const updates = {
    [colunasClientes.NOME]:  'Carlos Henrique',
    [colunasClientes. EMAIL]: 'carlos.henrique@email.com'
  }
  manager.updateRowById(idCliente, updates) // Modifica apenas os campos especificados
}
// Parâmetros: `idCliente` (identificador) e `updates` (objeto com colunas e novos valores)
// Ação: Atualiza seletivamente os campos indicados na linha correspondente

// Exemplo 4: deleteRowById(idCliente)
// Remove um registro específico da planilha
function deleteCliente() {
  const manager = new PlanilhaManager(planilhas.cadastro, abasClientes.clientes)
  const idCliente = 1002
  manager.deleteRowById(idCliente) // Elimina o registro do cliente especificado
}
// Parâmetros: `idCliente` para localizar o registro
// Ação: Remove completamente a linha correspondente ao identificador
```

</br >

### 🎯 Arquitetura Escalável

Este projeto adota uma arquitetura altamente escalável ao centralizar toda a manipulação de dados em uma única classe:  **PlanilhaManager** e seus métodos especializados. Essa abordagem oferece benefícios significativos:

- **Simplicidade**: Para qualquer operação (leitura, inserção, atualização ou exclusão), basta instanciar `PlanilhaManager` e invocar o método apropriado
- **Manutenibilidade**: Todas as modificações ou adições são implementadas diretamente nos métodos da classe
- **Organização**: O código permanece estruturado e de fácil compreensão
- **Expansibilidade**:  Novas planilhas ou operações podem ser integradas sem afetar o código existente

</br >

# 📦 Implementação Rápida

### Para utilizar este código em seu projeto, simplesmente copie o conteúdo do arquivo `apisheet.js` e cole no editor do Apps Script

</br >

# 🛠️ Alternativa:  Desenvolvimento com IDE Externa

### 🚀 Pré-requisitos para Clonar o Projeto (Para desenvolvimento em IDE local)

[![Clasp](https://img.shields.io/badge/Clasp-Google%20Apps%20Script-blue?logo=google)](https://github.com/google/clasp)

```
📋 Requisitos:
- Node.js versão 21.7.1 ou superior
- Conta Google ativa com acesso ao Google Sheets e Apps Script
- Clasp (Command Line Apps Script Projects) - https://github.com/google/clasp

🔧 Processo de Configuração: 

1. Clone do Repositório Git:
   Procedimento padrão de clonagem de repositório

2. Autenticação no Clasp:
   Execute:  npm run login
   (Consulte instruções detalhadas no package.json)

3. Clone do Projeto Apps Script:
   a) Substitua o ID do projeto no arquivo package.json
      (localize o campo "clone" e insira o ID do seu projeto Apps Script)
   b) Execute: npm run clone
   c) Isso estabelecerá a conexão entre o Apps Script e seu editor local

4. Configuração Final:
   Será gerado um arquivo .clasp.json dentro da pasta apps
   ⚠️ IMPORTANTE: Mova este arquivo para a raiz do projeto para funcionamento correto

```

</br >
<div align="center">

**Desenvolvido por Sergio Paulo de Andrade** 

</div>
