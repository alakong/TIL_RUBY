# Ruby

#### 0.개요

1. 루비는 순수 객체지향 언어-모든 것이 객체
2. Ruby on Rails 프레임워크의 등장으로 부상
3. 두칸 띄어쓰기를 추천
4. 세미콜론(;)이 없음/여러 코드 한줄쓰기를 위해 사용할 수는 있음
5. #으로 주석처리

#### 1. puts vs print

```ruby
3.times {print "hello"}
#hellohellohello => 3 
3.times {puts "hello"}
#hello
#hello
#hello
# => 3 
```

#### 2. puts vs p

~~~ruby
a= "ruby"
puts a
#=>ruby
p a
#=>"ruby"

array=[1,2,3]
puts array
1
2
3
 => nil 
p array
[1, 2, 3]
 => [1, 2, 3] 
~~~



#### 3.Naming convention

- 변수 
  - snake_case
- 상수 
  - CONSTANT
- 클래스 
  - CamelCase

#### 4.pry

- 설치
  - `gem install pry`
- 실행
  - `pry`

#### 5. Inline statement

``` ruby
#if
puts "a=0" if a==0  #"a=0"
puts "a=0" if a==1  #출력X

#while
c=0
result =c+=2 while c<50
puts result #50

    puts "hi" if 0 # hi
    #0 is true

```



#### 6. Case

~~~ruby
 #case
    [18] pry(main)> name ="yoojung"
=> "yoojung"
[19] pry(main)> case name
[19] pry(main)* when "yoojung" then puts "hi"  
[19] pry(main)* when "yuu" then puts "hiiiii2"  
[19] pry(main)* else puts "hello"  
[19] pry(main)* end  
hi
=> nil
[20] pry(main)> 
~~~



#### 7.method

- 대부분의 언어

  - 클래스 안: function
  - 클래스 밖: method

- 루비에서는 모든 function은 method

- ```ruby
  #루비에서의 메소드 선언
  [4] pry(main)> def simple
  [4] pry(main)*   puts "method simple"  
  [4] pry(main)* end  
  => :simple
  [5] pry(main)> simple
  method simple
  => nil
  
  #()를 명시적으로 적어줄 수도 있음
  [4] pry(main)> def simple()
  [4] pry(main)*   puts "method simple"  
  [4] pry(main)* end 
  ```

- ~~~ruby
  #return
  [7] pry(main)> def add(a,b)
  [7] pry(main)*   return a+b
  [7] pry(main)* end  
  => :add
  [8] pry(main)> add 1,2
  => 3
  
  #return이 없어도 마지막 행이 자동으로 return행으로 됨
  [9] pry(main)> def add2(a,b)
  [9] pry(main)*   a+b
  [9] pry(main)* end  
  => :add2
  [10] pry(main)> add2 1,2
  => 3
  
  #return을 선택적으로 사용 가능
  [11] pry(main)> def divide(a,b)
  [11] pry(main)*   return "Idon't think so" if b==0                                                                                                  
  [11] pry(main)*   a/b
  [11] pry(main)* end  
  => :divide
  [12] pry(main)> divide 2,0
  => "Idon't think so"
  [13] pry(main)> divide 4,2
  => 2
  ~~~

- 기본 매개변수

- ~~~ruby
  def factorial(n)
      n==0? 1 : n*factorial(n-1)
  end
  
  factorial
  #매개변수 안넣고 부르면 에러
  #ArgumentError: wrong number of arguments (given 0, expected 1)from (pry):39:in `factorial'
  
  #매개변수에 10을 디폴트로 넣음
  def factorial_default(n=10)
      n==0? 1 : n*factorial(n-1)
  end
  
  factorial_default
  #=> 3628800
  
  ~~~

#### 8. block

~~~ruby

# 0부터 2까지 세번의 값을 asdf에 담고 밑에 코드인 출력하는 코드를 실행하는 것
[29] pry(main)> 3.times do |asdf|                                                      [29] pry(main)*   puts asdf  #이 부분이 블럭
[29] pry(main)* end  
0
1
2
=> 3

#
3.times {puts "hello"}

# 
[31] pry(main)> def hihi
[31] pry(main)*   return "noBlock" unless block_given?
[31] pry(main)*   yield 
[31] pry(main)* end  
=> :hihi
[32] pry(main)> hihi
=> "noBlock"
[33] pry(main)> hihi{puts"hihi"}
hihi
=> nil

~~~

#### 9. String

~~~ruby
# '' vs ""
a="안녕.\n whfflek"
puts a
안녕.
 whfflek

b='dkssud\n sjanwhfflek'
puts b
dkssud\n sjanwhfflek

[39] pry(main)> name="yoojung"
=> "yoojung"
[40] pry(main)> a="#{name}님 안녕하세요 "                                                                                                           
=> "yoojung님 안녕하세요 "
[41] pry(main)> b='#{name}님 안녕하세요 '
=> "\#{name}님 안녕하세요 "
[42] pry(main)> puts a
yoojung님 안녕하세요 
=> nil
[43] pry(main)> puts b
#{name}님 안녕하세요 
=> nil
[44] pry(main)> 

#upcase=>뒤에 !를 붙이면 upcase상태로 바로 변수에 저장됨
[45] pry(main)> my_name="you jung"
=> "you jung"
[46] pry(main)> my_name.upcase
=> "YOU JUNG"
[47] pry(main)> my_name.upcase!
=> "YOU JUNG"
[48] pry(main)> my_name
=> "YOU JUNG"


~~~

#### 10. Array

~~~ruby
[53] pry(main)> array=[]
=> []
[54] pry(main)> array<<5
=> [5]
[55] pry(main)> array<<10
=> [5, 10]
[56] pry(main)> array
=> [5, 10]
[57] pry(main)> arr=[]
=> []
[58] pry(main)> arr<<1
=> [1]
[59] pry(main)> arr<< "string"
=> [1, "string"]

[60] pry(main)> arr<<:s
=> [1, "string", :s]
[61] pry(main)> arr<< true
=> [1, "string", :s, true]
[62] pry(main)> arr[1]
=> "string"
[63] pry(main)> arr[-1]
=> true
[64] pry(main)> arr[-2]
=> :s
[65] pry(main)> arr[1..2]
=> ["string", :s]
[66] pry(main)> arr << 5
=> [1, "string", :s, true, 5]
[67] pry(main)> arr.push 999
=> [1, "string", :s, true, 5, 999]
[69] pry(main)> arr.pop 1                                                             
=> [999]
[70] pry(main)> arr
=> [1, "string", :s, true, 5]
[71] pry(main)> arr.shift 1
=> [1]
[72] pry(main)> arr
=> ["string", :s, true, 5]
[73] pry(main)> 

~~~

#### 11.hash

-  key value 로 이루어져있다.

- ~~~ruby
  #hash 3가지 방식
  hash1 = {:key => value}
  hash2= {key: value}
  hash3= {"key" => value}
  
  ~~~

- each 반복하기

- ~~~ruby
  hash1.each do |k,v|
      #k,v는 어떠한 문자로 적어도 됨
      puts "#{keyy}:#{valuee}"
       end  
  
  name:youjung
  age:27
  hometown:ko
  => {:name=>"youjung", :age=>27, "hometown"=>"ko"}
  ~~~

- https://gist.github.com/nacyot/7624036

