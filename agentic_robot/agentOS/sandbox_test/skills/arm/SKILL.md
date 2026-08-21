---
name: arm
description: |
 控制机械臂进行预设的手臂动作，使用此技能时需要在下面的`allowed_targets`列表中选择一个词原样复制作为target，请根据任务理解并分析，从预设列表中选取动作，不要自己直接翻译，严禁编造不在列表中的词作为target。
 **适用场景：**
 -用户要求执行某个手臂动作，如"挥手“、”抓取“。
 -任务需要进行手臂动作才能完成，如“拿”。
 **使用规则：**
  - “抓取”、“夹”等拿取动作必须统一映射为clamp,若无特别指明，默认使用右手（即clamp_right)；“放”、“松开”等放下动作必须映射为realse_arm,且与对应clamp的手是同一只手。绝对禁止使用其他不在`allowed_targets`中的词。
  - 注意左右手协调，单个物品的拿和放（clamp和release_arm是同一只手），禁止同一个机器人同一只手连续抓取（clamp)两次而不释放。
  - 若指令中包含“抓取”，请调用clamp,禁止使用其他词作为target。
  - 用户指令中包含“拿”、“取”等拿取含义时，任务分解需包含以下四个节点：导航至物品(navigation)->抓取物品(clamp)->导航至返回点(navigation)->放下物品(release_arm)。特别地，如果一次需要拿超过一个物品，请先去拿篮子，将后续物品放入篮子送到返回点。
  - 请在以下`allowed_targets`中匹配适合的target，禁止输出不在以下列表中的target。
allowed_targets:
 - wave_above_head
 - wave_under_head
 - high_five
 - hug
 - shake_hand
 - clamp_right
 - clamp_left
 - release_arm_right
 - release_arm_left
 - make_heart
 - put_in_basket_right
 - put_in_basket_left
   
---
