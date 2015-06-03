---
layout:     post
title:      Instalar e configurar ambiente Ruby on Rails
date:       2015-06-03 17:55:19
author:     Aristeu Roriz
summary:    Tutorial para instalar e configurar ambiente Ruby on Rails no Linux
categories: ruby-on-rails
thumbnail:  terminal
tags:
- instalar
- configurar
- ambiente
- ruby on rails
---
<p class="recuo" align="justify">
	Vou ensinar neste post como instalar e configurar o ambiente de desenvolvimento Ruby on Rails no LINUX.
	Eu instalei no meu computador rodando <a href="https://elementary.io/" target="_blank">Elementary OS Freya</a>, OS baseado no Ubuntu 14. Utilizo o <a href="https://rvm.io/" target="_blank">RVM (Ruby Version Manager)</a> que é um gerenciador para se ter várias versões do Ruby na mesma máquina. Vamos usar o "Ruby 2.2.2" e o "Rails 4.2", que são as últimas versões estáveis na data deste post.
</p>


<p align="justify">
	Para começar, atualize a lista de pacotes do linux:
	<code>
		sudo apt-get update
	</code>
</p>

<p align="center">
	<strong>
		Instalando o RVM (Ruby Version Manager) e o Ruby
	</strong>
</p>

<p align="justify">
	Instale a chave pública do RVM, conforme abaixo:
	<code>
		gpg --keyserver hkp://keys.gnupg.net --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3
	</code>
</p>

<p align="justify">
	Para instalar o RVM, use este comando:
	<code>
		curl -L https://get.rvm.io | bash -s stable
	</code>
	<br>

	Se você não tiver o "curl" instalado, rode este comando para instalar:

	<code>
		sudo apt-get install curl
	</code>
</p>


<p align="justify">
	
	Com esses passos prontos, temos que adicionar o RVM ao shell. Para isso cole o código abaixo ao arquivo <strong>.bashrc</strong> ou ao <strong>.bash_profile</strong>:
	<code>
		PATH=$PATH:$HOME/.rvm/bin # Add RVM to PATH for scripting <br>
		[[ -s "/usr/local/rvm/scripts/rvm" ]] &amp;&amp; source "/usr/local/rvm/scripts/rvm"<br>
		[[ -s "$HOME/.rvm/scripts/rvm" ]] &amp;&amp; source "$HOME/.rvm/scripts/rvm"
	</code>
</p>

<small>
	<p class="text-warning">
		<em>
			Obs.: Se algum comando com rvm não funcionar, você precisa acessar as preferências (Edit -> Profile Preferences) do terminal e marcar a opção para executar comandos com login.
		</em>
	</p>
</small>

<p align="justify">

	Para verificar quais as versões do Ruby estão disponíveis no RVM use:
	<code>
		rvm list known
	</code>
	<br>
	Mas antes de instalar o Ruby, instale algumas dependências necessárias:

	<code>
		sudo apt-get install build-essential openssl libreadline6<br> libreadline6-dev curl git-core zlib1g zlib1g-dev <br>libssl-dev libyaml-dev libsqlite3-dev sqlite3 libxml2-dev <br>libxslt-dev autoconf libc6-dev ncurses-dev automake libtool bison <br>subversion pkg-config
	</code>
	<br>
	Agora, rode este comando para instalar a versão 2.2.2 do Ruby:
	<code>
		rvm install 2.2.2
	</code>
	<br>
	Configure a versão instalada para ser a versão padrão:
	<code>
		rvm use 2.2.2 --default
	</code>
	<br>
	Pronto! Já podemos verificar a versão do Ruby instalada com este comando:
	<code>
		ruby -v
	</code>
</p>


<p align="center">
	<strong>
		Instalando o Rails
	</strong>
</p>	

<p align="justify">
	
	Vamos a instalação do Rails. Para isso rode o comando:

	<code>
		gem install rails
	</code>
	<br>
	Da mesma forma que o Ruby, após a instalação do Rails poderemos verificar a versão instalada:
	<code>
		rails -v
	</code>
</p>
<p class="recuo" align="justify">
	Mais uma observação: O Rails usa por padrão o SQLite, entretanto você poderá usar outros bancos como MySQL, PostgreSQL, MongoDB, etc.
	Não entrarei nos detalhes sobre a instalação de banco de dados para este post não ficar muito longo. Você consegue um tutorial sobre como instalá-los com uma simples pesquisa na web.
</p>

<p class="recuo" align="justify">
	Espero que este post ajude a quem está iniciando no mundo RoR e sirva também para os mais experientes relembrarem os passos iniciais.
</p>



*** Ahhh... e não deixe de compartilhar! ;-)
