完美解决gradle依赖库导致build慢的问题
https://www.jianshu.com/p/ab1f5e5f5f5c

mavenCentral镜像仓库地址
http://maven.aliyun.com/nexus/content/groups/public/
jentral镜像仓库地址
http://maven.aliyun.com/nexus/content/repositories/jcenter
google镜像仓库地址
http://maven.aliyun.com/nexus/content/repositories/google
我们更新工程的build.gradle成如下形式

```gradle
buildscript {
    repositories {
//        mavenCentral()
//        jcenter()
//        google()
        <!-- maven { url 'https://plugins.gradle.org/m2/' } -->
        maven { url 'http://maven.aliyun.com/nexus/content/repositories/google' }
        maven { url 'http://maven.aliyun.com/nexus/content/groups/public/' }
        maven { url 'http://maven.aliyun.com/nexus/content/repositories/jcenter'}
    }
    dependencies {
        classpath 'com.android.tools.build:gradle:3.0.1'
    }
}

allprojects {
    repositories {
//        mavenCentral()
//        jcenter()
//        google()
        <!-- maven { url 'https://plugins.gradle.org/m2/' } -->
        maven { url 'http://maven.aliyun.com/nexus/content/repositories/google' }
        maven { url 'http://maven.aliyun.com/nexus/content/groups/public/' }
        maven { url 'http://maven.aliyun.com/nexus/content/repositories/jcenter'}
    }
}
```