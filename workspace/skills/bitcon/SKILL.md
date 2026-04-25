---
name: bitcon
description: Evidence-only altcoin review workflow based strictly on the Gate Learn article “山寨币的交易逻辑：基本面分析，技术分析，聪明钱地址”. Use when the user wants a standardized altcoin review, due diligence, or screening flow that must follow the article’s three-part structure: (1) 基本面分析, (2) 技术分析, (3) 聪明钱地址追踪. Use when conclusions must be backed by explicit evidence, with no assumptions, no narrative extrapolation, no missing-data guesswork, and clearly separated evidence gaps.
---

# Bitcon

Use this skill to review a token with a rigid, evidence-first workflow.

Core rule: every conclusion must be tied to observable evidence. If evidence is missing, say it is missing. Do not infer intent, future price, project quality, or hidden motives from incomplete data.

## Workflow

1. Confirm the review target.
2. Collect only verifiable facts.
3. Review in this fixed order:
   - 基本面分析
   - 技术分析
   - 聪明钱地址追踪
4. Cross-check the three sections.
5. Output only evidence-backed conclusions.
6. Mark all missing evidence explicitly.

## Step 1: Confirm the target

Do not start substantive review until these are identified:
- token name
- symbol
- chain
- contract address
- data timestamp or retrieval time
- data source names

If symbol search returns multiple candidates, stop and ask for the exact contract address or tell the user which candidate you are reviewing.

## Step 2: Evidence collection rules

Collect only facts that can be attributed to a visible source.

Allowed evidence types:
- official documentation or official site content
- chain explorer / onchain tool outputs
- trading or liquidity data from the tool used
- labeled address intelligence from the tool used
- article content explicitly cited by the user

Forbidden moves:
- do not fill gaps with prior knowledge unless you explicitly cite the source used in this run
- do not convert address movement into intent without supporting context
- do not treat absent data as positive or negative evidence
- do not make price predictions
- do not use persuasive language like “大概率”“要起飞”“庄家在吸筹”

## Step 3: Review order and scope

### A. 基本面分析

Review only the article’s categories:
- 团队与愿景
- 技术与产品落地
- 数据指标（链上/业务数据）
- 代币经济模型
- 社群和市场热度

For each category, output:
- 证据
- 结论
- 证据缺口

If you cannot verify a category, write “信息不足，无法下结论”.

### B. 技术分析

Review only directly visible chart or market facts:
- 趋势
- 支撑与压力
- 技术指标
- 成交量

Do not turn technical readings into certainty claims. Phrase results as current-state observations only.

Good:
- “24h 放量上涨，当前价格位于当日区间上沿附近。”
- “4h 已出现回撤，短线追高赔率下降。”

Bad:
- “马上要突破”
- “主力洗盘结束”
- “这里一定反转”

### C. 聪明钱地址追踪

Review only observable address facts:
- important labeled addresses
- concentration / top holder data
- transfers to exchanges or out of exchanges
- notable wallet accumulation or reduction if directly shown

Do not attribute motive unless the source itself provides the label or context.

Good:
- “某地址被工具标记为交易所地址，当前持仓占比 5.9%。”
- “观察到大额代币转入交易所地址。”

Bad:
- “这是准备砸盘”
- “巨鲸已经确认看多”

## Step 4: Three-way cross-check

After the three sections, explicitly answer:
- 基本面是否支持：是 / 否 / 信息不足
- 技术面是否支持：是 / 否 / 信息不足
- 聪明钱是否支持：是 / 否 / 信息不足
- 三者是否共振：是 / 否 / 信息不足

Then give the basis in 2-5 bullet points.

## Step 5: Output format

Always use the template in `references/review-template.md`.

Do not switch to essay format.
Do not skip the “明确未确认事项 / 证据缺口” parts.
Do not output a stronger conclusion than the evidence supports.

## Decision policy

Allowed final action suggestions only:
- 继续观察
- 可进入下一步深挖
- 暂不交易
- 信息不足，先补资料

Every action suggestion must include:
- direct evidence that triggered it
- missing evidence required for the next step

## Quality bar

Before sending the result, check:
- Is every conclusion tied to explicit evidence?
- Did I mark missing data instead of guessing?
- Did I avoid future-price prediction?
- Did I keep the article’s three-part structure intact?
- Did I use the required template?

## Resources

### references/
- `references/review-template.md`: fixed response template for evidence-only altcoin review
