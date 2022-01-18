# 20220117

##### 講義來源 
https://hackmd.io/features-tw?view

##### 學長github
https://github.com/arthurc0102

##### gitbook.tw (補充：使用Git flow)
https://gitbook.tw

---

## fork顯示
紅色icon：刪除
黃色icon：修改
綠色icon：新增


![圖片替代名稱](https://i.imgur.com/joHDYMF.png)

Discard changes：直接取消在Unstaged所做的動作，會直接回到上個節點的紀錄

![name](https://i.imgur.com/gs6LKxh.png)


revert 將前一個步驟相反(最建議用這個，若revert和reset相比的狀況下)

reset：取消變更
- mixed:直接到Unstaged
- soft:直接到Staged
- Hard:mixed+discard changes(不建議使用)

---

## 上傳圖片
只要按下這個按鈕 <i class="fa fa-camera"></i>
或是 **拖放** 圖片到編輯器，甚至 **貼上** 圖片也可以喔！
這會自動上傳圖片至 **[imgur](http://imgur.com)**，啥都不必煩惱了 :tada:
![Image](https://i.imgur.com/9cgQVqD.png)

---

## 註解
簡報模式用「---」，來分頁(要跟- - -上下隔著空行才能成功)

---
## git 指令
```uml=
git status                    # 目前檔案的狀態
git add 文件檔                 # 將文件檔放進Staged區域
git commit -m "Create a.txt"  # 建立節點
git log                       # 目前建立節點的狀態
git log --oneline             # 目前建立節點的狀態(簡潔版本)
touch b.txt                   # 建立b.txt檔案
git reset --soft b4963d1      # 將b.txt檔從commit退回Staged區域(要選擇前一個節點碼)
git restore --staged b.txt    # 將b.txt檔從Staged退回Unstaged區域
git reset --mixed b4963d1     # 將b.txt檔從commit退回Unstaged區域(要選擇前一個節點碼)
git push -u origin master     # 首次將檔案推上github的設定
git push                      # 首次推完之後就輸入git push即可
git pull                      # 從雲端載下來(原本有資料夾)
git clone https://github.com/LaruaChen/git_playground.git # 從雲端載下來(Localhost本來是沒有任何資料的情況下)
```

---

.gitinore 此檔內容會放一些檔案不讓上傳到github上
.gitkeep  此檔會保留住空的資料夾，將空資料夾顯示在fork上(.gitkeep要放進資料夾中)

---
## github架設靜態網頁
架設屬於你的靜態網頁，建立index.html並上傳到github上
在Setting -> Pages -> Branch選master分支 -> 選 /(root) -> 選 save -> 點選藍色框框裡的連結 -> 等待一段時間


---

## 合併分支
將其他分支merge到master分支中，先選擇No Fast-Forward

---

## 解決衝突
#### fork解決

#### 記事本

---

### 合併分支的方式：

No Fast-Forward 強制長一個新的點，讓master分支保持一條線

Default 不強制長一個新的點，讓master分支到那個子分支的節點上，master就不會保持一條線。若另一個子分支需要再合併，最後還是會新增一個新的節點到分支上。 

---

### 在github上進行網頁合併
寫在20200116的研習中

---

### 在fork上查詢
Blame/Timeline 查看檔案文件記錄
History 查看檔案合併紀錄

---

### 設定SSH
前提：要將email設定為公開
指令：ssh-keygen.exe(在有git repository的地方按右鍵選git-bush)

SSH協定：跟HTTPS協定相比較有安全性，會新增id_rsa(公鑰)和id_rsa.pub(私鑰)，不用跟HTTPS一樣重複產生token

HTTPS協定上傳到github，需要用帳密登入，但現在改為需要用一個有期限的token(較適用於一次性使用)

---

### 遠端和本地端的上下傳
* push：從localhost上傳到github(差異化更新)
* Force push：強制性將localhost的紀錄，覆蓋雲端的紀錄
* 不建議在master分支用reset + Force push的原因：因為其他合作同學的版本紀錄都需要將紀錄整理成的跟你相同，才能繼續往下更新；除非是只有你自己一個人使用就不影響
* pull：從github下載到localhost
* fetch：查看github上的目前紀錄，但不會下載到localhost
* pull = fetch + checkout
* checkout：將節點移置到最新的版本

---

### markdown 指令
- ~~Text~~：刪除線
- **Hello**：粗體
- hello*：斜體

> hello world：類似引用

- Hello `World` ： world被特別標註

```
Hello world：被特別標註
```

```python=
def hello():
    print("hello world")
```

1. hello
2. hello
3. 只認第一個格式

- 無數字列點
- hello

* 用*也可列點
* hello


* 表格

| Colunm 1 | Col 2    | Col 3    | 4sssssssssssssssss       |
| -------- | -------: | :-----   | :------:                 |
| Text     | 靠右對齊  | 靠左對齊   | 置中對齊                  |

* 超連結
<https://google.com>
[Google](https://google.com)

