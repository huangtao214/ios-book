# NSNotificationCenter 通告

### 1 创建通告
#####说明：
#####selector接受通告的处理函数，加上:标示带参数
#####name 表示通告key值，用于匹配通告
#####object表示通告参数
```objc
swift code:
NSNotificationCenter.defaultCenter().addObserver(self, selector: "outputClick:", name: "outputAV", object: nil)
```

### 2 发送通告

