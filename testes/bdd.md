# Testes BDD – Swag Labs

Cenários em linguagem Gherkin (português) derivados dos casos de teste CT-01 a CT-10 do Plano de Testes.

- **Produto:** Swag Labs
- **URL:** https://www.saucedemo.com
- **Navegador:** Google Chrome
- **Responsável:** Patrícia Simões Fiori

---

## Funcionalidade: Login

```gherkin
# language: pt
@login
Funcionalidade: Login
  Como usuário do Swag Labs
  Quero acessar o sistema com meu usuário e senha
  Para visualizar e comprar os produtos do catálogo

  Contexto:
    Dado que acesso o site "https://www.saucedemo.com"

  @CT-01 @sucesso
  Cenário: Login com credenciais válidas
    Quando informo o usuário "standard_user" no campo Username
    E informo a senha "secret_sauce" no campo Password
    E clico no botão "Login"
    Então o sistema autentica os dados
    E sou redirecionado para a página inicial do e-commerce

  @CT-02 @validacao
  Cenário: Login com campos vazios
    Quando deixo os campos Username e Password vazios
    E clico no botão "Login"
    Então o sistema exibe a mensagem de erro "Epic sadface: Username is required"

  @CT-03 @validacao
  Cenário: Login sem senha
    Quando informo o usuário "standard_user" no campo Username
    E deixo o campo Password vazio
    E clico no botão "Login"
    Então o sistema exibe a mensagem de erro "Epic sadface: Password is required"

  @CT-04 @validacao
  Cenário: Login com credenciais inválidas
    Quando informo o usuário "teste" no campo Username
    E informo a senha "senha" no campo Password
    E clico no botão "Login"
    Então o sistema exibe a mensagem de erro "Epic sadface: Username and password do not match any user in this service"
    E o acesso ao sistema é impedido
```

---

## Funcionalidade: Carrinho de compras

```gherkin
# language: pt
@carrinho
Funcionalidade: Carrinho de compras
  Como usuário logado
  Quero adicionar e remover produtos do carrinho
  Para escolher os itens que desejo comprar

  Contexto:
    Dado que estou logado como "standard_user"
    E estou na página de produtos

  @CT-05
  Cenário: Adicionar item ao carrinho
    Quando seleciono um produto
    E clico no botão "Add to cart"
    Então o item é adicionado ao carrinho
    E o contador do carrinho é atualizado

  @CT-06
  Cenário: Remover item do carrinho a partir da listagem
    Dado que possuo um item no carrinho
    Quando clico no botão "Remove" do item desejado
    Então o item é removido do carrinho
    E o contador do carrinho é atualizado

  @CT-09
  Cenário: Continuar comprando a partir do carrinho
    Dado que acesso o carrinho de compras
    Quando clico no botão "Continue Shopping"
    Então sou redirecionado para a página inicial do e-commerce
```

---

## Funcionalidade: Catálogo de produtos

```gherkin
# language: pt
@catalogo
Funcionalidade: Catálogo de produtos
  Como usuário logado
  Quero ordenar os produtos e ver seus detalhes
  Para encontrar mais facilmente o item que desejo

  Contexto:
    Dado que estou logado como "standard_user"
    E estou na página de produtos

  @CT-07
  Esquema do Cenário: Ordenar itens do catálogo
    Quando clico no menu suspenso de ordenação
    E seleciono a opção "<opcao>"
    Então os itens são exibidos ordenados conforme o filtro selecionado

    Exemplos:
      | opcao               |
      | Name (A to Z)       |
      | Name (Z to A)       |
      | Price (low to high) |
      | Price (high to low) |

  @CT-08
  Cenário: Ver detalhes do item
    Quando clico no nome ou na imagem de um produto
    Então sou redirecionado para a página de detalhes do produto
```

---

## Funcionalidade: Checkout

```gherkin
# language: pt
@checkout
Funcionalidade: Checkout
  Como usuário logado com itens no carrinho
  Quero finalizar minha compra
  Para concluir o pedido

  Contexto:
    Dado que estou logado como "standard_user"
    E possuo itens no carrinho

  @CT-10 @sucesso
  Cenário: Finalizar a compra com sucesso
    Dado que acesso o carrinho de compras
    Quando clico no botão "Checkout"
    E informo o First Name "Maria"
    E informo o Last Name "Silva"
    E informo o Zip/Postal Code "12345678"
    E clico no botão "Continue"
    E clico no botão "Finish"
    Então o sistema processa as informações do pedido
    E exibe a mensagem "Thank you for your order! Your order has been dispatched, and will arrive just as fast as the pony can get there!"
```

---

## Rastreabilidade

| Caso de teste | Cenário BDD | Funcionalidade |
|---|---|---|
| CT-01 | Login com credenciais válidas | Login |
| CT-02 | Login com campos vazios | Login |
| CT-03 | Login sem senha | Login |
| CT-04 | Login com credenciais inválidas | Login |
| CT-05 | Adicionar item ao carrinho | Carrinho de compras |
| CT-06 | Remover item do carrinho a partir da listagem | Carrinho de compras |
| CT-07 | Ordenar itens do catálogo | Catálogo de produtos |
| CT-08 | Ver detalhes do item | Catálogo de produtos |
| CT-09 | Continuar comprando a partir do carrinho | Carrinho de compras |
| CT-10 | Finalizar a compra com sucesso | Checkout |
