# intro-sinatra

- ~~~ruby
  mkdir sinatra-test
  
  cd sinatra-test
  
  touch app.rb
  
  gem install sinatra
  
  ~~~

- ~~~ruby
  #app.rb
  
  require 'sinatra'
  
  get '/' do
    'Hello world!'
  end
  
  #웹에 Hello world 출력
  ~~~

- ~~~ruby
  ruby app.rb -o $IP
  ~~~

- 