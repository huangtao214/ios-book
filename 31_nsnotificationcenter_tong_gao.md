# NSNotificationCenter 通告

### 1 创建通告
#####说明：
#####selector：接受通告的处理函数，加上:标示带参数
#####name： 表示通告名称，用于匹配通告
#####object：表示通告参数
```objc
swift code:
NSNotificationCenter.defaultCenter().addObserver(self, selector: "outputClick:", name: "outputAV", object: nil)
```
### 2 通告处理
```objc
 func inputClick(obj: NSNotification) {
        let btn = obj.object as! AVButton
        print(btn.tag)
    }
```

### 3 发送通告
#####注意：通告名称要一致，否则接收通告失败
```objc
NSNotificationCenter.defaultCenter().postNotificationName("outputAV", object: item)
```
