```kotlin
XposedBridge.hookAllMethods(Application::class.java, "dispatchActivityResumed", object : XC_MethodHook() {
    override fun afterHookedMethod(param: MethodHookParam) {
        super.afterHookedMethod(param)

        mCurrentActivity = param.args[0] as Activity
    }
})
```
```kotlin
XposedBridge.hookAllMethods(Instrumentation::class.java, "callApplicationOnCreate", object : XC_MethodHook() {
    override fun afterHookedMethod(param: MethodHookParam) {
        super.afterHookedMethod(param)
        
        mApplication = param.args[0] as Application
    }
})
```
