# E-mails Node.js
## Jak wysyłać e-maile za pomocą Nodemailera i SMTP
**Zainstaluj nodemailera** <br>
`npm install nodemailer` <br> <br>
Użyj[ Mailtrap ](https://mailtrap.io/)lub podobnej usługi, która będzie służyć jako fałszywy serwer SMTP.
Utwórz konto **Mailtrap** i z listy Integrations w Dashbordzie wybierz Nodemailer i skopiuj dane.
![Screen](https://www.courier.com/_next/image/?url=https%3A%2F%2Fimages.ctfassets.net%2Fz7iqk1q8njt4%2F6H4GZGxNUtAn6O0PkyqI80%2Fa0f71c30cc970433161253ca0014885e%2FMailtrap.jpg&w=3840&q=100)

`const nodemailer = require('nodemailer');
var transport = nodemailer.createTransport({
    host: "sandbox.smtp.mailtrap.io",
    port: 2525,
    auth: {
      user: "wstaw",
      pass: "wstaw"
    }
  });
message = {
    from: "from-example@email.com",
    to: "to-example@email.com",
    subject: "Temat",
    text: "Siema"
}
transport.sendMail(message, function(err, info) {
    if (err) {
      console.log(err)
    } else {
      console.log(info);
    }});`
