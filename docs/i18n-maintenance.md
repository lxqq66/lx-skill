# README 多语言维护

## 内容源

`README.md`（简体中文）是说明文档的唯一内容源。英文、西班牙语、德语、日语和韩语 README 是面向读者的本地化版本，不反向决定 skill 的逻辑。

## 更新流程

1. 修改中文 `README.md`。
2. 将有意义的内容变化同步到 `README.en.md`、`README.es.md`、`README.de.md`、`README.ja.md` 和 `README.ko.md`。
3. 保留命令、skill ID、文件路径和链接原样；翻译解释性文字。
4. 运行：

   ```bash
   python3 scripts/check_i18n_sync.py --update-markers
   python3 scripts/check_i18n_sync.py
   ```

5. 提交六份 README、源内容变更和新指纹。

## 检查机制

检查脚本计算中文 README 的 SHA-256 内容指纹，并要求六份 README 顶部记录相同指纹。它还检查：

- 六种语言的导航链接是否完整；
- 四个已发布 skill ID 是否都出现；
- 统一的 GitHub 克隆地址是否存在。

当中文 README 被修改而翻译文件没有更新指纹时，GitHub Action 会失败。指纹只能说明维护者确认了同步，不能证明翻译质量，因此新增或大幅改写内容仍需人工抽查。

## 翻译原则

- 保留 `lx-*` skill 名称、代码、命令和目录不翻译。
- 使用当地读者自然的表达，不逐字翻译中文句式。
- 教育、心理、安全、法律和职场内容不夸大结论。
- 不把中国“体制内”直接等同于所有国家的公共部门；用 hierarchical organizations、public institutions 等解释性表达。
- skill 本体保持一套逻辑，根据用户语言生成回答，避免复制六套 `SKILL.md` 后发生漂移。
