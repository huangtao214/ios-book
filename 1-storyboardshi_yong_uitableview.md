# storyboard使用UITableView


## 1 添加代理
###  1.1 代码实现 
#####  1.1.1 控制器继承 UITableViewDelegate 和 UITableViewDataSource
#####  1.1.2 添加代码
```objc 
table.delegate = self // 绑定委托
table.dataSource = self //绑定代理
```
###   2.1 界面实现
#####在storyboard中，选中uitableview， 按住 ctrl 后，拖线到黄色图标的控制器中
#####然后，选中 delegate，和dataSoruce,注意2个都要连线。



## 2 添加数据源
###2.1 注册cell，
#####说明：UITableViewCell.self 为cell类，可以自定义，“cell”为标识符，可以任意
```objc
table.registerClass(UITableViewCell.self, forCellReuseIdentifier: "cell")
```
###2.2 创建cell
##### 2.2.1 创建表格行数,创建10行
```objc
func tableView(tableView: UITableView, numberOfRowsInSection section: Int) -> Int {
        return 10
    }
```
##### 2.2.2 添加cell
```objc
func tableView(tableView: UITableView, cellForRowAtIndexPath indexPath: NSIndexPath) -> UITableViewCell {
        let cell = table.dequeueReusableCellWithIdentifier("cell",forIndexPath: indexPath)
        cell.textLabel?.text = "cell \(indexPath.row)"
        return cell
    }
```


