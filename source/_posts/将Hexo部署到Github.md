---
title: 将Hexo部署到Github
tags: [Hexo,部署]
categories: Hexo
---

# 一、申请新的Repository  
- 确保仓库名和用户名一致
- 确保已同步ssh
<!-- more -->
# 二、配置本地Hexo  
- 编辑本地Hexo根目录下的 **_comfig.yml**文件
  ```   
  deploy:
    type: git
    repository: http://github.com/YourName/YourName.github.io.git
    branch: master
  ```

<font color=red >注意，type: repository: branch: 前面有两个空格，冒号后面都有一个空格。</font>  
# 三、部署到Github
- 切换到hexo根目录  
- 执行命令  
```hexo
hexo generate  
hexo deploy
```
最后提示：*INFO  Deploy done: git*，部署成功，访问https://YourName.github.io/即可。

### 报错解决

若执行hexo命令报错，一般为SSH未成功设置，重新配置SSH即可。  
若提示```ERROR Deployer not found: git```则表示未创建```hexo-deployer-git```依赖包。执行```npm install hexo-deployer-git --save```创建依赖包，重新部署即可。