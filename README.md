# HKUSTGZ Travel Reimbursement Skill

把差旅材料交给 Agent，让它帮你整理凭证、录入 PBMS、核对金额，并在你确认后提交预算审核。

这是从实际报销流程整理的社区 skill，适用于香港科技大学（广州）PBMS。支持中文、英文及其他语言界面：Agent 根据当前页面对照按钮和字段，不要求切换语言。它需要能读本地文件、操作浏览器的 Agent 环境；仓库本身不连接账号，也不自动发起报销。

## 开始使用

在 Codex 中发送：

```text
请使用 skill-installer，从 https://github.com/jayjunjieqiu/hkustgz-travel-reimbursement
安装 hkustgz-travel-reimbursement 文件夹中的 skill，作为用户级全局 skill。
如果已经安装，请先备份旧版，再更新。
```

安装后在下一轮对话中使用：

```text
使用 $hkustgz-travel-reimbursement 处理这个报销文件夹：<本次报销目录>。
先检查材料并生成扫描件标注版，让我确认后再拆分。
出差人是<姓名及人员ID>，身份是<学生/教职工/RA>。
费用归属人为<姓名及ID>，经费为<项目号>。
先完成录入、核对和保存，最终提交前给我看汇总。
```

第一次不必把所有信息都写齐。Agent 会检查文件，再一次性问清真正缺少的信息。密码和验证码直接在网页中填写。

## 文件怎么放

每次报销一个文件夹。先把原件全部放进去，包括出差审批、电子发票/receipt。纸质票据是可选的：没有就无需扫描；如有，则必须提供完整扫描件并纳入对应报销材料。Agent 整理后，目录大致如下：

```text
本次报销/
  原始材料/
  Intercity Transportation Expenses_城市间交通费/
  Accommodation Expenses_住宿费/
  Meal Expenses_餐费/
  Intracity Transportation Expenses_市内交通费/
  Registration Fees for Conferences_会议注册费/
  分类索引.md
  output/
  tmp/
```

只有实际有材料的类别才建目录。扫描件先保留原页标注，确认后再拆；餐费按日汇总。机票配登机牌，国内打车发票配行程单。无法确定的材料会说明原因，不会默默跳过。

## Agent 会做什么

1. 盘点每份材料和每页扫描件，识别日期、币种、金额及配套关系。
2. 生成标注版，集中列出日期冲突或分类疑问。
3. 按确认结果分类、拆分和压缩文件；必要时转换 OFD。
4. 选择学生或教职工通道，核对出差人、收款人、费用归属人与经费。
5. 上传后校正 OCR；逐笔复算，不把“识别成功”当作“金额正确”。
6. 保存草稿，核对全单与附件；只有明确收到提交指令才提交。
7. 记录 BR 编号、金额和下一审批节点，方便会话过期后恢复。

## 需要你决定的事

费用归属和经费、票据冲突、特殊分类、限额扣减等由你确认。超限应按当日或对应期间的总费用计算，不能把每张票据分别套用同一个日上限。财务允许的人民币记账或日期口径，要在备注保留原始发生日期、原币金额及折算依据。

提交成功表示进入审核，不表示审批或付款完成。本项目不是学校官方系统或财务政策，具体报销口径仍按学校和经办财务要求执行。

## 文件说明

- [SKILL.md](hkustgz-travel-reimbursement/SKILL.md)：Agent 入口和完整工作顺序。
- [材料处理](hkustgz-travel-reimbursement/references/materials.md)：扫描标注、文件分类和左右上传配套。
- [PBMS 操作](hkustgz-travel-reimbursement/references/pbms.md)：表单、草稿恢复、多语言术语和提交验证。
- [核对与异常](hkustgz-travel-reimbursement/references/review.md)：金额核算、限额、特殊口径及交接记录。

教职工通道已实操至提交预算审核；学生具体表单、签证费和后续付款流程尚未完整验证。界面变化时以当前页面为准。

## 隐私与贡献

仓库只包含通用指引，没有真实报销凭证、账号、人员ID、审批编号或银行信息。反馈问题时请使用虚构数据；截图中的姓名、账号、二维码、项目号和文件下载链接应先不可逆遮盖。

欢迎通过 Issue 或 Pull Request 补充界面变化、可复现的问题及经确认的操作方法。请说明中文/英文界面、所在步骤、预期与实际表现，并避免上传真实票据。

## 许可与来源

采用 [MIT License](LICENSE)。PBMS及其他产品名称属于各自所有者。

- PBMS：https://pbms.hkust-gz.edu.cn/
- Codex Skills 文档：https://developers.openai.com/codex/skills/
