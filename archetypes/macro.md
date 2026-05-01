---
# 宏包标题，显示在网站页面顶部和列表卡片中
title: '{{ replace .File.ContentBaseName "-" " " | title }}'

# 发布日期，自动生成，无需手动修改
date: {{ .Date }}

# 草稿状态，true=不发布，false=正式发布
draft: false

# 职业，从以下列表中选择一项填入：
# warrior(战士) / paladin(圣骑士) / hunter(猎人) / rogue(潜行者)
# priest(牧师) / shaman(萨满) / mage(法师) / warlock(术士)
# monk(武僧) / druid(德鲁伊) / demonhunter(恶魔猎手)
# deathknight(死亡骑士) / evoker(唤魔师)
classes:
  - 

# 专精，常用值：
# arms(武器) / fury(狂怒) / protection(防护)
# holy(神圣) / protection(防护) / retribution(惩戒)
# beastmastery(兽王) / marksmanship(射击) / survival(生存)
# assassination(刺杀) / outlaw(狂徒) / subtlety(敏锐)
# discipline(戒律) / holy(神圣) / shadow(暗影)
# elemental(元素) / enhancement(增强) / restoration(恢复)
# arcane(奥术) / fire(火焰) / frost(冰霜)
# affliction(痛苦) / demonology(恶魔学识) / destruction(毁灭)
# brewmaster(酒仙) / mistweaver(织雾) / windwalker(踏风)
# balance(平衡) / feral(野性) / guardian(守护) / restoration(恢复)
# havoc(浩劫) / vengeance(复仇)
# blood(鲜血) / frost(冰霜) / unholy(邪恶)
# devastation(湮灭) / preservation(恩护) / augmentation(增辉)
specs:
  - 

# 版本号，如："11.0" / "10.2.7" / "11.1"
versions:
  - ""

# 类型：free(免费) / premium(付费)
# free 类型会在页面显示直接下载按钮
# premium 类型会在页面显示型号选择和购买按钮
type: free

# ===== 付费宏型号配置（仅 type: premium 时生效）=====
# models 是一个数组，每个型号包含：
#   name    - 型号名称（如：基础版 / 进阶版 / 大师版）
#   price   - 价格（如：¥19 / ¥39 / $9.99）
#   features- 功能列表（每行一项）
#   buy_cn  - 国内购买链接（爱发电 / 淘宝 / 闲鱼）
#   buy_global- 海外购买链接（Gumroad / PayPal）
models:
  - name: "基础版"
    price: "¥19"
    features:
      - "核心循环宏"
      - "常用技能整合"
    buy_cn: ""
    buy_global: ""

# 预览图路径，图片需放在 static/images/ 目录下
# 填写格式：/images/图片文件名.jpg
preview_img: ""

# 演示视频链接，支持 B站 / YouTube
demo_video: ""

# 下载文件路径（仅 free 类型生效）
# 文件需放在 static/downloads/ 目录下
# 填写格式：/downloads/文件名.zip
download_file: ""
---

## 功能介绍

## 适用场景

## 使用说明

## 更新日志
