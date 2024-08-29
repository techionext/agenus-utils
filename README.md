<p align=\"center\">
  <a href=\"\" rel=\"noopener\">
    <img width=200px height=200px src=\"https://i.imgur.com/6wj0hh6.jpg\" alt=\"Project logo\">
  </a>
</p>

<h3 align=\"center\">@agenus/mask</h3>

<div align=\"center\">

[![Status](https://img.shields.io/badge/status-active-success.svg)]()
[![GitHub Issues](https://img.shields.io/github/issues/agenus/mask.svg)](https://github.com/agenus/mask/issues)
[![GitHub Pull Requests](https://img.shields.io/github/issues-pr/agenus/mask.svg)](https://github.com/agenus/mask/pulls)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](/LICENSE)

</div>

---

<p align=\"center\"> 
Functionality that allows adding or removing masks from strings, working with any React library, or HTML, React, and JavaScript.
</p>

<p align=\"center\"> Available masks:</p>
<p align=\"center\">
  CPF | CNPJ | Phone | Postal Code | CPF or CNPJ | Currency | RG | Credit Card | Obscure Email | Number | Card Expiration Date | Date | Time | International Phone
</p>

# Table of Contents

- [Table of Contents](#table-of-contents)
- [Installation](#installation)
- [Usage](#usage)
- [Properties setMask](#properties-setmask)
- [Type](#type)
- [Usage single](#usage-single)
- [Authors](#️-authors)
- [Thanks](#thanks)

# Installation

\`\`\`sh
npm i @agenus/mask

# or

yarn add @agenus/mask
\`\`\`

# Usage

\`\`\`js
import { setMask, removeMask } from \"@agenus/mask\";

const cpf = setMask({ value: '00000000000', type: 'cpf' });
const cnpj = setMask({ value: '00000000000000', type: 'cnpj' });
const cpfOurCnpj1 = setMask({ value: '00000000000', type: 'cpfOurCnpj' });
const cpfOurCnpj2 = setMask({ value: '00000000000000', type: 'cpfOurCnpj' });
const currency = setMask({ value: '00000000000', type: 'currency' });
const phone = setMask({ value: '00000000000', type: 'phone' });
const postalCode = setMask({ value: '00000000000', type: 'postalCode' });
const rg = setMask({ value: '000000000', type: 'rg' });
const credCard = setMask({ value: '0000000000000000', type: 'credCard' });
const number = setMask({ value: '0dasdas0000dasdasd0dasdasd0000dasdas0dasd0', type: 'number' });
const obscureEmail = setMask({ value: 'user123@gmail.com', type: 'obscureEmail' });
const date = setMask({ value: '01012020', type: 'date' });
const time = setMask({ value: '123456', type: 'time' });
const internationalPhone = setMask({ value: '12345678901', type: 'internationalPhone' });

console.log({
cpf,
cnpj,
cpfOurCnpj1,
cpfOurCnpj2,
currency,
phone,
postalCode,
rg,
credCard,
number,
obscureEmail,
date,
time,
internationalPhone
});

// Output
{
cpf: '000.000.000-00',
cnpj: '00.000.000/0000-00',
cpfOurCnpj1: '000.000.000-00',
cpfOurCnpj2: '00.000.000/0000-00',
currency: '0,00',
phone: '(00) 00000-0000',
postalCode: '00000-000',
rg: '00.000.000-0',
credCard: '0000-0000-0000-0000',
number: '000000000000',
obscureEmail: 'u**\*\***@gmail.com',
date: '01/01/2020',
time: '12:34:56',
internationalPhone: '+12 (34) 5678-901'
}

const removeCPF = removeMask(cpf);
const removeCNPJ = removeMask(cnpj);
const removeRG = removeMask(rg);
const removePostalCode = removeMask(postalCode);
const removePhone = removeMask(phone);
const removeCurrency = removeMask(currency);
const removeCred = removeMask(credCard);
const removeCPFORCNPJ1 = removeMask(cpfOurCnpj1);
const removeCPFORCNPJ2 = removeMask(cpfOurCnpj2);

console.log({
removeCPF,
removeCNPJ,
removeRG,
removePostalCode,
removePhone,
removeCurrency,
removeCred,
removeCPFORCNPJ1,
removeCPFORCNPJ2,
});

// Output
{
removeCPF: '00000000000',
removeCNPJ: '00000000000000',
removeRG: '000000000',
removePostalCode: '00000000',
removePhone: '00000000000',
removeCurrency: '00000000000',
removeCred: '0000000000000000',
removeCPFORCNPJ1: '00000000000',
removeCPFORCNPJ2: '00000000000000'
}
\`\`\`

# Properties setMask

|     Name     |     Type     | Default | Description                          |
| :----------: | :----------: | :-----: | :----------------------------------- |
| **\`type\`** | \`{String}\` |         | Mask format                          |
|  **value**   | \`{String}\` |         | String to be formatted               |
|  **Prefix**  | \`{String}\` |         | Prefix added before formatted string |

# Type

\`\`\`
| CNPJ | CPFOURCNPJ | RG | PHONE | CURRENCY | POSTALCODE | CREDCARD | DATE | TIME | INTERNATIONALPHONE
\`\`\`

# Usage single

\`\`\`js
import {
cpfMask, cnpjMask, cpfOurCnpjMask, credCardMask, currencyMask, phoneMask, postalCodeMask, rgMask,
} from \"@agenus/mask\";

const cpf = cpfMask('00000000000');
const cnpj = cnpjMask('00000000000000');
const cpfOurCnpj1 = cpfOurCnpjMask('00000000000');
const cpfOurCnpj2 = cpfOurCnpjMask('00000000000000');
const currency = currencyMask('00000000000');
const phone = phoneMask('00000000000');
const postalCode = postalCodeMask('00000000000');
const rg = rgMask('000000000');
const credCard = credCardMask('0000000000000000');

console.log({
cpf, cnpj, cpfOurCnpj1, cpfOurCnpj2, currency, phone, postalCode, rg, credCard,
});

// Output
{
cpf: '000.000.000-00',
cnpj: '00.000.000/0000-00',
cpfOurCnpj1: '000.000.000-00',
cpfOurCnpj2: '00.000.000/0000-00',
currency: 'R$ 000.000.000,00',
phone: '(00) 00000-0000',
postalCode: '00000-000',
rg: '00.000.000-0',
credCard: '0000-0000-0000-0000'
}
\`\`\`

## ✍️ Authors <a name=\"authors\"></a>

- [@ReisSouza](https://github.com/ReisSouza) - Idea & Initial work

See also the list of [contributors](https://github.com/agenus/mask/graphs/contributors) who participated in this project.

# Thanks

Thanks to [BrowserStack](https://www.browserstack.com/) for the help with testing on real devices
# agenus-utils
