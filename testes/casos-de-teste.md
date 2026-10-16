# Casos de Teste – Swag Labs

Casos de teste detalhados do projeto. O escopo, os objetivos e o ambiente estão no [Plano de Testes](plano-de-testes.md).

- **Produto:** Swag Labs
- **URL:** https://www.saucedemo.com
- **Navegador:** Google Chrome — 154.0.8037.97
- **Responsável:** Patrícia Simões Fiori

## Índice

| ID | Caso de teste | Área |
|---|---|---|
| [CT-01](#ct-01--login-com-sucesso) | Login com sucesso | Login |
| [CT-02](#ct-02--login-sem-dados) | Login sem dados | Login |
| [CT-03](#ct-03--login-sem-senha) | Login sem senha | Login |
| [CT-04](#ct-04--login-com-dados-inválidos) | Login com dados inválidos | Login |
| [CT-05](#ct-05--adição-de-item-no-carrinho) | Adição de item no carrinho | Carrinho |
| [CT-06](#ct-06--remover-item-do-carrinho-a-partir-da-listagem) | Remover item do carrinho a partir da listagem | Carrinho |
| [CT-07](#ct-07--ordenar-itens) | Ordenar itens | Catálogo |
| [CT-08](#ct-08--ver-detalhes-do-item) | Ver detalhes do item | Catálogo |
| [CT-09](#ct-09--continuar-comprando-a-partir-do-carrinho) | Continuar comprando a partir do carrinho | Carrinho |
| [CT-10](#ct-10--checkout) | Checkout | Checkout |

---

## CT-01 — Login com sucesso

| Campo | Detalhamento |
|---|---|
| **Descrição** | Login com sucesso |
| **Passos para reprodução** | 1. Acessar site<br>2. Inserir usuário válido no campo Username<br>3. Inserir senha válida no campo Password<br>4. Clicar no botão Login |
| **Resultado esperado** | O sistema deve realizar a autenticação dos dados, permitir o acesso ao sistema e redirecionar para a página inicial do e-commerce. |
| **Observações / pré-requisito** | Pré-requisito: possuir usuário e senha registrados no sistema. |

## CT-02 — Login sem dados

| Campo | Detalhamento |
|---|---|
| **Descrição** | Login sem dados |
| **Passos para reprodução** | 1. Acessar o site<br>2. Deixar os campos Username e Password vazios<br>3. Clicar no botão Login |
| **Resultado esperado** | O sistema deve exibir uma mensagem de erro informando que o campo Username é obrigatório.<br>Mensagem: `Epic sadface: Username is required` |
| **Observações / pré-requisito** | Validar obrigatoriedade do campo. |

## CT-03 — Login sem senha

| Campo | Detalhamento |
|---|---|
| **Descrição** | Login sem senha |
| **Passos para reprodução** | 1. Acessar o site<br>2. Inserir usuário válido no campo Username<br>3. Deixar o campo Password vazio<br>4. Clicar no botão Login |
| **Resultado esperado** | O sistema deve exibir uma mensagem de erro informando que o campo Password é obrigatório.<br>Mensagem: `Epic sadface: Password is required` |
| **Observações / pré-requisito** | Validar obrigatoriedade do campo. |

## CT-04 — Login com dados inválidos

| Campo | Detalhamento |
|---|---|
| **Descrição** | Login com dados inválidos |
| **Passos para reprodução** | 1. Acessar o site<br>2. Inserir usuário inválido no campo Username<br>3. Inserir senha inválida no campo Password<br>4. Clicar no botão Login |
| **Resultado esperado** | O sistema deve exibir uma mensagem de erro informando que as credenciais são inválidas e impedir o acesso.<br>Mensagem: `Epic sadface: Username and password do not match any user in this service` |
| **Observações / pré-requisito** | Validar tratamento de credenciais inválidas. |

## CT-05 — Adição de item no carrinho

| Campo | Detalhamento |
|---|---|
| **Descrição** | Adição de item no carrinho |
| **Passos para reprodução** | 1. Acessar a página de produtos<br>2. Selecionar um produto<br>3. Clicar no botão Add to cart |
| **Resultado esperado** | O sistema deve adicionar o item ao carrinho com sucesso e atualizar o número de itens no carrinho. |
| **Observações / pré-requisito** | Pré-requisito: usuário logado no sistema. |

## CT-06 — Remover item do carrinho a partir da listagem

| Campo | Detalhamento |
|---|---|
| **Descrição** | Remover item do carrinho a partir da listagem |
| **Passos para reprodução** | 1. Acessar a página de produtos<br>2. Clicar no botão Remove do item desejado |
| **Resultado esperado** | O item deve ser removido do carrinho com sucesso e o sistema deve atualizar o número de itens no carrinho. |
| **Observações / pré-requisito** | Pré-requisito: possuir itens no carrinho. |

## CT-07 — Ordenar itens

| Campo | Detalhamento |
|---|---|
| **Descrição** | Ordenar itens |
| **Passos para reprodução** | 1. Acessar a página de produtos<br>2. Clicar no menu suspenso de ordenação<br>3. Selecionar uma opção de ordenação |
| **Resultado esperado** | O sistema deve realizar a ordenação dos itens conforme o filtro selecionado pelo usuário. |
| **Observações / pré-requisito** | Pré-requisito: usuário logado no sistema. |

## CT-08 — Ver detalhes do item

| Campo | Detalhamento |
|---|---|
| **Descrição** | Ver detalhes do item |
| **Passos para reprodução** | 1. Acessar a página de produtos<br>2. Clicar sobre o nome ou imagem de um produto |
| **Resultado esperado** | O sistema deve redirecionar o usuário para a página de detalhes do produto. |
| **Observações / pré-requisito** | Pré-requisito: usuário logado no sistema. |

## CT-09 — Continuar comprando a partir do carrinho

| Campo | Detalhamento |
|---|---|
| **Descrição** | Continuar comprando a partir do carrinho |
| **Passos para reprodução** | 1. Acessar carrinho de compras<br>2. Clicar no botão Continue Shopping |
| **Resultado esperado** | O sistema deve redirecionar o usuário para a página inicial do e-commerce. |
| **Observações / pré-requisito** | Pré-requisito: usuário logado. |

## CT-10 — Checkout

| Campo | Detalhamento |
|---|---|
| **Descrição** | Checkout |
| **Passos para reprodução** | 1. Acessar carrinho de compras<br>2. Clicar no botão Checkout<br>3. Informar dados obrigatórios (First Name, Last Name, Zip/Postal Code)<br>4. Clicar no botão Continue<br>5. Clicar no botão Finish |
| **Resultado esperado** | O sistema deve processar as informações do pedido e exibir uma mensagem de sucesso.<br>Mensagem: `Thank you for your order! Your order has been dispatched, and will arrive just as fast as the pony can get there!` |
| **Observações / pré-requisito** | Pré-requisito: possuir itens no carrinho. |
