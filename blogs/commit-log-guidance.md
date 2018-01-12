# commit log guidance 
commit 信息的熟悉规范

## git commit message 的格式
```
<type>(<scope>): <subject>

<body>

<footer>
```
### Header 包含三个部分：type(必需)，scope(非必需)，subject(必需)
- type: commit类型  
feat: 新功能
fix: 修复bug  
docs: 文档  
style: 格式(不影响代码运行的变动)  
refactor: 重构  
test: 测试  
chore: 构建过程或辅助工具的变动  
- scope: 用于说明commit影响范围
- subject: 目的的简单描述
### body 包含此次commit的详细描述
### footer 
- 不兼容变动
BREAKING CHANGE
- 关闭Issue
Close #233 or Closes #2333, #565