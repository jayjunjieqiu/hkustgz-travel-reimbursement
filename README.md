![差旅报销 · 适用于 HKUST(GZ) 和 PBMS](docs/pbms-banner-dark.png)

<a href="LICENSE"><img src="docs/mit-badge.png" alt="MIT License" width="86" height="21"></a>

用 Codex 整理香港科技大学（广州）的差旅凭证、录入 PBMS、核对申报金额，并经授权提交预算审核。

[PDF 操作指南](docs/HKUSTGZ_PBMS自动报销操作指南.pdf) · [技能说明](hkustgz-travel-reimbursement/SKILL.md)

## 开始使用

**安装一次。** 在 Codex 中发送：

```text
请安装这个仓库里的 hkustgz-travel-reimbursement 技能。
https://github.com/jayjunjieqiu/hkustgz-travel-reimbursement
```

**每次报销。** 将审批单、发票或收据、行程单和已有付款凭证放在同一个文件夹。如有纸质票据，按日期和费用类型整理，保留完整票面并扫描成 PDF。把文件夹拖进对话，或提供完整路径。

```text
请用 $hkustgz-travel-reimbursement 处理这次差旅报销。
材料文件夹：<路径>
出差人及身份：<姓名，学生 / 教职工 / RA>
支出负责人：<姓名>
经费：<项目号及用途>
```

在网页上登录 [PBMS](https://pbms.hkust-gz.edu.cn/)，核对材料标注和待确认事项。确认申报金额和处理口径后，授权提交。

## 报销流程

| 阶段 | 结果 |
| --- | --- |
| 整理材料 | 标注扫描件，配对票据与付款凭证，列出缺件和金额差异。 |
| 录入草稿 | 选择出差人、收款人及经费，逐笔校正 OCR 日期、币种和金额。 |
| 保存正式单据 | 复核限额和附件，生成 BR。境外餐费按正式明细在专栏逐笔登记。 |
| 提交预算审核 | 经授权提交，核对工作流的提交时间与下一审批节点。 |

教职工和 RA 使用 `Travel Reimburse`，学生使用 `Student Travel`。教职工流程已验证至提交预算审核。学生表单、签证费和后续付款流程仍以当前 PBMS 与学校财务要求为准。

## 参考资料

- [材料处理](hkustgz-travel-reimbursement/references/materials.md) — 扫描、分类和凭证配套
- [PBMS 操作](hkustgz-travel-reimbursement/references/pbms.md) — 表单、草稿恢复和附件登记
- [金额核对](hkustgz-travel-reimbursement/references/review.md) — 限额、日期和交接

欢迎通过 Issue 或 Pull Request 反馈界面变化。请使用虚构数据说明复现步骤。采用 [MIT 许可](LICENSE)。
