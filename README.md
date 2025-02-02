# 123云盘 下载工具
[发行版](https://github.com/naiheSH/123)
## 项目介绍
#### 下载工具
123云盘下载工具是一个使用 Python 编写的脚本，通过模拟安卓客户端协议来绕过 123云盘的自用下载流量限制。该工具可以帮助用户在电脑上方便地下载 123云盘上的文件，并提供了多种操作功能，如列出文件、下载文件、上传文件、分享文件等。
# 一、123云盘下载工具
## 功能特点

- **登录**：使用用户名和密码登录 123Pan 账号。
- **列出文件**：显示当前目录下的所有文件和文件夹。
- **下载文件**：通过模拟安卓客户端协议下载文件，绕过流量限制。
  
  文件均下载到同目录下的download文件夹，下载时使用.123pan后缀，完成后重命名为文件原始名称。
- **上传文件**：将本地文件上传到 123Pan。
- **分享文件**：生成文件分享链接。
- **删除文件**：删除指定的文件或文件夹。
- **创建文件夹**：在当前目录下创建新文件夹。

## 使用方法

**运行python脚本。**
- **非python版本已发布，详见[发行版](https://github.com/naiheSH/123)**

### 脚本运行
#### 环境准备

1. 确保已正确安装并配置 Python 3.x。

2. 克隆或下载本项目代码到本地，在项目目录打开终端

3. 安装所需的 Python 库：
   
   ```bash
   pip install -r requirements.txt
   ```

#### 运行脚本


1. 打开终端或命令提示符，进入项目目录。

2. 运行脚本：
   
   使用Windows环境
   ```bash
   python win.py
   ```

   使用Termux环境
   ```bash
   python android.py
   ```
   
   使用web协议（不建议，已停止更新）
   
   ```bash
   python web.py
   ```

### 命令

- **登录**：`log`

- **列出文件**：`ls`

- **刷新目录**：`re`

- **下载文件**：直接输入文件编号或者

  `download <文件编号>`
  
  Android协议下使用download命令可以直接下载文件夹

- **获取下载链接** `link <文件编号>`

- **分享文件**：`share`

- **删除文件**：`delete <文件编号>`

- **创建文件夹**：`mkdir <文件夹名称>`

- **切换目录**：直接输入文件夹编号，或

  `cd <目录编号>`
  
  使用`cd ..` 返回上一级目录<br>
  
- **上传文件**：`upload`，然后输入文件路径

- **直接输入数字**：进入文件夹，或是下载文件

- **退出**：`exit`

### 示例

1. 登录：
   
   ```bash
   > log
   ```

2. 列出文件：
   
   ```bash
   > ls↵
   ```

3. 下载文件：
   
   ```bash
   > download 1↵
   ```
   
   或直接输入文件编号：
   
   ```bash
    >54↵
   1.20.0.01_v8a.apk  193.53M
   press 1 to download now: 1↵
   1.20.0.01_v8a.apk    193.53M
    [██████████████████████████████████████████████████] 100%  
   ok
   ```
   
   下载文件夹（android）：
   
   打包下载依旧会受到流量限制，递归下载无限制，请尽量使用递归下载。
   
   ```bash
    >download 13
   test
   输入1遍历下载，输入2打包下载:1
   文件 FLUID.dat 已存在，是否要覆盖？
   输入1覆盖，2跳过，3全部覆盖，4全部跳过：4
   已跳过
   文件 FLUID.cas已跳过
   文件 profili2.3.zip已跳过
   ...
   ```

4. 获取下载链接
   
   ```bash
    >link 32
   https://1-180-24-9.pd1.cjjd19.com:30443/(A Long Link)
   ```
   
   获取下载链接后可以使用IDM下载

5. 分享文件：
   
   ```bash
    >share↵
   分享文件的编号：58↵
   ['Something.jpg']
   输入1添加文件，0发起分享，其他取消0↵
   提取码，不设留空：↵
   ok
   分享链接：
   https://www.123pan.com/s/(someting)提取码：(something)
   ```

6. 删除文件：
   
   ```bash
   > delete 1
   ```

7. 创建文件夹：
   
   ```bash
   > mkdir 新建文件夹
   ```

8. 上传文件：
   
   ```bash
    >upload
   请输入文件路径：C:\(some path)\config
   文件名: config
   检测到1个同名文件,输入1覆盖，2保留两者，0取消：2
   上传文件的fileId: (someThing)
   已上传：100.0%
   处理中
   上传成功
   ```
### 配置文件说明

在首次运行脚本时，会自动生成一个 `123pan.txt` 文件，用于保存用户的登录信息。请确保该文件与脚本在同一目录下。

# 注意事项

- 请确保在使用过程中网络连接正常。
- 由于使用了模拟安卓客户端协议，可能会有一定的风险，请谨慎使用。
- 本工具仅供学习和研究使用，请勿用于非法用途，任何滥用行为造成的后果由使用者承担
