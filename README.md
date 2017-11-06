# AndroidUnKillService

### START_STICKY
https://stackoverflow.com/a/47129517/5381331
If you use START_STICKY, when you kill app from recent task, your service will be killed
(`onTaskRemoved` fired, `onDestroy` NOT fired) THEN it will auto start again
(`onCreate` fired, `onStartCommand` fired).

However, for some device like `Xiaomi`, `Huawei` service won't start again after kill from Recent because
this manufacturer also Fore Close app when kill app from Recent

### onDestroy

`onDestroy` fired when we kill service normally by `Context.stopService(...)` or `stopSelf`
inside Service.
`onDestroy` fired when we kill service inside Setting->Running Process->MyService->Stop

### onTaskRemoved

Normally `onTaskRemoved` fired when we kill app from `Recent App` but for some device like `Xiaomi`
`onTaskRemoved` not fired (after my self test on Xiomi 5.0.2)