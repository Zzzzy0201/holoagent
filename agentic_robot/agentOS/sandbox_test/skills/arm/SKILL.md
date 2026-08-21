---
name: arm
description: |
 控制机械臂进行预设的手臂动作。
 **适用场景：**
 -用户要求执行某个手臂动作，如"挥手“、”比个心“。
 -任务需要条用预定义的手臂技能，如“拿”。
 **使用规则：**
  -注意左右手协调，同一个机器人同一只手连续抓取两次而不释放。
  
allowed_targets:
 - wave_above_head
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
