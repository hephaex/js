# YAML
* 정의
 - YAML Ain't Makrup Language
 - YAML is a human friendly data serialization standard for all programming language
 - 구조 데이터의 표현 기법
 - 설정파일, data 저장할 때 사용
* [공식사이트](http://yaml.org)
!
* 필요지식:  ruby

## YAML을 사용해 보자.

```
$ touch mydata.yml
$ parse.rb
```

```mydata.yml
bash-4.1# cat mydata.yml
- d1
- d2
- d3
```

```parse.rb
require 'yaml'

d = YAML.load_file('mydata.yml')
p d
```

* 실행해 보자.
```
bash-4.1# ruby parse.rb
["d1", "d2", "d3"]
```

## 시퀀스를 사용해 보자.
* 시퀀스 (배열)
* 매핑 (해쉬): -(공백)data
* -뒤에 반드시 공백이 필요함.
* 탭은 사용하지 않으며 주로 공백x2를 사용

* 예시 3-1
```mydata.yml
- d1
- d2
- d3
```

```
["d1", "d2", "d3"]
```

* 예시 3-2
```mydata.yml
- d1
-
  - x1
  - x2
- d3
```

```
["d1", ["x1", "x2"], "d3"]
```

* 예시 3-3: d2를 쓸 경우 이하는 자료로 함께 인식된다.
```mydata.yml
- d1
- d2
  - x1
  - x2
- d3
```

```
bash-4.1# ruby parse.rb
["d1", "d2 - x1 - x2", "d3"]
```

## 매핑: 키값과 값을 함께 쓴다.
* key:(공백)value

* 예시 4-1
```
name: hephaex
email: hephaex@gmail.com
```

```
bash-4.1# ruby parse.rb
{"email"=>"hephaex@gmail.com", "name"=>"hephaex"}
```

* 예시 
```
name: hephaex
emails:
  main: hephaex@gmail.com
  sub: hephaex@yahoo.co.kr
```

```
{"email"=>{"sub"=>"hephaex@yahoo.co.kr", "main"=>"hephaex@gmail.com"}, "name"=>"hephaex"}
```

## 복잡한 자료 구조를 사용해 보자.

```
- name: hephaex
  email: hephaex@gmail.com
- name: hephaex2
  email: hephaex+sub@gmail.com
```
```
[{"email"=>"hephaex@gmail.com", "name"=>"hephaex"}, {"email"=>"hephaex+sub@gmail.com", "name"=>"hephaex2"}]
```

* 해쉬에 시쿼스를 넣을수도 있다.
```
name:
  - apple
  - banana
cost:
  - 1000
  - 2000
```
```
{"cost"=>[1000, 2000], "name"=>["apple", "banana"]}
```

## block style, flow style

* block style
```
- d1
- d2
- d3
```

* flow style
```
[d1, d2]
```

* hash flow style
```
{name: apple}
```

```
name: [apple, banana]
cost: {apple: 1000, banana: 2000}
```
```
{"cost"=>{"apple"=>1000, "banana"=>2000}, "name"=>["apple", "banana"]}
```

## 각종 데이터를 표현해보자.
* 문자열:
```
str: hello
```

* 숫자:
```
num1: 5
num2: 3.14
```

* 진리값:
```
bool1: true
bool2: false
```

* nothing: null
* date: 2014-10-12
* d1: "5"

```
{"nothing"=>nil, "cost"=>{"banana"=>2000, "apple"=>1000}, "name"=>["apple", "banana"], "d1"=>"5", "date"=>#<Date: 4913885/2,0,2299161>, "bool2"=>false, "bool1"=>true, "num2"=>3.14, "num1"=>5}
```

## 개행을 포함한 데이터를 처리해 보자.

```
doc1:
  aaa
  bbb
  ccc
```

* 매행에 개행문자가 포함
```
doc2: |
  aaa
  bbb
  ccc
```

* 마지막만 개행이 들어감.
```
doc3: >
  aaa
  bbb
  ccc
```

* 시쿼스로 가능함.
```
- |
 aaa
 bbb
 ccc
```

* 실행결과
```
doc1:
  aaa
  bbb
  ccc
doc2: |
  aaa
  bbb
  ccc
doc3: >
  aaa
  bbb
  ccc
```

```
{"doc3"=>["aaa\nbbb\nccc\n"], "doc2"=>"aaa\nbbb\nccc\n", "doc1"=>"aaa bbb ccc"}
```

```
- |
  aaa
  bbb
  ccc
```
```
["aaa\nbbb\nccc\n"]
```

## ... 와 --- 를 사용해 보자.
* '...': 해석을 끝냄
```
- d1
- d2
...
- d3
```
```
["d1", "d2"]
```

* '---': 데이터를 구분함
```
---
- d1
- d2
- d3
---
- x1
- x2
```

```parse.rb
require 'yaml'

File.open('mydata.yml') do |io|
  YAML.load_documents(io) do |d|
      p d
  end
end
```
```
["d1", "d2", "d3"]
["x1", "x2"]
```
