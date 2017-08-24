
**add below in AndroidManifest.xml**
```
<application>
        <!-- 百度推送消息监听器，只需要这个，其它的BaiduPushLib 已做处理 -->
        <receiver
            android:name=".push.PushReceiver"
            tools:ignore="ExportedReceiver">
            <intent-filter>
                <!-- 接收push消息 -->
                <action android:name="com.baidu.android.pushservice.action.MESSAGE" />
                <!-- 接收bind、setTags等method的返回结果 -->
                <action android:name="com.baidu.android.pushservice.action.RECEIVE" />
                <!-- 接收通知点击事件，和通知自定义内容 -->
                <action android:name="com.baidu.android.pushservice.action.notification.CLICK" />
            </intent-filter>
        </receiver>
</application>
```
**add below in module build.gradle**

compile 'com.github.DonaldDu:BaiduPush:5.8.0.0'
