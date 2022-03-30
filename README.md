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
// 升级
mvn versions:set -DnewVersion=1.0.1-SNAPSHOT
// 回退
mvn versions:revert
// 确认
mvn versions:commit
```
|参数|默认值|说明|
|----|----|----|
|allowSnapshots|false|是否更新-snapshot快照版|
|artifactId|${project.artifactId}|指定artifactId|
|generateBackupPoms|true|是否生成备份文件用于回退版本号|
|groupId|${project.groupId}|指定groupId|
|newVersion||设置的新版本号|
|nextSnapshot|false|更新版本号为下一个快照版本号|
|oldVersion|${project.version}|指定需要更新的版本号可以使用缺省'*'|
|processAllModules|false|是否更新目录下所有模块无论是否声明父子节点|
|processDependencies|true|是否更新依赖其的版本号|
|processParent|true|是否更新父节点的版本号|
|processPlugins|true|是否更新插件中的版本号|
|processProject|true|是否更新模块自身的版本号|
|removeSnapshot|false|移除snapshot快照版本，使之为release稳定版|
|updateMatchingVersions|true|是否更新在子模块中显式指定的匹配版本(如/项目/版本)|