---
layout: post
title: Instalação do Jekyll no Windows
modified:
categories: blog
excerpt:
tags: []
image:
  feature:
date: 2016-04-26T19:02:12-03:00
---

Jekyll é um gerador de sites estáticos, ou seja, muito útil para a criação de um blog ou um site pequeno em que não é necessária a preocupação com um Banco de Dados.

No Mac OS X e Linux é possível instalar o Jekyll com muito mais facilidade que no Windows, por isso desse post, para auxiliar com o passo a passo necessário para a instalação no Windows.

Antes de instalar o Jekyll, o Ruby deve ser instalado já que no Windows não tem pré-instalado assim como no Linux.

## Instalação do Ruby

Faça o download do Ruby através deste link: [Download Ruby](http://rubyinstaller.org/downloads/archives)

Execute o arquivo de instalação do Ruby. Durante a instalação, selecione o diretório, marque as duas últimas opções e clique em “Install” na seguinte tela:

![Setup Ruby]({{ site.url }}/images/SetupRuby.jpg)

Faça o download da versão do DevKit correspondente a versão instalada do Ruby e a arquitetura do Windows: : [Download DevKit](http://rubyinstaller.org/downloads/) (Por exemplo: “For use with Ruby 2.0 and above (x64 - 64bits only)”).

Execute o arquivo baixado e extraia para o diretório: “C:\RubyDevKit”.

Após isso, abra a o cmd e vá até o diretório onde foi extraído o DevKit:

~~~
cd C:\RubyDevKit
~~~

Digite o seguinte comando:

~~~
ruby dk.rb init
~~~

Em seguida, o seguinte comando:

~~~
ruby dk.rb install
~~~

Após esses passos o Ruby estará instalado.

## Rouge

O Rouge é uma boa alternativa de realçador de sintaxe pois é de rápida e fácil instalação. Siga os passos a seguir:

Abra o cmd e execute o comando:

~~~
gem install rouge
~~~

E em seguida no arquivo _config.yml do seu site defina como realçador de sintaxe o Rouge:

~~~
highlighter: rouge
~~~

Pronto!

## Jekyll

Agora, o Jekyll pode ser instalado. Para isso, no cmd execute o comando:

~~~
gem install jekyll
~~~

A instalação pode demorar alguns minutos…

Quando instalado, pode ser realizada a criação de um projeto para testar. Para isso, no cmd execute o comando:

~~~
jekyll new nome-projeto
~~~

Após criado o projeto, abra o diretório onde foi criado com o comando:

~~~
cd nome-projeto
~~~

Neste diretório, execute o comando:

~~~
jekyll serve
~~~

Para acessar o projeto, acesse a URL: http://localhost:4000/.

## Resolução de Problemas

Alguns problemas que podem ser encontrados durante a instalação podem ser resolvidos seguindo os passos:

Quando: ruby dk.rb install
<br>Erro: Skipping existing gem override for 'C:/Ruby200-x64' 
<br>Solução: Excluir pasta Ruby e extrair novamente

Quando: gem install jekyll --version "=1.4.2"
<br>Erro:"could not find a valid gem 'jekyll' unable to download data from https://rubygems.org"
<br>Solução: gem sources -a http://rubygems.org

Quando: Aplicação do tema
<br>Erro: “File to import not found or unreadable variables”
<br>Solução: Gem update system + Gem Install Bundler + Bundle install (Instalar todos os aplicativos na última versão)

**OBS.:** Colocar o tema no diretório c:\www, nunca colocar em diretório com espaço e acento (Exemplo de diretório a não seguir: C:\Users\Angélica Chybior)