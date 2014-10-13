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
