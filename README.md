# CVE-2022-22965-rexbb
springboot core 命令执行漏洞，CVE-2022-22965漏洞利用工具，基于JavaFx开发，图形化操作更简单，提高效率。

### 2022年12月28日-周三-21:44

这几天在做漏洞复现，突然发现之前错过了很多经典的漏洞，也包括这个sping core的rce，所以网上查了很多资料，发现还挺有意思的，但是抓包和发包实在是太麻烦（其实不麻烦，只是我懒，每次改请求包特备麻烦），所以有了现在的这个CVE-2022-22965的图形化漏洞利用工具——Rexbb.jar❤️。

#### 一、工具展示与说明

外观上没有过多的花里胡哨，就是实现最基本的自动写马+任意命令执行，工具是基于jdk1.8开发的，也就是java8，因为jdk8适用范围广一点，所以我就没用高版本的jdk去开发了。

<img width="450" alt="图片" src="https://user-images.githubusercontent.com/64825932/209821940-69978531-5607-40d2-9f4c-a08704bb485f.png">

之前我的其他工具很多小伙伴说不能运行😤，后面我逐个私信才发现都是你们自身电脑的java环境问题出错了才运行不了😁。为了避免类似的事情的发生，我都会在上传Github前自己虚拟机jdk1.8运行一遍再加 其他人的电脑里运行，都没问题，如果你再和我说java版本一样但是运行不了，那就是你们电脑java环境的问题了🤔。

<img width="400" alt="图片" src="https://user-images.githubusercontent.com/64825932/209822719-0260c44e-327e-44fa-9043-1243a4292a8c.png">

#### 二、工具使用

① 这里我用vulfocus的靶场来进行测试，启动靶场后，输入url，先点击“发送payload”按钮。

<img width="500" alt="图片" src="https://user-images.githubusercontent.com/64825932/209824227-41e56fd7-f29c-4ca2-abc9-d84f8c2c2e21.png">

② 点击完发送payload之后，会显示发送paylaod之后的响应包html内容，然后再第二个文本框内就会显示完整的url，📢注意！！这个文本框我设置了不可编辑，使用者是修改不了的，我是怕大家乱改，导致后面的命令执行不成功，所以直接干脆不准修改了，只做显示的输出。如下图：

<img width="500" alt="图片" src="https://user-images.githubusercontent.com/64825932/209824488-7a54834c-0de6-4af4-9d25-d46bf891ca07.png">

③ 显示完url之后，就可以点击第二个按钮，rce检测了，这里直接就执行whomai，可以把命令执行的结果回显到大的文本框里，如下图所示：

<img width="500" alt="图片" src="https://user-images.githubusercontent.com/64825932/209824783-8cabf9e7-e7f1-40e8-b36b-c842b26fce1c.png">

④ 如果想执行其他命令，就可以在下面的小文本框里执行其他命令，这里直接 ls /tmp,命令执行成功，拿到flag。其他命令也是可以的。

<img width="500" alt="图片" src="https://user-images.githubusercontent.com/64825932/209825095-40e2cb21-4c09-4adf-91a0-6732c0a326fd.png">

想了解该工具背后的原理和开发思路，或者是漏洞原理和具体步骤的，可以参考我的这篇博客，里面有该漏洞的bp抓包复现和工具的开发大致思路，不足之处还望多多批评🙏

[http://t.csdn.cn/Gp5eX](https://blog.csdn.net/weixin_43847838/article/details/128475095)https://blog.csdn.net/weixin_43847838/article/details/128475095



