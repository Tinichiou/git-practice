# git-practice
## 專案管理- git 協作練習
### 練習流程
#### 協作者A地端建立
1. 在地端創建一個資料夾gitA 扮演協作者A, 資料夾內新增hello.txt
1. hello.txt內容為 "hello git"
1. 打開terminal 使用 ```git --version```可以確認git是否成功安裝git和查看版本
1. terminal輸入```cd gitA``` 進入gitA資料夾為根目錄
1. 輸入```git init``` 初始化資料夾
1. 使用 ```git add .```追蹤資料夾內檔案
1. 使用 ```git commit -m "add hello file"``` 存檔進度並新增description
1. 使用 ```git status``` 可以查看狀態
1. 使用 ```git log```查看respository local端的版本紀錄
#### 協作者A 將地端repository 傳到 github 
1. 到github建立 new repository (public or private) 取名:git-practice
2. 選擇push an existing repository from the command line 複製指令貼上terminal
3. 回到github重整可看到gitA的資料已經push到github上
#### 協作者B開始協作
1. 在地端建立一個新資料夾gitB 扮演協作者B
2. 確認terminal位置在gitB資料夾根目錄內
3. 先```git init```
4. 去github repository:git-practice複製url
5. 回gitB terminal 打```git clone [url]```
6. 此時可以看到原本空的gitB資料夾裡面已經有一個叫git-practice的資料夾裡面包含hello.txt
#### 建立分支, 各自編輯
1. - 協作者A : ```git branch A```建立A分支, ```git switch A```切換到A分支
   - 協作者B : 要先cd切換到git-practice資料夾, 再```git branch B```建立B分支, ```git switch B```切換到B分支
2. - 協作者A : 編輯hello.txt, 加上 "I am A"
   - 協作者B : 編輯hello.txt, 加上 "I am B"
3. - 協作者A : ```git add .```, ```git commit -m "add A"```, ```git push -u origin A```, 可以看到github上已經有分支A和hello.txt(A ver)
   - 協作者B : ```git add . ```,```git commit -m "add B"```, ```git push -u origin B```, 可以看到github上已經有分支B和hello.txt(B ver)
#### 合併分支
1. - 回到協作者A的terminal, ```git switch main```回到主分支, ```git merge A```(此時會發現vs code上方工作區會出現第二行"I am A")
   - 不用add, commit 直接```git push``` (因為存檔點和分支A一樣, 所以不用再存一次), 此時github上main裡面的檔案已經有"I am A"了
2. - 回到協作者B的terminal, ```git switch main```回到主分支, ```git checkout```,```git pull```, 把最新版本的main內容拉下來
   - ```git merge B```會發生衝突, 選擇accept both
   - 因為是新的內容所以要 ```git add .```, ```git commit -m "merge A and B"```, ```git push```
3. 此時github上main分支有A+B, A分支只有I am A, B分支只有I am B
#### 各自pull最新版本到地端
1. 切換到各自的branch, ```git pull origin main```
2. 各自 add, commit, push
3. 此時github上 main, A, B都是A+B的最新版本 
