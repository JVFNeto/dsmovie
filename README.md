﻿# TCC_Server_Fullstack

Introdução: Esse aplicativo foi feito utilizando as IDEs VSCode para o frontend e IntelliJ Comunity para o Backend,
em meus projetos eu tenho preferência por utilizar o MYSql como SGBD, mas como uparei esse projeto pelo Heroku, utilizarei o 
postgrees que pode ser upado de forma free. Quero deixar claro que essa produção não é de direito autoral meu, eu sou apenas um 
DEV Júnior que concluiu com sucesso o curso "Semana Spring React - Trilha Profissionalizante" do canal DevSuperior.
Posteriormente, pretendo fazer esse mesmo codigo, com o diferencial que trocarei o frontend de React para Angular9

instalações utilizadas nesse projeto 
{
JDK 15
Postman
Postgresql 12
pgAdmin
Heroku CLI
NodeJS 16
VSCode (frontend)
IntelliJ (backend)
Git
}


********************************************INICIO DO EPISODIO 1********************************************
(Criação do front e backend, Linkando com o Github, Subindo o front com yarn, Add bootstrap e css, ) 


yarn create react-app frontend --template typescript (cria o projeto chamado frontend utilizando typescript)

delete a pasta .git na pasta frontend

yarn start (frontend) (esse comando faz o projeto executar)

crie um projeto no spring initializer e cole no backend 
dependencias{
Web
JPA
H2
Postgres
Security
}

após configurar as dependencias do backend

---LINKANDO COM O GITHUB---

git init (para criar o repositorio gi no pc (pasta do projeto))
git add . (adiciona os arquivos na area de stading)
git commit -m "Projeto criado e pronto para codar" (da um comit master com esse "nome")
git branch -M main (cria branch main (boa pratica))
git remote add origin git@github.com:.......  (associei o projeto local, com o meu projeto remoto do github)
git push -u origin main (envia para o git hub) 

---sempre que for commitar---
git add .
git commit -m "commit"
git push


 

--------------------------------------------FRONT-END--------------------------------------------

deixe apenas os files (public{index.html} src{App.tsx, index.css, index.tsx e react-app}
o restante pode apagar desses packeges (public e src). Faça as auterações nescessarias e suba a aplicação
com "yarn start".

---Adicionando BootStrap e CSS ao projeto---
(bootstrap é um framework de css que uma boa estrutura já pronta que ejudará a montar um layout mais facilmente)

yarn add bootstrap@5.1.3 (frontend) (adiciona o bootstrap)


---ROTAS---
yarn add react-router-dom@6.2.1 @types/react-router-dom@5.3.2
  

********************************************FIM DO EPISODIO 1***********************************************


*******************************************INICIO DO EPISODIO 2*********************************************

a Class SecurityConfig, irá liberar o backend que esta hospedado em um servidor, possa ser acessado pelo frontend que está em outro lugar.


http://localhost:8080/h2-console (entra na pagina usando do banco de dados h2)


---abaixo está o .properties---

# Dados de conexão com o banco H2
spring.datasource.url=jdbc:h2:mem:testdb
spring.datasource.username=sa
spring.datasource.password=

# Configuração do cliente web do banco H2
spring.h2.console.enabled=true
spring.h2.console.path=/h2-console

# Configuração para mostrar o SQL no console
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.format_sql=true


---abaixo está o dev.properties---
#spring.jpa.properties.javax.persistence.schema-generation.create-source=metadata
#spring.jpa.properties.javax.persistence.schema-generation.scripts.action=create
#spring.jpa.properties.javax.persistence.schema-generation.scripts.create-target=create.sql
#spring.jpa.properties.hibernate.hbm2ddl.delimiter=;

spring.datasource.url=jdbc:postgresql://localhost:5432/dsmovie
spring.datasource.username=postgres
spring.datasource.password=link00forever

spring.jpa.properties.hibernate.jdbc.lob.non_contextual_creation=true
spring.jpa.hibernate.ddl-auto=none

---abaixo está o test.properties---

# Dados de conexão com o banco H2
spring.datasource.url=jdbc:h2:mem:testdb
spring.datasource.username=sa
spring.datasource.password=

# Configuração do cliente web do banco H2
spring.h2.console.enabled=true
spring.h2.console.path=/h2-console

# Configuração para mostrar o SQL no console
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.format_sql=true

---abaixo está o prod.properties---


spring.datasource.url=${DATABASE_URL}

---abaixo está o system.properties---

java.runtime.version=15



--------abaixo está a config do heroku com pg------------

postgres://

***************** (username)
:
***************************************** (senha)
@
********** (Hostname)
:
5432 (port)
/
********* (maintanance database) (db restriction)

********************************************FIM DO EPISODIO 2***********************************************


*******************************************INICIO DO EPISODIO 3*********************************************



Instalar Axios---
yarn add axios@0.24.0


React hooks: useState e useEffect-----

Hooks são funções cujo comportamento está vinculado ao estado e ao ciclo de vida do React a partir de componentes funcionais.

Hook: useState
Manter estado no componente
{
const [pageNumber,setPageNumber]= useState(0);

axios.get(`${BASE_URL}/movies?size12&page=0`)
.then(response => {
    const data = response.data as MoviePage;
    setPageNumber(data.number)
});
}

Hook: useEffect
Executar algo na instanciação ou destruição do componente, observar estado
{

}
