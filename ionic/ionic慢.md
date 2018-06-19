如果很久不用ionic,首次build会很慢
### 1.在./platforms/android/build.gradle 和app/build.gradle文件中

```gradle
mavenCentral()     改为
maven { url "http://maven.aliyun.com/nexus/content/groups/public" }

```
### 2.在./platforms/android/project.properties中只保留最新的com.android.support:support-v4和com.android.support:appcompat-v7,并且版本一样
```gradle
cordova.system.library.4=com.android.support:appcompat-v7:27.+
cordova.system.library.6=com.android.support:support-v4:27.+
```

如果用ionic命令build一直卡住没有动,看不到日志的时候,建议用android studio打开./platforms/android下面的项目,用android studio编译,就可以看到具体错误