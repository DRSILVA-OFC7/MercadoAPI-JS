💳 MercadoAPI-JS

<p align="center">
<img src="https://readme-typing-svg.herokuapp.com/?font=Fira+Code&size=28&duration=4000&color=00B386&center=true&vCenter=true&width=800&lines=MercadoAPI-JS;Integra%C3%A7%C3%A3o+Pix+com+Mercado+Pago;Cria%C3%A7%C3%A3o+e+Valida%C3%A7%C3%A3o+de+Pagamentos;Node.js+Payment+Library" />
</p><p align="center">
<img src="https://img.shields.io/badge/Node.js-18+-green?style=for-the-badge&logo=node.js">
<img src="https://img.shields.io/badge/Mercado%20Pago-API-blue?style=for-the-badge">
<img src="https://img.shields.io/badge/Version-1.0.0-orange?style=for-the-badge">
<img src="https://img.shields.io/badge/License-MIT-red?style=for-the-badge">
</p>---

📖 Sobre

MercadoAPI-JS é uma biblioteca desenvolvida para simplificar a integração com a API do Mercado Pago, permitindo gerar cobranças PIX e consultar pagamentos de forma rápida e prática utilizando Node.js.

✨ Recursos

- ✅ Criação de pagamentos PIX
- ✅ Geração de QR Code Base64
- ✅ Código PIX Copia e Cola
- ✅ Consulta de status do pagamento
- ✅ Definição automática de expiração
- ✅ Integração simples e rápida
- ✅ Compatível com qualquer projeto Node.js

---

📦 Instalação

Via NPM

npm install mercadoapi-js

Via GitHub

git clone https://github.com/seuusuario/MercadoAPI-JS
cd MercadoAPI-JS
npm install

---

🔑 Configuração

Obtenha seu Access Token no painel do Mercado Pago.

const { payment } = require("mercadoapi-js")

const mp = new payment("SEU_ACCESS_TOKEN")

---

💸 Criar Pagamento PIX

const { payment } = require("mercadoapi-js")

async function criarPix() {

    const mp = new payment("SEU_ACCESS_TOKEN")

    const pagamento = await mp.create_payment(10)

    console.log(pagamento)

}

criarPix()

Retorno

{
  "payment_id": "123456789",
  "copy_paste": "0002010102122685...",
  "qr_code": "iVBORw0KGgoAAAANSUhEUgAA..."
}

---

🔍 Verificar Status do Pagamento

const { payment } = require("mercadoapi-js")

async function verificar() {

    const mp = new payment("SEU_ACCESS_TOKEN")

    await mp.create_payment(10)

    const status = await mp.check_payment()

    console.log(status)

}

verificar()

Retorno

{
  "status": "approved"
}

---

⏰ Tempo de Expiração

Por padrão, os pagamentos expiram em 30 minutos.

Você pode definir outro valor:

await mp.create_payment(10, 60)

Neste exemplo:

60 = 60 minutos

---

📚 Métodos Disponíveis

create_payment(valor, tempo)

Cria uma cobrança PIX.

Parâmetros

Nome| Tipo| Descrição
valor| Number| Valor da cobrança
tempo| Number| Tempo de expiração em minutos

---

check_payment()

Consulta o status do pagamento.

Retorno

{
  "status": "approved"
}

Possíveis status:

approved
pending
cancelled
rejected

---

📂 Estrutura

MercadoAPI-JS
│
├── api.js
├── package.json
├── README.md
│
└── utils
    └── requests.js

---

🚀 Exemplo Completo

const { payment } = require("mercadoapi-js")

async function main() {

    const mp = new payment("SEU_ACCESS_TOKEN")

    const pix = await mp.create_payment(25)

    console.log("PIX:", pix.copy_paste)

    const status = await mp.check_payment()

    console.log("Status:", status.status)

}

main()

---

🛡️ Requisitos

- Node.js 18+
- Access Token Mercado Pago
- Conexão com internet

---

📜 Licença

Distribuído sob a licença MIT.

---

👨‍💻 Autor DEV: !DR. SILVA 💫 

GitHub:
https://github.com/DRSILVA-OFC7

---

<p align="center">
<img src="https://readme-typing-svg.herokuapp.com/?font=Fira+Code&size=22&duration=4000&color=00B386&center=true&vCenter=true&width=700&lines=Obrigado+por+usar+MercadoAPI-JS;Boas+vendas!+💸;Powered+by+Node.js+%26+Mercado+Pago" />
</p>
