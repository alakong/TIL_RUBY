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



