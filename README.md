💳 MercadoAPI-JS

<p align="center">
<img src="https://readme-typing-svg.herokuapp.com/?font=Fira+Code&size=30&duration=4000&color=009EE3&center=true&vCenter=true&width=900&lines=MercadoAPI-JS;Integra%C3%A7%C3%A3o+PIX+com+Mercado+Pago;Cria%C3%A7%C3%A3o+e+Valida%C3%A7%C3%A3o+de+Pagamentos;Node.js+Payment+Library" />
</p><h1 align="center">
<img src="https://img.shields.io/badge/Mercado%20Pago-009EE3?style=for-the-badge&logo=mercadopago&logoColor=white">
</h1><p align="center">
<img src="https://img.shields.io/badge/Node.js-18+-green?style=for-the-badge&logo=node.js">
<img src="https://img.shields.io/badge/Mercado%20Pago-API-009EE3?style=for-the-badge&logo=mercadopago&logoColor=white">
<img src="https://img.shields.io/badge/License-MIT-red?style=for-the-badge">
</p><p align="center">
<img title="Autor" src="https://img.shields.io/badge/Autor-@DR_.SILVAOFC-orange.svg?style=for-the-badge&logo=github">
<img title="Versão" src="https://img.shields.io/badge/Versão-1.0.1-orange.svg?style=for-the-badge&logo=github">
</p><p align="center">
<img src="https://img.shields.io/badge/Discord-@dr_.silva-5865F2?style=for-the-badge&logo=discord&logoColor=white">
<img src="https://img.shields.io/badge/Instagram-@silva_.ofczxz-E4405F?style=for-the-badge&logo=instagram&logoColor=white">
</p>---

📖 Sobre

O MercadoAPI-JS é uma biblioteca desenvolvida para simplificar integrações com a API do Mercado Pago, oferecendo geração de cobranças PIX, QR Codes, PIX Copia e Cola e consulta de pagamentos através de uma interface simples para Node.js.

✨ Recursos

- ✅ Criação de pagamentos PIX
- ✅ QR Code Base64
- ✅ PIX Copia e Cola
- ✅ Consulta de status
- ✅ Expiração automática
- ✅ Fácil implementação
- ✅ Baixo consumo de recursos
- ✅ Compatível com Node.js
- ✅ Integração com Mercado Pago

---

📦 Instalação

Via NPM

npm install mercadoapi-js

Via GitHub

git clone https://github.com/DRSILVA-OFC7/MercadoAPI-JS
cd MercadoAPI-JS
npm install

---

🔑 Configuração

const { payment } = require("mercadoapi-js")

const mp = new payment("SEU_ACCESS_TOKEN")

---

💸 Criando um Pagamento PIX

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

🔍 Verificando Pagamentos

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

Por padrão:

await mp.create_payment(10)

Expira em:

30 minutos

Definindo outro tempo:

await mp.create_payment(10, 60)

60 minutos

---

📚 Métodos

create_payment(valor, tempo)

Parâmetro| Tipo| Descrição
valor| Number| Valor da cobrança
tempo| Number| Tempo em minutos

check_payment()

Verifica o status do pagamento.

Possíveis retornos

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

    console.log("PIX Copia e Cola:")
    console.log(pix.copy_paste)

    console.log("ID:")
    console.log(pix.payment_id)

    const status = await mp.check_payment()

    console.log("Status:")
    console.log(status.status)

}

main()

---

🛡️ Requisitos

- Node.js 18+
- Access Token Mercado Pago
- Internet

---

👨‍💻 Desenvolvedor

<p align="center">
<img src="https://img.shields.io/badge/Discord-@dr_.silva-5865F2?style=for-the-badge&logo=discord&logoColor=white">
<br><br>
<img src="https://img.shields.io/badge/Instagram-@silva_.ofczxz-E4405F?style=for-the-badge&logo=instagram&logoColor=white">
</p>---

📜 Licença

Distribuído sob licença MIT.

---

<p align="center">
<img src="https://readme-typing-svg.herokuapp.com/?font=Fira+Code&size=24&duration=4000&color=009EE3&center=true&vCenter=true&width=900&lines=Obrigado+por+usar+MercadoAPI-JS;Integra%C3%A7%C3%A3o+Profissional+com+Mercado+Pago;Powered+by+Node.js+%26+Mercado+Pago" />
</p>
