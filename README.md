# gradle-publish

## step1 : update module's build.gradle
```groovy
ext {
    artifact = ''
    libraryName = ''
    libraryDescription = ''
}

apply from: 'https://raw.github.com/WeiLianYang/gradle-publish/master/publish.gradle'
```

## step2 : update gradle.properties
```
# config
publishedGroupId=io.github.xxx // 发布的groupId
siteUrl=https://github.com/xxx/xxx // 项目主页
gitUrl=https://github.com/xxx/xxx.git // 项目git地址
# developer
developerId=xxx // 开发者id，最好是申请sonatype的fullname
developerName=xxx // 开发者名称
developerEmail=xxx@xxx.com // 开发者email，最好是申请sonatype的email
# license
licenseName=The Apache License, Version 2.0
licenseUrl=http://www.apache.org/licenses/LICENSE-2.0.txt
allLicenses=["Apache-2.0"]
```

## step3 : upload to Maven Central
```groovy
gradle uploadArchives
```
