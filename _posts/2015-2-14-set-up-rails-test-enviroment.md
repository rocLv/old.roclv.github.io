---
layout: post
title: Rails开发环境常用配置
---
列举了Rails开发常用的gem以及初始化过程
<!--more-->

###Rails开发环境常用配置 
Rails开发中除了初始化后，Gemfile中自动包含的gem，常用的还有：
* rspec-rails
* capybara
* shoulda-matcher
* guard-rspec
* guard-livereload
等等。

首先在Gemfile中添加如下代码：

```ruby
   group :developement, :test do
     gem 'rspec-rails'
     gem 'capybara'
     gem 'shoulda-matcher'
     gem 'guard-rspec'
     gem 'guard-livereload'
   end
 ```
 
 保存， 然后运行：  
 `$ bundle`
 
 然后，初始化rspec
 
 ```ruby
   rails generate rspec:install
   
   #或者
   
   rails g rspec:install
 ```
 
 生成以下文件：
 
* .rspec
* spec/spec_helper.rb
* spec/rails_helper.rb

然后，初始化Guardfile

`$ guard init`

提示：
    
    11:31:04 - INFO - Writing new Guardfile to /your/app/path/Guardfile
    11:31:04 - INFO - livereload guard added to Guardfile, feel free to edit it
    11:31:05 - INFO - rspec guard added to Guardfile, feel free to edit it


然后添加__capybara__到rails_helper.rb

`require 'capybara/rails'`

添加shoulda-matcher到rails_helper.rb文件中  
`require 'shoulda/matchers'`

至此，一个基本的rails测试环境基本搭建完毕。


