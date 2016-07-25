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

O Download do openfire pode ser feito de duas formas uma, direto pelo site do [openfirelink],
ou então pelo comando. 

{% highlight linux %} $ wget http://www.igniterealtime.org/downloadServlet?filename=openfire/openfire-3.8.1-1.i386.rpm

{% endhighlight %}




   [Wtfless], [Github] .

[openfirelink]: http://www.igniterealtime.org/index.jsp 
[Wtfless]: http://wtfless.github.io/
[Github]: https://github.com/


