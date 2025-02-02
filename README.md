# Site Estático no s3

![Tela inicial](https://github.com/AgataAraujo-dev/site_s3/blob/340f8011022b5ab564217b3b3736606112165164/telaFinal.jpg)

### Índice 

- [Descrição do projeto](#descrição-do-projeto)

- [Funcionalidades](#funcionalidades)

- [Atualizações](#atualizações)

- [Passo a Passo](#passo-a-passo)

- [Ferramentas utilizadas](#ferramentas-utilizadas)

- [Agradecimentos](#agradecimentos-e-colaboradoras)


## Descrição do projeto 

<p align="justify">
 Aproveitando a recente aplicação web desenvolvida, subi ela para um bucket s3 para praticar meus conhecimentos em AWS. Este trabalho foi desenvolvido em conjunto com colegas muito queridas e habilidosas.

O objetivo deste repositório é demonstrar meu conhecimento em AWS, adquirido durante o curso oferecido pela Escola da Nuvem. Graças ao ensino e apoio da instituição pude conquistar a AWS Cloud Practitioner!

</p>

## Funcionalidades

:heavy_check_mark: `Funcionalidade 1:` Permite que você adicione seu nome na lista de participantes. Após essa etapa, ele solicita o nome dos outros participantes e quando todos forem adicionados basta sortear o seu amigo secreto.

:heavy_check_mark: `Funcionalidade 2:` Por estar armazenado em bucket público o projeto não consome armazenamento em minha máquina e com o versionamento ativado tenho a segurança de todas as versões salvas para caso precise fazer alguma consulta no histórico do bucket. 

:heavy_check_mark: `Funcionalidade 3:` Utilizando a hospedagem de site estático oferecida pelo próprio s3, o site está público e disponível pela internet.

## Atualizações

🆕 `Atualização 1:` Em nosso segundo encontro, utilizamos AWS CloudFront e Route53 para distribuir o site.

🆕 `Atualização 2:` Também criamos e habilitados um certificado SSL através do AWS Certificated Manager, para garantir o uso de HTTPS.


###

## Passo a Passo

# Criar o Bucket

 Iniciamos criando o Bucket na região de São Paulo (sa-east-1)

<a> <img src="https://github.com/AgataAraujo-dev/site_s3/blob/340f8011022b5ab564217b3b3736606112165164/Console%20-%20regi%C3%A3oSP.jpg" alt="Criando o bucket" width="500" height="250"/> </a>

<a> <img src="https://github.com/AgataAraujo-dev/site_s3/blob/340f8011022b5ab564217b3b3736606112165164/bucketCriado.jpg" alt="Bucket Criado" width="500" height="250"/> </a>

# Políticas

Após fazer upload dos objetos no bucket, criamos a política para torná-lo público e seguro.

<a> <img src="https://github.com/AgataAraujo-dev/site_s3/blob/340f8011022b5ab564217b3b3736606112165164/bucketPoliticas.jpg" alt="Políticas do Bucket" width="500" height="250"/> </a>

O texto gerado para política foi:

```
{
	"Version": "2012-10-17",
	"Id": "Policy1738034702575",
	"Statement": [
		{
		   "Sid": "Stmt1738034657280",
		   "Effect": "Allow",
		   "Principal": "*",
		   "Action": "s3:GetObject",
		   "Resource": "arn:aws:s3:::amigosecreto-one/*"
		}
	]
}
```

<a> <img src="https://github.com/AgataAraujo-dev/site_s3/blob/340f8011022b5ab564217b3b3736606112165164/bucketPublico.jpg" alt="Bucket Público" width="500" height="250"/> </a>

# Hospedagem

Utilizamos a opção de hospedagem do próprio s3, para fins didáticos.

<a> <img src="https://github.com/AgataAraujo-dev/site_s3/blob/340f8011022b5ab564217b3b3736606112165164/bucketHospedado.jpg" alt="Bucket Hospedado" width="500" height="250"/> </a>

# Resultado Final

Ao final tivemos nossa aplicação web hospedada, pública e segura!

<a> <img src="https://github.com/AgataAraujo-dev/site_s3/blob/340f8011022b5ab564217b3b3736606112165164/telaFinal.jpg" alt="Tela Final" width="500" height="250"/> </a>

E o bucket organizado ficou da seguinte forma:

<a> <img src="https://github.com/AgataAraujo-dev/site_s3/blob/340f8011022b5ab564217b3b3736606112165164/organiza%C3%A7%C3%A3oFinal.jpg" alt="Organização Final" width="500" height="250"/> </a>

# Atualização 1

Em nosso segundo encontro, utilizamos o AWS CloudFront para distribuir nosso site:

<a> <img src="https://github.com/AgataAraujo-dev/siteEstatico_s3/blob/dbfe40c8902718f1ae24403f969bde6af01e0661/cloudfront.jpg" alt="CloudFront" width="500" height="250"/> </a>

E com o Route53 validamos o DNS da nossa distribuição, para isso também criamos uma Zona Hospedada:

<a> <img src="https://github.com/AgataAraujo-dev/siteEstatico_s3/blob/dbfe40c8902718f1ae24403f969bde6af01e0661/route53.jpg" alt="Route53" width="500" height="250"/> </a>

# Atualização 2

Por fim criamos e habilitamos um certificado SSL com o AWS Certificated Manager, garantindo a segurança do uso de protocolo HTTPS:

<a> <img src="https://github.com/AgataAraujo-dev/siteEstatico_s3/blob/dbfe40c8902718f1ae24403f969bde6af01e0661/https.jpg" alt="HTTPS" width="500" height="250"/> </a>


###

## Ferramentas utilizadas

<a href="https://aws.amazon.com/pt/free/?gclid=CjwKCAiAneK8BhAVEiwAoy2HYaSwsL4PO5R6dupPuDnB0Ud8CTLW90TPXHs-iX3AyLHSieA94x_U7hoC6K0QAvD_BwE&all-free-tier.sort-by=item.additionalFields.SortRank&all-free-tier.sort-order=asc&awsf.Free%20Tier%20Categories=categories%23storage&trk=3daf7be6-997a-4e7c-af79-be4074c210e4&sc_channel=ps&ef_id=CjwKCAiAneK8BhAVEiwAoy2HYaSwsL4PO5R6dupPuDnB0Ud8CTLW90TPXHs-iX3AyLHSieA94x_U7hoC6K0QAvD_BwE:G:s&s_kwcid=AL!4422!3!536324461821!e!!g!!amazon%20s3!12024810840!115492236865&awsf.Free%20Tier%20Types=*all" target="_blank"> <img src="https://github.com/AgataAraujo-dev/site_s3/blob/340f8011022b5ab564217b3b3736606112165164/s3.png" alt="AWS s3" width="170" height="100"/> </a>

###

## Agradecimentos e Colaboradoras

Agradeço muito à Escola da Nuvem por todo aprendizado, principalmente ao meu instrutor Matheus. Agradeço também às minhas colegas colaboradoras que me incentivaram e junto comigo desenvolveram esse projeto!

<a href="https://escoladanuvem.org/" target="_blank"> <img src="https://github.com/AgataAraujo-dev/site_s3/blob/340f8011022b5ab564217b3b3736606112165164/EdN.png" alt="Escola da Nuvem" width="100" height="100"/> </a>
<a href="https://www.linkedin.com/in/sarah-m-castro/" target="_blank"> <img src="https://github.com/AgataAraujo-dev/site_s3/blob/340f8011022b5ab564217b3b3736606112165164/Sarah.jpg" alt="Sarah Castro" width="100" height="100"/> </a>
<a href="https://www.linkedin.com/in/elisa-souzaa/" target="_blank"> <img src="https://github.com/AgataAraujo-dev/site_s3/blob/340f8011022b5ab564217b3b3736606112165164/Elisa.jpg" alt="Elisa Souza" width="100" height="100"/> </a>
<a href="https://www.linkedin.com/in/naara-reis-santana/" target="_blank"> <img src="https://github.com/AgataAraujo-dev/site_s3/blob/340f8011022b5ab564217b3b3736606112165164/Naara.jpg" alt="Naara Santana" width="100" height="100"/> </a>
