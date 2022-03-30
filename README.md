# github 作为maven仓库
## maven 引入方法
```xml
<repository>
    <repository>
        <id>hobbit</id>
        <url>https://raw.githubusercontent.com/liuhongyu2017/maven/main</url>
        <snapshots>
            <enabled>true</enabled>
        </snapshots>
    </repository>
</repositories>
```

## maven deploy 方法
```shell
mvn deploy -DaltDeploymentRepository=${distribute_id}::default::file:D:\GitHub
```

## maven 升级版本号
```shell
mvn versions:set -DnewVersion=1.0.1-SNAPSHOT
```