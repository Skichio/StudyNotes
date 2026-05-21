# git使用

## 一、配置用户名与邮箱

```bash
git config --global user.name "Skichio"
git config --global user.email 123@email.com
git config --global credential.helper store
# --global 全局配置，所有仓库生效
# --system 系统配置，所有用户生效
```

## 二、新建仓库

```bash
git init
```

## 三、添加与提交文件

查看状态

```bash
git status
```

添加文件到暂存区

```bash
git add <filename|dirname>
git rm --cached <filename|dirname> # 从暂存区删除
```

提交文件

```bash
git commit -m "first commit"
git commit -am"commit" # 相当于add+commit
```

查看提交日志

```bash
git log
```

## 四、版本回退

```bash
git reset
# --soft   保存工作区与暂存区
# --hard   丢弃工作区与暂存区
# --mixed  保存工作区丢弃暂存区
```

## 五、查看差异

```bash
git diff # 查看工作区与暂存区的差异
git diff HEAD # 查看工作区与最新提交的差异
git diff --cached # 查看暂存区与最新提交的差异
git diff v1_id v2_id <filename> # 比较两个提交版本中对应文件的差异
```

## 六、删除文件

```bash
git rm <file>
git rm -r <dir>
git rm --cached <file>
```

## 七、配置ssh密钥

```bash
ssh-keygen -t rsa -b 4096

# config
"""
# github
Host github.com
HostName github.com
PreferredAuthentications publickey
IdentityFile ~/.ssh/test
"""
```

## 八、关联仓库

```bash
git remote add origin <SSH>
git push -u origin main:main
```

## 九、分支

```bash
git branch <branchname> # 创建新分支
git switch/checkout <branchname> # 切换分支
git merge dev # 将dev分支合并到当前分支
git branch -d dev # 删除分支（已被合并的分支）
git branch -D dev # 强制删除分支
```

