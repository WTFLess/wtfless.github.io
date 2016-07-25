---
layout: post
title:  "Instalando Openfire com Mysql usando o cliente Spark no Linux"
date:   2016-07-21 16:15:00
categories: Tecnologia
---

![openfire](/assets/images/logo-openfire.png "logo da openfire")

O openfire é uma aplicação que permite habilitar um chat para comunicação interna, muito usado em empresas para subistituir o Skype, com ele é possivel fazer video chamada, tranferencia de arquivos, e ate mesmo salas de reunição. 

vamos la, para a parte interessante. 

Instalação:

O openfire é uma aplicação java, sendo assim necessitamos instalar o mesmo. para instalar, o comando é p seguinte:

{% highlight linux %} $ yum install java -y

{% endhighlight %}

Bom o openfire pode usar um banco de dados interno ou um externo, podendo sem mysql postgresql mariadb enfim,
neste nosso caso iremos usar o mysql.

Então vamos baixar o mysql com o comando 

{% highlight linux %} $ yum install mysql mysql-server -y

{% endhighlight %}



   [Wtfless], [Github] .

[Wtfless]: http://wtfless.github.io/
[Github]: https://github.com/


