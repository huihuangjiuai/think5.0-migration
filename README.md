此插件的项目环境为php8.0 thinkphp5.0.24
原项目为  thinkphp-migration:1.1.1

此插件建立的目的是为了兼容php8版本的环境,php8环境下变量类型要求严格，之前很多模棱两可的函数用法会出现错误，比如
原插件的Phinx/Util/Util.php文件
$fileName = static::getCurrentTimestamp() . '_' . strtolower(implode( $arr,'_')) . '.php';
此行代码的implode($arr,'_')函数，在php8环境中会出现错误，  Type error: implode(): Argument #2 ($array) must be of type ?array, string given  
应该这么用，implode('_',$arr)。具体原因请自行查看php官方文档。

# thinkphp5.0 数据库迁移工具

## 安装
~~~
composer require huihuangjiuai/think5.0-migration
~~~
