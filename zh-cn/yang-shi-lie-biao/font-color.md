# 文本颜色

## **函数原型**

```php
fontColor(int $color): self
```

### **int $color**

> RGB 十六进制值 或 颜色常量

## 示例

```php
$config = [
    'path' => './tests'
];

$fileObject  = new \Vtiful\Kernel\Excel($config);

$fileObject = $fileObject->fileName('tutorial.xlsx');
$fileHandle = $fileObject->getHandle();

// 创建样式资源
$format     = new \Vtiful\Kernel\Format($fileHandle);
$colorStyle = $format->fontColor(\Vtiful\Kernel\Format::COLOR_ORANGE)->toResource();

$filePath = $fileObject->header(['name', 'age'])
    ->data([
        ['viest', 21],
        ['wjx',   21]
    ])
    ->setRow('A1', 50, $colorStyle) // 应用样式
    ->output();
```

