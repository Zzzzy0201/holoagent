---
name: arm
description: |
 控制机械臂进行预设的手臂动作，使用此技能时需要在下面的`allowed_targets`列表中选择一个词原样复制作为target，请根据任务理解并分析，从预设列表中选取动作，不要自己直接翻译，严禁编造不在列表中的词作为target。
 **适用场景：**
 -用户要求执行某个手臂动作，如"挥手“、”抓取“。
 -任务需要进行手臂动作才能完成，如“拿”。
 **使用规则：**
  - 必须遵循的固定映射：1.“拿”、“抓取”、“取”、“夹”等拿取含义的动作必须映射成clamp,默认使用右手（即clamp_right）。 2.“放”、“松“等释放含义的动作必须映射成release_arm,方向要与夹取的手一致。
  - 注意左右手协调，单个物品的拿和放（clamp和release_arm是同一只手），禁止同一个机器人同一只手连续抓取（clamp)两次而不释放。
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
