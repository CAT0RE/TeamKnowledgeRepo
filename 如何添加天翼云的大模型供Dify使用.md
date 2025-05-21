
在[天翼云的官网](https://www.ctyun.cn/act/xirang/deepseek),我们提供了2500万Tokens的免费试用，每个模型均可免费试用2500万Token，或者两周，两个条件达到其一则试用终止。下文将介绍如何调用天翼云的大模型API供Dify使用。


![[Pasted image 20250521140616.png]]

Step 1. 创建服务组
![[Pasted image 20250521140855.png]]


Step 2. 选择需要的模型服务
![[Pasted image 20250521140919.png]]

Step 3.  创建服务组后，从服务组上面获取APP KEY
![[Pasted image 20250521140942.png]]

Step 4. 在模型广场找到对应配置的模型id
![[Pasted image 20250521140957.png]]

![1747798969044](file:////Users/xiaowangzi/Library/Group%20Containers/UBF8T346G9.Office/TemporaryItems/msohtmlclip/clip_image010.jpg)

dify配置系统模型

Step 5. 通过直接配置OpenAI-API-compatible支持，配置方式如下：
![[Pasted image 20250521141009.png]]

Step 6. 在OpenAI-API-compatible的配置界面设置有关的参数
![[Pasted image 20250521141015.png]]

Step 7. 在模型的调用设置中，选择添加的语言模型。此处显示的是模型ID，实际上在`模型名称`这一项填写官网中显示的`模型名称`也可以，例如`DeepSeek-R1-昇腾版`。

![[Pasted image 20250521141021.png]]