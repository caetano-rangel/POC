<h1 align="center">POC - Practical Examples</h1>
<br>

<div align="center">
  
[![LinkedIn](https://img.shields.io/badge/linkedin-%230077B5.svg?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/caetano-rangel/)

</div>
<br>

| Section | Description |
|---------|-------------|
| [POC 1](#POC-1) | Acconunt Takeover partindo de Xss |
| 2. [POC 2](#POC2) | Web Cache Deception |
| 3. [POC 3](#POC3) | Xss + WAF bypass |
| 4. [POC 4](#POC4) | Email Verify Bypass |
| 5. [POC 5](#POC5) | Image Upload com XSS Interno |

---
<br>

## **POC 1**
<br>

**Acconunt Takeover partindo de Xss**
```bash
campo name -->
<img/src/onerror='alert(1)'> -->
pagina /welcome refletiu (procurar onde reflete) -->
apenas isso sem impacto, necessita aumentar -->
magic link onde entra direto na pagina welcome podendo enviar o link direto -->
script de formulario que manda para o myserver com os dados -->
acconunt takeover partindo de xss
```
<br>

## **2. POC 2**
<br>

**Web Cache Deception**
```bash
faz o upload de alguma extensão que fique em cache -->
id na url ou coisa parecida linkando para o arquivo -->
no burp acessar a url ex: doc/12345 -->
adicionar .js ou .css no endpoint ou outra extensão -->
verificar o status code 200 e o cache-control -->
public e max-age -->
x-cache MISS envie novamente até x-cache HIT -->
cache deception confirmado -->
apos isso simular
```
<br>

