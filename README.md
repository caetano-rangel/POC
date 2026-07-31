<h1 align="center">POC - Practical Examples</h1>
<br>

<div align="center">
  
[![LinkedIn](https://img.shields.io/badge/linkedin-%230077B5.svg?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/caetano-rangel/)

</div>
<br>

| Section | Description |
|---------|-------------|
| [POC 1](#POC-1) | Acconunt Takeover partindo de Xss |
| [POC 2](#POC-2) | Web Cache Deception |
| [POC 3](#POC-3) | Xss + WAF bypass |
| [POC 4](#POC-4) | Email Verify Bypass |
| [POC 5](#POC-5) | Image Upload com XSS Interno |
| [POC 6](#POC-6) | SSRF Access AWS Metadata |

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

## **POC 2**
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

## **POC 3**
<br>

**Xss + WAF bypass**
```bash
verificou que refletia -->
saiu da div com o payload </div><script.. -->
firewall modsecurity (firewall web) block -->
tentou com outro payload </div><svg onload=alert("test")> -->
continua testando payload e consegue com </div><svg> -->
entende que o svg nao é bloqueado e provavelmente o alert sim -->
</div><svg onload=confirm("test")> confirmando a hipotese -->
existem payloads direcionados para bypass diferentes
```
<br>

## **POC 4**
<br>

**Email Verify Bypass**
```bash
recebe o link de verificação -->
intercepta com o burp e verifica -->
criar outra conta como attacker email (onde supostamente nao temos acesso) -->
copiar o id -->
remove o token e substitui o id antigo pelo novo -->
obs: precisa logar e depois fazer a verificação, nao apos o cadastro
```
<br>

## **POC 5**
<br>

**Image Upload com XSS Interno**
```bash
upload de imagem com xss interno -->
content typ de image/png para text/html no intercept (não repeater) -->
inspect element e abra em outra aba -->
link url do stored xss
```
<br>

## **POC 6**
<br>

**SSRF via Misconfigured Host Header | Access AWS Metadata**
```bash
capturar a tela de login no burp -->
GET /login -->
alterar o host para 169.254.169.254 -->
alterar o get para GET https://169.254.169.254/latest/meta-data/
```
<br>
