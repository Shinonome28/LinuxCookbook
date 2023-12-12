# wget下载站点

有时在网上看到一些好用的小工具或者想要保存的网页, 想要在脱机下继续查看,
就可以利用wget将其下载下来.

```bash
wget -r -p -np -k <url>
```

说明：

- `-r, –recursive（递归）`
- `-k, –convert-links（转换链接、将 HTML 页面中的链接转换为相对链接即本地链接）`
- `-p, –page-requisites（下载所有的图片等页面显示所需的内容）`
- `-np, –no-parent（不追溯至父级）`

注意有时会出现不能全部下载的现象, 这是因为有些下载是由JavaScript发起的,
wget不能正确识别. 这时可以在chrome打开下载的网页, 
在调试工具找到失败的下载, 并手动从源网站下载.

有时会出现`403 拒绝访问的现象`, 可以尝试通过添加User-Agent的解决:

```bash
wget -U "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/72.0.3626.121 Safari/537.36"
```

还有一种更加彻底的办法, 就是直接扫描下载全站:
```
wget -m <url>
```

最后, 请尊重版权.

---

部分引用自:
- <https://www.cnblogs.com/xing-29391/p/16755039.html>