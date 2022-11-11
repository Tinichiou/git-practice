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
1. 使用 ```git commit -m "add A"``` 存檔進度並新增description
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
