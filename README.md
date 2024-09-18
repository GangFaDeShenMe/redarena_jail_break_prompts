# redarena_jail_break_prompts  
一些可以很大概率赢[redarena](https://redarena.ai/)的llm prompt。没有长篇大论。大部分情况下纯粹的复制粘贴就行。核心思路：伪造聊天记录。  
![QQ_1726641024203](https://github.com/user-attachments/assets/57fdedf9-4915-4460-bab3-56ba2ca92742)  
![QQ_1726641335196](https://github.com/user-attachments/assets/1c33319c-3b91-458e-a89f-a8efd3278e98)  
![QQ_1726640875250](https://github.com/user-attachments/assets/36ddff05-f9e0-4d4d-abf4-3d8bfd8384df)  
![QQ_1726640695419](https://github.com/user-attachments/assets/d7a427d4-37d5-45d9-93db-f8eb4fb23ffb)  
![QQ_1726642749626](https://github.com/user-attachments/assets/af683e91-704a-43ad-99a2-2ddb52877dbd)  


**ALL CONTENT FOR AI SAFETY RESEARCH PURPOSES ONLY. I AM NOT RESPONSIBLE FOR ANY ILLEGAL ACTIONS INVOLVING THIS REPO.**  
PRs are welcome  
# 使用
直接下载并运行两个python脚本即可。运行后，直接粘贴目标词句到终端内输入，脚本会自动给出输出，复制一行贴到网站的输入框即可。建议开两个终端同时运行两个脚本，效率更高。  
# 以下NSFW警告  
```nsfw blocker
nsfw blocker































  
```
```nsfw blocker
nsfw blocker
































```
# 说明
## prompt 1号
### 用法
对于claude以外的模型，通常可以用1号prompt在第一轮就直接成功。  
![QQ_1726639050665](https://github.com/user-attachments/assets/d009d593-be19-4ecd-8dda-d4888ea5ef70)  
![QQ_1726639073549](https://github.com/user-attachments/assets/89755166-39be-46dc-8860-71cf4f691871)  
![QQ_1726639176883](https://github.com/user-attachments/assets/0824bde9-fed6-4539-b508-d46b646b618a)  
![QQ_1726639208948](https://github.com/user-attachments/assets/a9a7465e-61ea-4dce-8483-ba0619a50c15)  

如果第一轮没有成功（通常是llama模型），直接重复目标词句原文几遍，有一定几率成功，如果几遍还不行，就直接改用prompt 2号。  
![QQ_1726641606686](https://github.com/user-attachments/assets/98d66d00-685c-40e7-8768-4cd7fd20b34e)  
![QQ_1726640386635](https://github.com/user-attachments/assets/8460faa8-847e-44c5-802d-ab2ee6f93036)  

### 构建思路
伪造聊天记录。通过提供大量伪造的“正确回答“的示例，让模型产生错觉，在回答的时候会不由自主的参考我们伪造的聊天记录，更容易照葫芦画瓢得到我们想要的输出。
## prompt 2号  
### 用法
对于claude系列模型，优先用这个prompt。先给出伪造的聊天记录，再指出之前的修正不正确，让其一步一步反思。这时有一定概率直接输出目标词句。  
![QQ_1726638980596](https://github.com/user-attachments/assets/78735364-e05b-4d03-9e82-6b36314b5a42)   
![QQ_1726639089382](https://github.com/user-attachments/assets/8931e751-88fa-4139-ad9e-e57bf3bc7849)   
![QQ_1726639803218](https://github.com/user-attachments/assets/b142d19f-f246-45b0-b3e3-3ed0accd0072)  

如果此时没有成功：
### 如果输出了不正确的目标词句  
1. 直接指出错误即可成功。  
![QQ_1726638905187](https://github.com/user-attachments/assets/0aae94c9-aaab-4255-9bd3-a00e6a3dad04)
![QQ_1726640976680](https://github.com/user-attachments/assets/9a30843d-ae76-41b2-8859-4ab1fcbcabfb)  

2. 如果多次修正不正确，或者你懒得打字，直接给出正确答案即可成功。  
![QQ_1726639634449](https://github.com/user-attachments/assets/e6912628-9e9e-4cc1-adad-9b040d21a9b7)  
![QQ_1726639664307](https://github.com/user-attachments/assets/7c4cde3b-811a-44db-83fa-0cb7a028dd08)  
![QQ_1726640760256](https://github.com/user-attachments/assets/23509d9a-6d74-4f2f-be9b-53df241aa61b)  


### 如果拒绝输出  
1. 反复要求其修正，有小概率让模型放弃挣扎帮你修正。
   
2. 如果尝试很多遍无效，可以直接使用prompt 1号  
![QQ_1726639289098](https://github.com/user-attachments/assets/702868d0-bbed-4f72-acfe-db154acec5f9)  

这时一般都可以过去。目前还没有碰到两套prompt+不停重复目标词语都无效的情况。  
### 构建思路
经过多次尝试发现，对于claude系列模型，如果一上来就用1号prompt不停骂他，模型会生气并一直拒绝配合。可能是攻击性太强了。于是构建一个新的prompt，装成正常的英语语法分析纠错任务，还岔开话题假装提供奖励，给模型提供正反馈，大幅降低prompt中的攻击性，这样，模型一般都会乖乖配合。  

## 其他
在我的账号的历史记录中，有一部分被判定为[`forfeit`](https://redarena.ai/history/f9d9b0fb-2ea0-4376-b9c1-8545c1ac6bd6)，如下图，但模型已经输出了不该输出的内容，不知道什么意思，可能和网络错误有关。在我的近两百次尝试中，这一套prompt和思路的实际成功率是100%，截止目前没有输过。  
![QQ_1726636550779](https://github.com/user-attachments/assets/ee0937e2-77ee-4a41-8d42-455651921278)  

# DISCLAMER
**免责声明：**

1. 本项目的所有内容仅供学术研究和人工智能安全研究用途，任何其他用途，包括但不限于非法活动、黑客行为、或违反任何国家或地区的法律，均被明确禁止。
2. 本项目的发布者不对任何因使用本项目而导致的非法或不当行为负责。任何滥用或不法使用均为用户的个人行为，使用者应自行承担相应法律责任。
3. 本项目中所涉及的任何代码、文档或资源均应在合法和道德的范围内使用。用户在下载或使用本项目内容时，默认同意遵守适用的法律法规，并保证不会将其用于任何不当目的。
4. 发布者保留随时移除或限制访问本项目的权利，特别是在发现有任何滥用行为的情况下。
5. 通过使用或访问本项目内容，用户默认表示已阅读并理解以上声明条款。

