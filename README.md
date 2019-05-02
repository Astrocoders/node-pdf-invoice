pdf-invoice
===========

# Install
```
$ npm i -s pdf-invoice
```

# Usage

```js
const pdfInvoice = require('pdf-invoice')

const document = pdfInvoice({
  company: {
    phone: '(99) 9 9999-9999',
    email: 'company@evilcorp.com',
    address: 'Av. Companhia, 182, Água Branca, Piauí',
    name: 'Evil Corp.',
  },
  customer: {
    name: 'Elliot Raque',
    email: 'raque@gmail.com',
  },
  items: [
    {amount: 50.0, name: 'XYZ', description: 'Lorem ipsum dollor sit amet', quantity: 12},
    {amount: 12.0, name: 'ABC', description: 'Lorem ipsum dollor sit amet', quantity: 12},
    {amount: 127.72, name: 'DFE', description: 'Lorem ipsum dollor sit amet', quantity: 12},
  ],
})

// That's it! Do whatever you want now.
// Pipe it to a file for instance:

const fs = require('fs')

document.generate() // triggers rendering
document.pdfkitDoc.pipe(fs.createWriteStream('path/to/file.pdf'))
```

Checkout this PDF demo at https://github.com/Astrocoders/node-pdf-invoice/blob/master/tests/testing.pdf
