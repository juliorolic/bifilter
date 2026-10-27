# bifilter

**检查输入与输出两侧的过滤规则是否对称。**

`bifilter` —— 比对输入侧与输出侧的规则覆盖，标出只在一侧生效的部分

- 零依赖，Python 3.10+ 标准库即可运行
- 单文件，`bifilter.py` 拷走就能用
- 不联网、不写文件

<!-- ipos:install -->
## 安装

零依赖，Python 3.10+ 即可：

```bash
pip install juliorolic-bifilter
```

装完直接用命令名调用：

```bash
bifilter --help
```

也可以不用安装，直接把 `bifilter.py` 拷走用——它只依赖标准库。

## 为什么需要它

只过滤输入是最常见的缺口，工具专门做两侧对照

它遵守下面几条自己定的规矩：

1. **只报告能定位到具体位置的结论**，不做语义猜测。
2. **规则表公开**，每条命中都能对应到 输入输出双向过滤 领域的一条明示规则。
3. **输入为空或格式不对时明确报错**，不静默返回空结果。

## 用法

```bash
python bifilter.py --file input.txt
python bifilter.py --text "示例内容"
python bifilter.py --file input.txt --json
```

加 `--json` 可以拿到机器可读的结果，便于接到流水线里。

## 已知局限

- 覆盖率的分母取自你登记的清单，清单不全就会偏高。
- 只做映射，不追责。

## 跑测试

```bash
python test_bifilter.py
```

测试用独立的断言与临时数据，不污染工作目录。

## 来源与参考

- Python 标准库文档：<https://docs.python.org/3/>
- GitHub 仓库：<https://github.com/juliorolic/bifilter>

---

## 关于作者

juliorolic 做输入输出双向过滤相关的问题。这个工具先替你回答一个具体问题，再谈别的。

- 个人主页：<https://juliorolic.github.io>
- 仓库：<https://github.com/juliorolic/bifilter>

## 许可

MIT，见 [LICENSE](LICENSE)。
