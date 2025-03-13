<p align="center">
  <a href="https://fastsoftbrasil.com" rel="noopener">
    <img width=256px height=55px src="https://cdn.fastsoftbrasil.com/logo.png" alt="FastSoft logo">
  </a>
</p>

---

## 📝 Tabela de Conteúdos

- [🧐 Sobre](#-sobre)
- [⚡ Funcionalidades](#-funcionalidades)
- [💻 Instalação](#-instalação)
- [🚀 Como Usar](#-como-usar)
- [🎫 Características do Token](#-características-do-token)
- [🔒 Segurança](#-segurança)
- [🔍 Validações Implementadas](#-validações-implementadas)
- [💬 Suporte](#-suporte)

## 🧐 Sobre

Esse repositório se refere à biblioteca de segurança da FastSoft, que permite tokenizar dados de cartão de crédito de forma segura e eficiente, além de coletar o fingerprint do consumidor para integração com sistemas de antifraude.

## ⚡ Funcionalidades

| Funcionalidade              | Status | Descrição                                       |
| --------------------------- | ------ | ------------------------------------------------- |
| Criptografia de Cartão     | ✅     | Criptografa dados sensíveis do cartão           |
| Fingerprint do Consumidor   | ✅     | Coleta informações do dispositivo do consumidor |
| Integração com Antifraude | ✅     | Envia dados para análise de fraude               |

### 🔧 Métodos Disponíveis

#### `setPublicKey(key)`

- **Descrição**: Configura a chave pública para uso da API
- **Parâmetros**:
  - `key` (string): Chave pública
- **Retorno**: Promise

#### `encrypt(card)`

- **Descrição**: Criptografa dados do cartão
- **Parâmetros**:
  ```javascript
  {
    number: "4111111111111111",    // Número do cartão
    holderName: "NOME DO TITULAR", // Nome do titular
    expMonth: "12",                // Mês de expiração (1-12)
    expYear: "2025",               // Ano de expiração (4 dígitos)
    cvv: "123"                     // Código de segurança
  }
  ```
- **Retorno**: Promise com token do cartão

## 💻 Instalação

Adicione o script ao seu HTML:

```html
<script src="https://js.fastsoftbrasil.com/security.js"></script>
```

## 🚀 Como Usar

```javascript
// Configuração inicial
FastSoft.setPublicKey('sua_chave_publica_aqui');

// Criptografando um cartão
const card = {
    number: "4111111111111111",
    holderName: "JOAO DA SILVA",
    expMonth: "12",
    expYear: "2025",
    cvv: "123"
};

try {
    const cardToken = await FastSoft.encrypt(card);
    console.log('Token do cartão:', cardToken);
} catch (error) {
    console.error('Erro ao criptografar:', error);
}
```

## 🎫 Características do Token

O token gerado possui as seguintes características:

- ⏰ Validade: O token expira após 5 minutos da sua geração
- ⚡ Uso único: Cada token só pode ser utilizado uma vez

## 🔒 Segurança

A biblioteca implementa as seguintes validações de segurança:

- ✅ Validação completa dos dados do cartão
- ✅ Criptografia segura dos dados sensíveis
- ✅ Integração com sistema antifraude
- ✅ Carregamento dinâmico de scripts de segurança

## 🔍 Validações Implementadas

- 💳 Número do cartão é obrigatório
- 👤 Nome do titular deve conter nome e sobrenome
- 📅 Mês de expiração deve ter no máximo 2 caracteres
- 📅 Ano de expiração deve ter exatamente 4 caracteres
- 🔐 CVV deve ter entre 3 e 4 caracteres

## 💬 Suporte

Para mais informações, acesse:

- 🌐 Website: https://fastsoftbrasil.com
- 📚 Documentação: https://developers.fastsoftbrasil.com

---

<div align="center">
  <sub>Desenvolvido com ❤️ pela equipe FastSoft</sub>
</div>
