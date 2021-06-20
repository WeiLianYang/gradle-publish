# gradle-publish

## step 1 : update module's build.gradle
```groovy
ext {
    artifactId = ''
    libraryName = ''
    libraryDescription = ''
}

apply from: 'https://raw.github.com/WeiLianYang/gradle-publish/master/publish.gradle'
```

## step 2 : update gradle.properties
```
# config
publishedGroupId=io.github.xxx
siteUrl=https://github.com/xxx/xxx // Project home page
gitUrl=https://github.com/xxx/xxx.git // Project git address
# developer
developerId=xxx // sonatype fullname
developerName=xxx // sonatype name
developerEmail=xxx@xxx.com // Developer email, preferably Sonatype email
# license
licenseName=The Apache License, Version 2.0
licenseUrl=http://www.apache.org/licenses/LICENSE-2.0.txt
allLicenses=["Apache-2.0"]

```


## step 3 : Update your home gradle.properties
You need to configure the username and password in the home gradle.properties. The location defaults to USER_HOME/.gradle/gradle.properties.
```
# mavenCentral config data
signing.keyId=The last 8 bits of GPG certificate fingerprint
signing.password=GPG password
signing.secretKeyRingFile=GPG certificate path
# sonatype account
ossrhUsername=
ossrhPassword=
```

> If you don't have a GPG certificate, create a new one by referring to the [documentation](https://central.sonatype.org/publish/requirements/gpg/)

## step 4 : upload to Maven Central
```groovy
gradle uploadArchives
```
