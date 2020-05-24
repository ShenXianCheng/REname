# 解决github图片显示异常问题

### 一：问题：github网站内部图片显示异常

有博主总结：

>实际上，可以认为，`ERR_CERT_COMMON_NAME_INVALID`就是用一个错误的域名访问了某个节点的`https`资源。导致这个错误的原因，基本是：
>
>1. dns污染
>2. host设置错误
>3. 官方更新了dns，但是dns缓存没有被更新，导致错误解析。

### 二：解决办法

使用本地`hosts`文件对网站进行解析，一般的`DNS`问题都可以通过修改`host`文件解决。将域名解析直接指向`IP`地址来绕过`DNS`的解析，以此解决污染问题。

#### 2.1 找到URL

在任意未显示的图片上使用**元素选择器**放在显示不了的图片上，**右键-检查元素**，定位到该图片的标签，得到它的**URL**。

#### 2.2 获取URL

打开[IPAddress.com](https://www.ipaddress.com/)，搜索获得的**URL**。

#### 2.3 修改hosts

**windows系统**：在`C:\Windows\System32\drivers\etc\hosts`文件后面加上你所获得的**URL**保存即可。

**Linux系统：**



这里提供的均为2019.5月更新的。

```
# GitHub Start 
140.82.113.3      github.com
140.82.114.20     gist.github.com

151.101.184.133    assets-cdn.github.com
151.101.184.133    raw.githubusercontent.com
151.101.184.133    gist.githubusercontent.com
151.101.184.133    cloud.githubusercontent.com
151.101.184.133    camo.githubusercontent.com
151.101.184.133    avatars0.githubusercontent.com
199.232.68.133     avatars0.githubusercontent.com
199.232.28.133     avatars1.githubusercontent.com
151.101.184.133    avatars1.githubusercontent.com
151.101.184.133    avatars2.githubusercontent.com
199.232.28.133     avatars2.githubusercontent.com
151.101.184.133    avatars3.githubusercontent.com
199.232.68.133     avatars3.githubusercontent.com
151.101.184.133    avatars4.githubusercontent.com
199.232.68.133     avatars4.githubusercontent.com
151.101.184.133    avatars5.githubusercontent.com
199.232.68.133     avatars5.githubusercontent.com
151.101.184.133    avatars6.githubusercontent.com
199.232.68.133     avatars6.githubusercontent.com
151.101.184.133    avatars7.githubusercontent.com
199.232.68.133     avatars7.githubusercontent.com
151.101.184.133    avatars8.githubusercontent.com
199.232.68.133     avatars8.githubusercontent.com

# GitHub End
```

