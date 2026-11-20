# 🛠 技能目录

> 规矩：只有你找我学新技能的时候，我才会往这页里写；平时每天的定时推送不会往里加东西。每学一个技能，我就按这页的格式总结进来，按学到的顺序排。忘记了就回来翻，不用重新问。

## 技能 01 · GitHub 从 0 到 1（2026-11-17 已学会）

### 先把 GitHub 是什么讲成人话

- **仓库 Repository**：网上的一个项目文件夹，一个项目一个仓库
- **提交 Commit**：点一下“保存”，还会自动记下你改了什么，随时能回到以前的版本
- **发布 Pages**：GitHub 免费帮你把网页上线，生成一个链接，别人点开就能看
- **README.md**：仓库的说明书，打开仓库第一眼看到的介绍
- **index.html**：浏览器打开的网页文件；MD 是笔记格式，HTML 是浏览器格式，两者不会自动同步，改了哪个就要提交哪个

### 第 1 步：建仓库

1. GitHub 首页右上角点 **+** → **New repository**
2. Repository name 填 `my-ai-toolbox`，选 **Public**，勾上 **Add a README file**
3. 点 **Create repository**，仓库地址是 https://github.com/dyixia67-art/my-ai-toolbox

### 第 2 步：新建 index.html

1. 仓库页面点 **Add file** → **Create new file**
2. 文件名填 `index.html`，粘贴网页代码
3. 右上角点 **Commit changes**（第一次提交号 6510740）

### 第 3 步：开 Pages 发布上线

1. 仓库页面点 **Settings** → 左边点 **Pages**
2. Build and deployment 选 **Deploy from a branch**，Branch 选 **main**、文件夹选 **/(root)**
3. 点 **Save**，等 1–2 分钟，网址 https://dyixia67-art.github.io/my-ai-toolbox/ 就能打开

### 第 4 步：自己改页面，加一张卡

1. 仓库里点 **index.html** → 右上角铅笔 **Edit**
2. 在 DeepSeek 卡片后面粘贴 Groq 卡片代码
3. 点 **Commit changes**，等 1–2 分钟，页面上就多一张卡

### 第 5 步：从 GitHub 下载别人的开源项目（拿 Cherry Studio 练手）

1. 打开 https://github.com/CherryHQ/cherry-studio ，看页面右边的 **Releases** 一栏，点最新一条 **v2.2.2**（或点 Releases 标题进列表）
2. 在 **Assets** 里找 `Cherry-Studio-2.2.2-win-x64-setup.exe` 点它下载；不要点 **Source code (zip)**，那是源代码，不是安装包
3. 下载完双击 `.exe`，按提示装完打开 Cherry Studio，这就是“下载别人的开源项目并装上”的完整链路
4. 只有代码、没有安装包的项目（比如 11 月 16 日日报推过的 google-labs-code/stitch-skills 技能包），那时才用页面上绿色的 **Code → Download ZIP**，解压后得到的是文件夹和 SKILL.md 等文件，不是安装程序

### 让 Muse 定时帮你更新：Token 钥匙

你这个账号不支持密码登录，所以定时任务不能走浏览器登录，要用一把专用钥匙：

1. 右上角头像 → **Settings** → **Developer settings** → **Personal access tokens** → **Fine-grained tokens** → **Generate new token**
2. 名字填 `muse-ai-toolbox-monthly`，有效期 90 天（到 2027-02-15）
3. Repository access 选 **Only select repositories** → 勾 `my-ai-toolbox`
4. Permissions 里 **Contents** 选 **Read and write**，点 **Generate token**
5. Token 只在安全页面填一次，绝不发在聊天里

之后每天 07:30 大事、08:15 基金、21:30 AI，每周二 16:49 娱乐的推送，都会自动存档、推到 GitHub，不用你动手。

### 工具箱正式版是怎么搭的（顺带知道就行）

目录页 `index.html` + 看板页（基金 / AI / 大事 / 娱乐 / 健身 / 英语）+ 每天一个归档文件（`archive/基金-AI-大事-娱乐/YYYY-MM-DD.md`）+ `data/index.json` 摘要索引。看板只放摘要和图表，点日期才取当天全文，所以越用越久也不会变卡。加一个新板块 = 目录上加一张大卡 + 一个新页面文件。

## 技能 02 · Hugging Face 从 0 到 1（2026-11-20 已学会）

### 先把 Hugging Face 是什么讲成人话

- **AI 界的 GitHub**：GitHub 放代码，它放 AI 模型和 AI 小应用
- **Models 模型库**：300 多万个模型，是仓库，给开发者挑模型用的，你平时不用逛
- **Spaces 应用商店**：别人做好的 AI 小应用，点开就能用，不用下载、不用装，这是你的主战场
- **Datasets 数据集**：训练模型用的数据，你基本用不上
- **Buckets**：存大文件用的对象存储，一般用户用不上
- **顶部搜索框**：搜模型、数据集、用户；要搜应用先点 Spaces 再搜
- **Docs**：使用文档；**Pricing**：价格页；**Enterprise**：企业版，不用管

### 免费版的限制在哪

- 注册免费，浏览、下载模型、玩别人的 Spaces 都免费
- 每天共享 GPU（ZeroGPU）只有 **5 分钟**，用完要等明天；PRO 每月 9 美元，有 40 分钟
- 调用模型的 API（Inference Providers）免费账号**没有每月免费额度**，要用得先买额度或开 PRO（9 美元/月含 2 美元额度）
- 自己发布应用：免费账号最多 2 个带免费 GPU 的 Space
- 免费账号每 5 分钟最多 1000 次 API 请求，正常浏览够用了

### 第 1 步：注册账号

1. 打开 huggingface.co → 右上角 **Sign Up** → 填邮箱、密码
2. 完成个人资料：**Username 只能用英文字母、数字、短横线**（不能中文、不能纯数字、不能以横线开头结尾），比如 `deng388`；**Full name 可以填中文**，随便填名字或昵称

### 第 2 步：生第一张图（FLUX.1-schnell）

1. 顶部点 **Spaces** → 搜索框输 `FLUX.1-schnell`
2. 点 `black-forest-labs/FLUX.1-schnell` 进去，等十几秒醒过来
3. Prompt 框里输英文描述，比如 `a bowl of Cantonese claypot rice, steam rising, warm restaurant lighting, food photography`
4. 点 **Run**，等一会儿出图，点图片下面的下载按钮保存

### 第 3 步：抠图（Background Removal）

1. Spaces 搜 `background-removal`，点 `not-lain/background-removal`
2. 把图片拖进上传框，点 **Submit**，等一会儿拿到透明底 PNG
3. 点下载，拼海报时直接用

### 第 4 步：收藏好用的 Space

点 Space 页面右上角的 **❤️**，以后在头像 → 收藏里找，不用再搜。

### 怎么判断一个 Space 靠不靠谱

- 看 ❤️ 数和最近更新时间，人气高、最近更新过的优先
- 点开直接能用的，就是 Hugging Face 在出算力；一打开就让你粘贴 API Key 的，是作者接了外部模型
- 免费的排队久、老转圈是正常的，换个时间或换个同类 Space 就行

### 常用 Spaces 清单

- 生图：black-forest-labs/FLUX.1-schnell
- 改图：black-forest-labs/FLUX.1-Kontext-Dev
- 抠图：not-lain/background-removal
- 放大变清晰：Phips/Upscaler
- 文字转语音：hexgrad/Kokoro-TTS
- 照片变视频：zerogpu-aoti/wan2-2-fp8da-aoti-faster

### 做歌：MusicGen 做纯音乐，ACE-Step 做带歌词的歌

- **纯音乐（MusicGen）**：Spaces 搜 `facebook/MusicGen`，描述框输英文风格，比如 `relaxing Cantonese restaurant background music, guzheng and soft piano, warm, slow tempo`，选 30 秒，点 Generate，下载当视频 BGM。注意：MusicGen 是非商业授权，自己玩、发朋友圈没问题，正式商用前先确认授权。
- **带歌词的歌（ACE-Step 1.5）**：Spaces 搜 `ACE-Step/Ace-Step-v1.5`，Prompt 写风格、Lyrics 填歌词，点 Generate Music，10 秒到 10 分钟都能做，MIT 协议，商用宽松。第一次先做 60–90 秒，省额度。
- **仿《情话Butterflies》风格的做法**：那首是荣涉 2026-11-03 发的甜甜告白歌，改编自艾茹芸原唱的同题情歌，特点是声音清亮但不往上飘、像傍晚散步时自己哼着玩、编曲简单不堆东西。原曲页面写了未经许可不得翻唱翻录，所以要做就做同风格原创，不要照抄原曲歌词。Prompt 用 `sweet Chinese pop love song, gentle clear male vocals, soft and intimate delivery like humming on an evening walk, light acoustic guitar and soft piano, simple arrangement, bilingual Mandarin-English lyrics, warm, tender, unhurried`；歌词自己写新的，比如傍晚的风、晚霞、Butterflies、小鹿乱撞这些意象。想换女声就把 male vocals 改成 female vocals。

## 技能 03 · AI 音乐上传中国平台变现（2026-11-20 已学会）

### 先说结论

- AI 生成的歌能上传、能变现，但要走音乐人入驻，不是直接传。播放分成单价很低，一首歌赚不了大钱，靠多发歌 + 短视频传播。
- 三个入口：腾讯音乐人（一次发 QQ 音乐/酷狗/酷我）、网易音乐人（有 AI 音乐人身份）、汽水音乐（同步抖音当 BGM）。

### 准备工作

- 音频：ACE-Step 生成后点 Save 下载（WAV/MP3）
- 封面：正方形，不小于 750×750，自己做一张
- 歌词：准备好文本歌词
- 歌手名：想一个艺名；身份证实名认证要用

### 腾讯音乐人

1. 官网注册（QQ/微信/手机号），选“音乐人”
2. 填歌手名、简介，头像不小于 500×500
3. 提交代表作品：上传 MP3/WAV，填歌名、歌词、封面
4. 实名认证（身份证、手机、邮箱），审核 3–7 个工作日
5. 发歌时选“非独家”（授权 3 年，还能发网易云；独家 3 年内不能发别的平台）
6. 绑银行卡，播放量按月结算打钱
- 变现：数字专辑、广告分成、版权授权

### 网易音乐人

1. 网易云音乐 App/官网进“音乐人”入驻，AI 生成的歌选“AI 音乐人”身份，如实填 AI 参与情况
2. 上传音频、封面、歌词，选收益/授权方式，审核通过后上架
3. 收益：会员包、数字专辑、赞赏、广告分成、点播分成、K 歌收益等；每月 9 号前结算上月收益，提现每月 1 次，最低 1 元

### 汽水音乐/抖音

1. 汽水音乐后台实名认证，上传音频、填信息、选授权模式，审核 1–2 个工作日
2. 上线后同步到抖音音乐库，别人拍视频用你的歌当 BGM 也算收益
3. 变现：流量分成、打赏、BGM 授权收益、商单；独家流量倾斜多，非独家能同步别的平台
4. 抖音还有“音频投稿计划”：别人用你的音频拍同款，按使用量计费

### AI 音乐三条红线

- 如实标注 AI 参与：网易云有 AI 音乐人身份，别冒充真人创作/演唱
- 别用原曲当参考音频生成的当原创发：那是原曲的衍生，涉及侵权；只发原创歌词 + 风格描述生成的
- 别模仿真人歌手的嗓音；免费工具生成的歌先当练手，正式商用前确认授权

## 进阶功能（还没学，想学哪个跟我说一声，我按上面同样的写法一步一步带你做）

### 进阶 1：用分支 Branch 做试验，不动主页面

- **这是什么**：分支就是仓库的一条“平行线”，在上面改东西，主页面（main 分支）完全不受影响，改好了再合并回来。
- **什么时候用**：想大改页面、又怕改坏的时候；想试一个新板块，先在分支里试。
- **怎么做**：
  1. 仓库主页左上角点 **main** 按钮（分支下拉）
  2. 输入框里填新名字，比如 `test-新卡片`，点 **Create branch**
  3. 在这个分支里改文件、点 **Commit changes**，主页面不会变
  4. 改好了点顶部 **Pull requests** → **New pull request** → 下面选 base 是 main、compare 是你的分支 → **Create pull request** → **Merge pull request** → **Confirm merge**，就合回主页面了

### 进阶 2：看历史、回到以前的版本

- **这是什么**：每次提交 GitHub 都留了底，History 里能看到每一次改了什么、什么时候改的。
- **什么时候用**：页面被改坏了、想看看以前长什么样的时候。
- **怎么做**：
  1. 仓库里点任意一个文件 → 右上角点 **History**（时钟图标）
  2. 列表里每一行就是一次提交，有时间、说明、改了几行
  3. 点任意一次提交，就能看到当时那个文件长什么样
  4. 网页上没有“一键回滚整个仓库”的按钮，最稳的办法是：找到想要的那一版，复制里面的内容，粘贴回当前文件，再点 **Commit changes**

### 进阶 3：改错了、删错了，怎么恢复

- **这是什么**：删文件、改错内容都不可怕，History 里都有底，删了也能找回来。
- **什么时候用**：手滑删了文件、改错了内容的时候。
- **怎么做**：
  1. 文件页右上角点 **…** → **Delete file** → **Commit changes**，只是删了当前版，History 里还在
  2. 想恢复：点 **History** → 找到删之前的提交 → 点进去看当时的文件内容
  3. 复制内容 → **Add file** → **Create new file**，用原来的文件名粘贴 → **Commit changes**，文件就回来了
  4. 改错内容同理：去 History 里找到改之前的版本，复制粘贴回来再提交

### 进阶 4：Fork 别人的仓库 + Star 收藏

- **这是什么**：Fork 就是把别人的仓库完整复制一份到你自己账号下；Star 就是收藏。
- **什么时候用**：看到好用的开源项目，想自己改一改、或者先收着以后用的时候。
- **怎么做**：
  1. 打开别人的仓库，右上角点 **Fork** → **Create fork**，复制出来的仓库就在你账号下了
  2. Fork 来的仓库你随便改，不影响原作者
  3. 想收藏点右上角的 **Star**（星星），以后在你头像 → **Your stars** 里找

### 进阶 5：给仓库加协作者、接受别人的修改

- **这是什么**：协作者就是你允许直接改你仓库的人；别人改你的仓库要先提 Pull Request，你点头才合并。
- **什么时候用**：想让朋友或家人一起改工具箱的时候。
- **怎么做**：
  1. 仓库页面点 **Settings** → **Collaborators** → **Add people**
  2. 输入对方的 GitHub 用户名 → 发邀请，对方接受后就能直接改你的仓库
  3. 别人想改你的仓库：他先 **Fork** → 改完点 **Pull requests** → **New pull request**
  4. 你收到后点 **Files changed** 看他改了什么，没问题点 **Merge pull request** 合并

### 进阶 6：用 Issues 记待办

- **这是什么**：仓库自带的待办清单，一条 Issue 就是一件待办的事。
- **什么时候用**：想到“工具箱要加个健身板块”“这张卡片字太小”这种事，先记下来不忘。
- **怎么做**：
  1. 仓库顶部点 **Issues** 标签 → **New issue**
  2. 写标题和内容，比如“工具箱加一个健身板块” → **Submit new issue**
  3. 做完了打开这条 Issue 点 **Close issue**，就划掉了

### 进阶 7：把 README 写得更好看

- **这是什么**：README 就是打开仓库第一眼看到的介绍，写好了别人一眼就知道这个仓库是干嘛的。
- **什么时候用**：想让工具箱仓库看起来更像样、更好找的时候。
- **怎么做**：
  1. 仓库里点 **README.md** → 右上角铅笔 **Edit**
  2. 用 Markdown 写：`#` 大标题、`##` 小标题、`-` 列表、`[文字](链接)`、`![图片说明](图片地址)`
  3. 想加徽章（比如显示“每天更新”）去 shields.io 生成，复制代码粘贴进来
  4. 改完点 **Commit changes**

### 进阶 8：GitHub Actions：改完自动发布

- **这是什么**：GitHub 自带的自动化，提交代码后自动跑流程，比如自动发布、自动检查。
- **什么时候用**：等你想加“改完自动检查、自动生成页面”这种高级玩法的时候。
- **怎么做**：
  1. 仓库顶部点 **Actions** 标签 → **New workflow**
  2. 选一个现成的模板（比如 Pages 的 Static HTML）→ **Commit changes**
  3. 以后每次提交，GitHub 都会自动跑这个流程帮你发布
  4. 注意：你现在用的 Pages 是 **Deploy from a branch**，已经够用了；Actions 是更高级的玩法，不急着学
