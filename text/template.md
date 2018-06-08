## 文本与空格

为了同时保证代码的可读性 和 文本实际输出内容的紧凑性，可以使用`{{ -}}` 或 `{{- }}`来进行文本内容格式化。

如果你输出 `x<y`你可能这么写： 
```
{{x}}<{{y}}
```
但是这样写代码，可读性太差来，代码太紧凑，当你有更多的单词，`if`,`range`之类的语句在一起时，更难看清一个表达式，因此可以这么写:

```
{{x -}} < {{- y}}
输出为：
x<y
中间的空格都去掉了，也保证了代码可读性。
```

通过使用`-`来删除空格。

看一个实例代码：

```
if ( $request_uri !~ /{{range $index, $abVersion := $project.ABVersion}}({{$abVersion.Tag}}){{if ne $index $project.VersionLength}}|{{end}}{{end}} )/
{
     rewrite ^(.*)/{{$project.Name}}/(.*)$ $1/{{$project.Name}}/${{$project.Name}}_var/$2 break;
}
```
为了保证nginx的语法正确，模版写的非常紧凑，可读性并不好，所以修改成下面这样

```

```
