# SQL 谋杀之谜（中文版）

![侦探正在查看线索](174092-clue-illustration.png)

SQL 城发生了一起谋杀案！《SQL 谋杀之谜》既是一门可以自学的 SQL 入门课，也是一桩给老手消遣的推理游戏。

只想破案？直接打开 [在线版](https://occam-7.github.io/sql-mysteries/)。刚接触 SQL？建议从 [图文教程](https://occam-7.github.io/sql-mysteries/walkthrough.html) 开始——它不会把 SQL 讲全，但足够你独立破这桩案子。

## 关于这个中文版

这是 [Knight Lab 原作](https://github.com/NUKnightLab/sql-mysteries) 的非官方中文翻译（fork），原作由 Joon Park 与 Cathy He 制作，MIT / CC BY-SA 4.0 授权。

翻译范围只有叙事部分：案情报告、关键人物的访谈记录、结案判定后的提示语，以及页面与交互文案。

**刻意没译的东西**（译了游戏就跑不起来）：

- 人名、街道名、城市名、车牌片段、健身馆与活动名——它们同时出现在查询条件和结案校验的十六进制比对里，改动即导致答案失效。
- 表名、列名、字段取值（`murder`、`SQL City`、`Get Fit Now Gym`……）。
- 数据库中约六千条填充数据（Alice in Wonderland 摘录、lorem ipsum 之类），它们只是干扰项，不影响破案。
- `schema.png` 仍是英文 ERD；四份 PDF（prompt、reference、SQLiteStudio 安装指引）也仍是英文原文。

## 在自己的电脑上破案（离线玩法）

* **sql-murder-mystery.db**：SQLite 数据库文件，全部线索都在里面。
* **题面**：按水平二选一——[prompt_experienced.pdf](prompt_experienced.pdf)（进阶）或 [prompt_beginner.pdf](prompt_beginner.pdf)（入门）。两份都是英文。
* **[reference.pdf](reference.pdf)**：SQL 概念与命令速查。英文。
* **任意 SQLite 环境**：新手推荐 [SQLiteStudio](https://sqlitestudio.pl/)，图形界面看数据、写查询都方便。

## 上手

* **SQL 新手**：先读 reference，再看 prompt_beginner，然后照着 [sqlite_studio.pdf](sqlite_studio.pdf) 装上 SQLiteStudio 并载入 db 文件。卡住了就回头翻 reference。
* **SQL 老手**：看 prompt_experienced，下载 db 文件，用你惯用的环境开干。尽量全程待在 SQL 环境里，别开记事本记笔记。

## 验证答案

在你自己的 SQL 环境里执行：

```SQL
INSERT INTO solution VALUES (1, "把你找到的人名填在这里");

SELECT value FROM solution;
```

注意：如果用的是本仓库的中文版数据库，人名仍须写英文原名（`Jeremy Bowers`、`Miranda Priestly`），校验靠十六进制逐字比对。

## 作者与授权

* 原作：[Joon Park](https://twitter.com/JoonParkMusic)、[Cathy He](https://twitter.com/Cathy_MeiyingHe)
* 灵感来自 [邻城 Terminal City 的一桩命案](https://github.com/veltman/clmystery "command-line murder mystery")
* 代码以 [MIT 许可](LICENSE) 发布；原作文字与内容以 [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/) 发布，本中文翻译沿用同一许可。
* 页面中的 SQL 查询自定义组件改编自 [Select Star SQL](https://selectstarsql.com/) 作者 Zi Chong Kao 的公有领域代码。
* [侦探插图 by rambleron](https://www.vecteezy.com/vector-art/174092-clue-illustration)，依 Vecteezy 免费许可使用。
