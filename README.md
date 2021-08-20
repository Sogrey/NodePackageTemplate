# NodePackageTemplate
npm 包模板

## 注册npm账户

前往[官网](https://www.npmjs.com/)注册账号,记住用户名、密码、邮箱。

## 添加账户
使用以下命令添加npm的账户名、密码和邮箱即可：
``` bash
npm adduser
```
> 如果遇到使用了taobao镜像源导致添加账户失败，可切换回npm官方源:
> ``` bash
> npm config set registry https://registry.npmjs.org/
> ```
> 因为taobao镜像源是只读的。


## 发布到npm

发布前检查是否已存在同名package，在[官网](https://www.npmjs.com/)直接搜索你要命名的名字，即package.json中`name`字段，如果已存在需要更名，不得重复。

发布：
``` bash
npm publish
```
因为包名带有@符，使用如下命令发布到npm表示公开:
``` bash
npm publish --access public
```

> 每次发布版本需要修改版本号

## 撤销发布包

如果发现已经发布的版本有问题，可以进行撤销操作：
``` bash
npm unpublish <packagename>@<version>
```
如果有权限问题，撤销不了，可以添加`--force`。

撤销还是有诸多限制的：

1. 根据规范，只有在发包的24小时内才允许撤销发布的包（ unpublish is only allowed with versions published in the last 24 hours）
2. 即使你撤销了发布的包，发包的时候也不能再和被撤销的包的名称和版本重复了（即不能名称相同，版本相同，因为这两者构成的唯一标识已经被“占用”了）
