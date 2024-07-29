# Youtube2Bilibili
这是一个可以将YouTube视频/频道一键搬运到B站的脚本。具体步骤如下：

1. 首先，修改配置文件：
```
OWNER_NAME = "username" // 你的B站账号名
REMOVE_FILE = True  //是否删除投稿后的视频文件
LineN = "qn"  //线路，如cos、bda2、qn、ws、kodo
DEFAULT_TID = 21
PROXY = 'http://192.168.99.148:20171' //代理地址，在使用境外VPS时可以不填，但要删除所有与代理（PROXY）相关的参数
COOKIES_FROM_BROWSER = ("firefox",)
URL_LIST_FILE = "url_list.json"
```

2. 在配置完成之后，访问 [这个链接](https://github.com/biliup/biliup-rs) 下载最新的release并解压到根目录（即biliup 可执行文件和 upload.py 在同一个目录下）。你需要手动创建一个空文件夹，命名为 "videos"。

3. 接下来，执行 `pip install -r requirements.txt` 来安装所有必要的依赖。

4. 执行 `./biliup login` 并选择扫码登录。

5. 根据你的操作系统，你可能需要修改 `"biliup upload"` 的路径。如果你使用的是 windows 操作系统，那么这一步可以跳过。在其他平台上，你需要将它改为 `./biliup upload`。

6. 最后，运行 `python upload.py`。这个脚本有三种模式，模式1会上传单个视频，模式2会上传播放列表。如果你使用的链接是像 `https://www.youtube.com/@user/streams` 这种格式的，它将会被看作一个播放列表，脚本将会搬运所有的直播。模式3是断点续传，在模式2生成的 url_list.json 文件存在的情况下，脚本将会继续上传状态为 "no" 的视频。

以上步骤完成后，就可以实现YouTube视频到Bilibili的自动搬运了。

如果有任何疑问，请参阅README文件。
---
# Youtube2Bilibili
This is a script that can transfer videos/channels from YouTube to Bilibili with a single click. Here are the steps:

1. First, modify the configuration file: 
```python
OWNER_NAME = "username" // Your Bilibili account name
REMOVE_FILE = True  // Whether to delete the video file after contribution
LineN = "qn"  // Line, such as cos, bda2, qn, ws, kodo
DEFAULT_TID = 21
PROXY = 'http://192.168.99.148:20171' // The proxy address, you can leave it blank when using an overseas VPS, but you need to delete all parameters related to proxy (PROXY)
COOKIES_FROM_BROWSER = ("firefox",)
URL_LIST_FILE = "url_list.json"
```

2. After the configuration is complete, visit [this link](https://github.com/biliup/biliup-rs) to download the latest release and extract it to the root directory (i.e., the biliup executable file and upload.py are in the same directory). You need to manually create a blank folder named "videos".

3. Next, run `pip install -r requirements.txt` to install all the necessary dependencies.

4. Execute `./biliup login` and choose to log in by scanning the QR code.

5. Depending on your operating system, you may need to modify the path of "biliup upload". If you are using the Windows operating system, you can skip this step. On other platforms, you need to change it to `./biliup upload`.

6. Finally, run `python upload.py`. There are three modes for this script. Mode 1 will upload a single video, Mode 2 will upload a playlist. If you use a link like `https://www.youtube.com/@user/streams`, it will be regarded as a playlist and the script will transfer all live streams. Mode 3 is breakpoint resumption. If the url_list.json file generated in Mode 2 exists, the script will continue to upload videos with the "no" status.

After completing the above steps, you can automatically transfer videos from YouTube to Bilibili.

If you have any questions, please refer to the README file.
