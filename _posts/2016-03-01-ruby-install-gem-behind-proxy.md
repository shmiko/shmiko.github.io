---
layout: post
section-type: post
title: Ruby Install Gem Behind Proxy
categories: ['ruby_on_rails']
tags: [ 'ruby_on_rails']
---


## How to Install Ruby Gem behind a corperate proxy sepecially when your password contains special characters  

![Ruby on Rails](/img/ruby-on-rails.jpg)  

<pre><code>
  gem install --http-proxy http://johnsmith:F%40o%3Ao%21B%23ar%24@corperatefirewall.com.au:8080 rails --no-ri --no-rdoc
</pre></code>

The answer is to encode the special characters.  
Convert @:!#$ into equivalent hexadecimal unicode using unum command.  
In this example @ becomes %40, : becomes %3A, and so on.  
- F@o:o!B#ar$  
Replace with:  
- F%40o%3Ao%21B%23ar%24  

OR  
Rather than use the proxy within each gem install command you can set it this way:  
<pre><code>
  export http_proxy="http://user:F%40o%3Ao%21B%23ar%24@corperatefirewall.com.au:8080/"
</pre></code>
