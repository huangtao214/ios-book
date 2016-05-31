# 1-自定义按钮，图片在上，文字在下

```objc
import UIKit

class ScenarioButton: UIButton {

    // 按钮宽度比例
    let IWTabBarButtonImageRatio:CGFloat = 0.8
    
    // 内部图片frame
    override func imageRectForContentRect(contentRect: CGRect) -> CGRect {
        
        let imageW:CGFloat  = contentRect.size.width - 6;
        let imageH:CGFloat  = contentRect.size.height * IWTabBarButtonImageRatio;
        return CGRectMake(3, 0, imageW, imageH);
    }
    
    // 内部文字的frame
    override func titleRectForContentRect(contentRect: CGRect) -> CGRect {
       
        let titleY:CGFloat = contentRect.size.height * IWTabBarButtonImageRatio;
        let titleW:CGFloat = contentRect.size.width - 6;
        let titleH:CGFloat = contentRect.size.height - titleY;
        return CGRectMake(3, titleY, titleW, titleH);
    }
  
    override init(frame: CGRect) {
        super.init(frame: frame)
   
        // 图标居中
        self.imageView!.contentMode = UIViewContentMode.Center;
        
        // 文字居中
        self.titleLabel!.textAlignment = NSTextAlignment.Center;
    
        //图片缩放
        self.imageView?.contentMode = UIViewContentMode.ScaleAspectFit
    }

    required init?(coder aDecoder: NSCoder) {
        super.init(coder: aDecoder)
        //fatalError("init(coder:) has not been implemented")
    }

}
```