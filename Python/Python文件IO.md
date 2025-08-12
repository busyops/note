### 一、什么是编码
编码（Encoding）就是把信息（文字、符号等）转换成计算机可以理解和存储的数字形式的过程。计算机底层只能处理 二进制（0 和 1），而人类使用的语言是各种文字（中文、英文、日文、符号、表情…）。编码就是定义一个“映射关系”：

- 哪个字符 → 对应哪个数字（再存成二进制）。

- 例如在 ASCII 编码中：

```python
'A' → 65 → 01000001
'B' → 66 → 01000010
```

> 就像电话本，把“张三”映射到电话号码“138xxxx8888”，电脑用的是“字符表”把字符映射到数字。

### 二、 为什么需要编码

如果不编码，计算机无法知道你输入的“字母 A”在内存里该用什么样的 0/1 来表示。
 编码的作用主要有几个方面：
(1) **计算机存储和处理需要统一标准**

- 没有编码，计算机看到的只是二进制的 0 和 1，无法区分是文字还是图片。
- 有了编码，电脑可以知道：这个二进制数据代表的是什么字符。

(2) **不同语言的文字数量差异**

- 英文 26 个字母，用 1 个字节就够（ASCII）。
- 中文有几万个汉字，需要 2～4 个字节（GBK、UTF-8 等）。
- 编码方案决定了每个字符用几个字节、怎么排列。

(3) **跨平台、跨系统的兼容**

- 如果没有统一的编码规则，不同系统保存的文件可能互相打不开（产生乱码）。
- 例如 Windows 默认 `GBK`，Linux 默认 `UTF-8`，编码不一致时就会乱码。

(4) **支持全球化**

- 早期的 ASCII 只能表示英文。
- Unicode 系列（UTF-8、UTF-16、UTF-32）可以表示全世界所有文字和符号，包括 emoji。

**3. 举个乱码的例子**
假设一个中文“你”在 UTF-8 中是 `**0xE4 0xBD 0xA0**`（3 字节），
 但如果用 GBK 编码去解读这 3 个字节，就会变成完全不同的符号，导致乱码。



### 三、常见的编码方案

| 编码名称 | 字节长度 | 支持字符范围 / 语言 | 是否兼容 ASCII | 常用场景 | 备注 |
|----------|----------|---------------------|----------------|----------|------|
| **ASCII** | 1 字节（7 位有效） | 英文、数字、基础符号 | ![:加粗的对钩:](https://a.slack-edge.com/production-standard-emoji-assets/14.0/google-medium/2714-fe0f.png) | 早期计算机、协议头、基础文本 | 最基础的字符编码标准 |
| **ISO-8859-1 (Latin-1)** | 1 字节 | 西欧语言 | ![:加粗的对钩:](https://a.slack-edge.com/production-standard-emoji-assets/14.0/google-medium/2714-fe0f.png) | 老系统、旧网页 | Windows-1252 是其超集 |
| **Windows-1252** | 1 字节 | 西欧语言 | ![:加粗的对钩:](https://a.slack-edge.com/production-standard-emoji-assets/14.0/google-medium/2714-fe0f.png) | Windows 文本文件、旧网页 | 增加了额外符号 |
| **GB2312** | 1–2 字节 | 简体中文、英文 | ![:加粗的对钩:](https://a.slack-edge.com/production-standard-emoji-assets/14.0/google-medium/2714-fe0f.png) | 老版简体中文文档、早期网页 | 收录 6763 个汉字 |
| **GBK** | 1–2 字节 | 简/繁中文、英文 | ![:加粗的对钩:](https://a.slack-edge.com/production-standard-emoji-assets/14.0/google-medium/2714-fe0f.png) | Windows 简体中文系统 | 向下兼容 GB2312 |
| **GB18030** | 1–4 字节 | Unicode 全部字符 | ![:加粗的对钩:](https://a.slack-edge.com/production-standard-emoji-assets/14.0/google-medium/2714-fe0f.png) | 国家标准、现代中文系统 | 中国强制性标准 |
| **BIG5** | 1–2 字节 | 繁体中文（台港澳） | ![:加粗的对钩:](https://a.slack-edge.com/production-standard-emoji-assets/14.0/google-medium/2714-fe0f.png) | 台港澳系统、文档 | 与 GBK 不兼容 |
| **Shift_JIS** | 1–2 字节 | 日文（平假名、片假名、汉字） | ![:加粗的对钩:](https://a.slack-edge.com/production-standard-emoji-assets/14.0/google-medium/2714-fe0f.png) | 日本系统、文档 | 与 EUC-JP 不兼容 |
| **EUC-KR** | 1–2 字节 | 韩文、汉字 | ![:加粗的对钩:](https://a.slack-edge.com/production-standard-emoji-assets/14.0/google-medium/2714-fe0f.png) | 韩国系统、网页 | - |
| **UTF-8** | 1–4 字节 | Unicode 全部字符 | ![:加粗的对钩:](https://a.slack-edge.com/production-standard-emoji-assets/14.0/google-medium/2714-fe0f.png) | HTML、JSON、Linux 系统、网络传输 | 英文 1 字节，中文 3 字节 |
| **UTF-16** | 2 或 4 字节 | Unicode 全部字符 | ✘（部分） | Windows 内部编码、Java、C# | 有字节序（LE/BE）问题 |
| **UTF-32** | 4 字节 | Unicode 全部字符 | ✘ | 内部字符处理 | 占用空间大 |
| **Base64** | 4 字符表示 3 字节数据 | 任意二进制 → 文本 | ![:加粗的对钩:](https://a.slack-edge.com/production-standard-emoji-assets/14.0/google-medium/2714-fe0f.png) | 邮件附件、URL、加密数据传输 | 非字符集，属于编码方式 |
| **URL 编码** | 可变（%xx 形式） | 任意字节 → ASCII | ![:加粗的对钩:](https://a.slack-edge.com/production-standard-emoji-assets/14.0/google-medium/2714-fe0f.png) | HTTP URL、表单数据 | 非字符集 |


### 四、Ascii 码表
![ascii_table](..\images\ascii_table.png)
