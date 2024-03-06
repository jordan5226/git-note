# git-note
1. 指定工作目錄
```
command line> cd 工作目錄
```

2. 初始化git
```
git init
```

3. 把該資料夾中的全部檔案都加入版本控制
```
git add .
git add --all
```

4. 在github建立新的repository

5. 把本地內容連結到遠端github
```
git remote add origin https://github.com/username/MyRepository.git
git remote set-url origin  https://<your_token>@github.com/<USERNAME>/<REPO>.git
```

6. 切換到一個Branch (若有需要)
```
git checkout -b <branch name>
```

7. Commit Project修改
```
git commit -am 'First step.'
```

8. Push Commit
```
git push origin master
```
  
## Note: 如果有大型檔案需要上傳( > 50MB )
下載Git LFS [https://git-lfs.com/](https://git-lfs.com/)
  
然後Command line輸入  
```
git lfs install
```

再指定要管理的大型檔案  
```
git lfs track "*.dll"
git lfs track "*.dat"
....
```

別忘了加上  
```
git add .gitattributes
```
之後就可以照流程7, 8: `commit`, `push`  
  
## 出現error: This repository is over its data quota. Account responsible for LFS bandwidth should purchase more data packs to restore access.
`repo settings` -> `Archives section` -> 選取`Include Git LFS objects in archives`  
再次嘗試`push`  
  
## 出現error: failed to push some refs to xxxxxxxxx
```
git pull --rebase origin master
```
需要同步遠端到本地庫  
--rebase的作用是取消本地庫中剛剛提交的commit，並把他們接到更新後的版本庫中。  
  
## 刪除無用目錄
`git rm -r <one-of-the-directories>` // Deletes from filesystem  
or  
`git rm -r --cached <myFolder>` // Remove directory from Git but NOT local  
  
`git commit -m "Remove duplicated directory"`  
`git push origin <your-git-branch>` (typically 'master', but not always)
  
