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
