tags: #api #API
up:: [[+主页|Home]]
# local-rest-api

黑曜石的本地REST API
请看我们的互动文档：[https://coddingtonbear.github.io/obsidian-local-rest-api/](https://coddingtonbear.github.io/obsidian-local-rest-api/)
你是否曾经需要自动与你的笔记进行互动？这个插件为Obsidian提供了一个REST API，你可以通过其他工具与你的笔记进行交互，这样你就可以把你需要的东西自动化了。

这个插件提供了一个安全的HTTPS接口，通过api密钥认证，允许你。

读取、创建、更新或删除现有笔记。甚至还有一个PATCH HTTP方法，用于将内容插入到笔记的特定部分。
列出存储在你的保险库中的笔记。
创建和获取周期性笔记。
执行命令并列出可用的命令。
如果你需要从[Obsidian Web](https://chrome.google.com/webstore/detail/obsidian-web/edoacekkjanmingkbkgjndndibhkegad)这样的浏览器扩展中与Obsidian进行交互，这就特别有用。

黑曜石的本地REST API
你可以使用这个界面来尝试你在Obsidian的本地REST API。
在试用下面的工具之前，你要确保按下下面的 "Authorize "按钮，并提供你在打开Obsidian设置中的 "Local REST API "部分时所显示的API Key。所有对API的请求都需要一个有效的API密钥；所以不这样做的话，你就走不远了。

当使用这个工具时，你可能会看到浏览器的安全警告，因为你的浏览器不相信这个插件在第一次运行时生成的自签名证书。如果你这样做，你可以通过在你的浏览器或操作系统的设置中将该证书添加为 "受信任的证书"，使这些错误消失。

Servers




Authorize
Vault Files


库文件
GET /vault/{filename} 返回您保险库中单个文件的内容。
PUT /vault/{filename} 在您的保险库中创建一个新文件或更新一个现有文件的内容。
POST /vault/{filename} 向一个新的或已有的文件添加内容。
PATCH /vault/{filename} 将内容插入到一个现有的笔记中，与该文件的标题相对应。
DELETE /vault/{filename} 在你的保险库中删除一个特定的文件。

库目录
GET /vault/ 列出存在于你的保险库根部的文件。
GET/vault/{pathToDirectory}/ 列出存在于指定目录中的文件。

周期性说明
GET/ periodic/{period}/ 获取当前指定时期的定期报告。
PUT/ periodic/{period}/ 更新一个定期报告的内容。
POST/ periodic/{period}/ 将内容附加到一个定期注释中。
PATCH /periodic/{period}/ 将内容插入相对于该文件中的一个标题的定期注释中。
DELETE /periodic/{period}/ 删除一个周期性笔记。

命令
GET /commands/ 获取可用命令的列表。
POST /commands/{commandId}/ 执行一个命令。

搜索
POST /search/ 搜索符合指定搜索查询的文件
POST/search/simple/ 搜索符合指定文本查询的文件
POST/search/gui/ 搜索符合指定的gui-evaluated查询的文件

打开
POST /open/{filename} 在黑曜石中打开指定的文件

状况
GET / 返回关于服务器的基本细节。

