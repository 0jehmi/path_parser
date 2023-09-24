# What is path_parser

path_parser는 지정한 패턴의 템플릿을 생성하고 

패턴과 선택한 경로를 매칭시켜서 원하는 경로 값을 파싱해주는 도구입니다.

# How to use path_parser

1.  path_parse.py를 연다.
2. 클래스를 불러옵니다.
```
> ps = PathSearch()
```
3.  init의 self._json_path에 json파일을 저장할 경로를 입력합니다.
```
self._json_path = "json저장경로/lucidity.json"
```
4. 원하는 템플릿 이름과 패턴을 추가해줍니다.
```
> ps.add_temp('이름','/패턴경로/{추출하고 싶은 값}')
```
5. 추가한 템플릿 이름 중 원하는 템플릿 이름을 입력합니다.
```
> ps.set_temp_name = '이름'
```
6. 추출하고 싶은 파일의 경로를 적어줍니다.
```
> print(ps.set_path('/파일경로'))
```

# Examples
2.
```
ps = PathSearch()
```
3.
```
self._json_path = "C:/Users/home/Desktop/github/test_file/lucidity.json"
```
4.
```
ps.add_temp('nuke','C:/Users/home/Desktop/github/test_file/show/{project}/seq/{seq}/{shot}/{ver}/{dept}/{project}_{seq}_{shot}_{dept}_{ver}_{padding}.{ext}')
```
5.
```
ps.set_temp_name = 'nuke'
```
6.
```
print(ps.set_path('C:/Users/home/Desktop/github/test_file/show/IHJ/seq/s0010/0010/v001/comp/IHJ_S0010_0010_comp_v001_0000.jpg'))
```
Result
```
{'dept': 'comp', 'ext': 'jpg', 'padding': '0000', 'project': 'IHJ', 'seq': 'S0010', 'shot': 0010', 'ver': 'v001'}
```
