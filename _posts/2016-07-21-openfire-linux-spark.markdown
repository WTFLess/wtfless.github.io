---
layout: post
title:  "Instalando Openfire com Mysql usando o cliente Spark no Linux"
date:   2016-07-21 16:15:00
categories: Tecnologia
---

![openfire logo](/assets/images/logo-openfire.png "logo da openfire")

O openfire é uma aplicação que permite habilitar um chat para comunicação interna, muito usado em empresas para subistituir o Skype, com ele é possivel fazer video chamada, tranferencia de arquivos, e ate mesmo salas de reunição. 

Vamos la, para a parte interessante. 

# Instalação:

## Java

O openfire é uma aplicação java, sendo assim necessitamos instalar o mesmo. para instalar, o comando é p seguinte:

{% highlight linux %} $ yum install java -y

{% endhighlight %}

## Mysql

Bom o openfire pode usar um banco de dados interno ou um externo, podendo sem mysql postgresql mariadb enfim,
neste nosso caso iremos usar o mysql.

Então vamos baixar o mysql com o comando 

{% highlight linux %} $ yum install mysql mysql-server -y

{% endhighlight %}

Obs.: Interessante adicionar o mysql na inicialização do sistema

{% highlight linux %} $ chkconfig mysqld on

{% endhighlight %}

Iniciar o Mysql 

{% highlight linux %} $ service mysqld start

{% endhighlight %}

Configurar a senha do Root do Mysql

{% highlight linux %} $ mysqladmin -u root password 'escoha a senha de root'

{% endhighlight %}

## Openfire

O Download do openfire pode ser feito de duas formas uma, direto pelo site do [Openfirelink],
ou então pelo comando. 

{% highlight linux %} $ wget http://www.igniterealtime.org/downloadServlet?filename=openfire/openfire-3.8.1-1.i386.rpm

{% endhighlight %}

É necessario também, instalar as libs "libldb.i686" e "glibc.i686" pois o openfire é 32Bits.

{% highlight linux %}
$ yum install glibc.i686
$ yum install libldb.i686 
{% endhighlight %}

Agora instale o pacote do openfire baixado, seja pelo link direto ou pelo wget, com o comando:

{% highlight linux %} $ rmp -ivh openfire-x.x.x-x.i686.rpm

{% endhighlight %}

## Configurações 

Primeiro inicie o servico do openfire. 

{% highlight linux %} $ service openfire start

{% endhighlight %}

Agora é necessario  acessar o Mysql para configurar as tabelas.

{% highlight linux %} $ mysql -u root -p

{% endhighlight %}

Criando as tabelas:

{% highlight linux %} 
mysql> CREATE DATABASE openfire;
mysql> GRANT ALL PRIVILEGES ON openfire.* TO 'openfire'@'localhost' IDENTIFIED BY 'senhade acesso';
mysql> FLUSH PRIVILEGES;
mysql> quit
{% endhighlight %}

Agora, é necessario importar os dados para o Mysql.

{% highlight linux %} $ mysql -u root -p openfire <  /opt/openfire/resources/database/openfire_mysql.sql 

{% endhighlight %}










[Openfirelink]: http://www.igniterealtime.org/index.jsp/
[Wtfless]: http://wtfless.github.io/
[Github]: https://github.com/

