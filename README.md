開始使用 GitHub， 註冊與建立repo
介紹如何申請Github帳號，以及如何利用它與本地端的電腦連接。
01. 建立Github帳號、方案介紹與變更主要Email 
以下正式開始文章
________________________________________
Git 和 GitHub 是兩個有關聯但不同的東西，Git 是一種版本管理的工具, 如同svn, 微軟的team foundation server。
GitHub 則是一個網站提供免費的空間讓你擺放你程式的Source Code (原始碼)
不過免費是有條件的，只要用免費的方案，Source code 就會是Open的, 大家都可以下載與觀看，如果不要Open, 那就使用付費方案吧。
 ![image](https://github.com/nasonyehfm/test/blob/main/%E5%9C%96%E7%89%871.jpg)
本篇文章目的 :  註冊github 帳戶, 並建立第一個遠端倉庫(repo)
 每個版本管理都有自己的強項, git 來說的話大概就是branch 與其沿伸功能,不過本文並不會提到, 之後的文章才會對於這段描述。
本文指描述到建立一個遠端的下載連結
===============================================
1. 註冊GitHub
連上GitHub網站，然後點擊右上角的Sign In直接登入。
 
 進入Join GitHub畫面之後填寫一些Create your personal account的基本資料
Username : 使用者名稱
Email Address: 電子郵件信箱
password : 密碼
填好資料的輸入框右邊會出現綠色的勾勾，然後按下方的「Create an account」鈕。
 
 
 接著進入下一頁，Step2的內容就是選擇免費及付費方案。
 
因為在GitHub裡面放的所有東西都是open的，如果在GitHub裡面放的東西不公開的話，比如說商業用途的code...等隱私性較高的東西，就要選擇付費方案每月$7塊美金。
那我們這邊選擇的是Unlimited pubilc repositores for free(免費方案),到這裡都是給個人用戶的項目選擇，接下來的項目勾選則是給組織用戶勾選的，所以這邊我們就都不管，直接按「Continue」進入Step3。
 
Step3的內容就是一些基本的問卷填寫，隨便勾一勾後按「Submit」。
 
Submit完成後請至剛剛申請註冊的電子郵件信箱收GitHub發的驗證信件，並完成帳號驗證程序。
 
完成驗證後就直連進GitHub登入的畫面，這時我們可以直接點進「Your profile」。
 
2. 建立Repo  (Repositories)
然後點進Repositories，點擊右邊的「New」來建立一個新的程式庫。
 
 進入Create a new repository畫面後需輸入一些建立程式庫的資料，
	Owner : 這裡已設定好是使用者名稱
	Repository name : 程式庫名稱
	Description : 程式庫的相關描述
	Public | Private : 該程式庫適用的公開或隱私管理方案選項，如果是選擇Private的話，下方就會出現付費帳戶資料填寫項目，那我們這邊選擇的依然是Public(公開免費)，然後下方的Initialize this repository with a README項目要勾選，README就是這個程式庫工具內有很多的功能及使用方式的說明記錄，通常這個功能使用說明記錄都會被寫入一個README.md檔內。
  
	Add .gitgnore : GitHub的檔案管理功能。
這裡如果有選擇建立的話，會產生出名為.gitgnore的隱藏檔，被寫在該檔案內的檔名不會加入版本管理，通常是寫入一些程式自動新增的管理檔案，或是包含帳號密碼的設定檔。
(不要把帳號密碼上傳應該是常識，尤其是公開在網路上)
 
	Add a license : 檔案授權使用權限設定。
這裡設定None的話，代表檔案不授權公開使用，別人來使用你的檔案必須要自行負責。
如果設定的是MIT License的話，代表檔案可供別人使用於任何用途，甚至修改。
其它的License選項都有著不同授權的概念，詳細說明可參照旁邊的「i」
連進其各種License說明網頁。  
 
 
 
 
3. 加入要版本管理的檔案
用Git 版本管理簡單來講, 就是將"最初的"檔案複製到例外一個資料夾,之後的所有的變動以, Patch或log 檔的形式記錄下來，我們使用的是GitHub提供給我們的網路資料夾, 所以理所當然的需要"上傳"我們要管理的檔案到GitHub網站，雖然GitHub也有提供圖形化介面的工具，但之前用過覺得不是很理想，而且之後架站也可能會使用Linux，所已還是提早習慣文字介面的好。
 
Windows的話要先安裝git bash，可以參考這一篇 
Git 版本管理 (G1.0) Git 介紹與安裝 - Windows
 
所以我們就直接在bash底下操作了
Windows: git bash

有幾種方式, 比較正規的方式是用 git remote 的方式，但我覺得要說的有點多, 所以本文先介紹最簡單的方式，要下載遠端的備份必須要用git clone指令，而且clone 下來後 remote 自動就設好了。
(關於remote的簡易解釋在文末有介紹)
 
首先開啟Git Bash (Windows系統) 或 Shell (Linux系統)
a. cd 至你想放repo的路徑
這裡就直接示範放在Desktop(桌面)
$ cd Desktop
 
 
 
b. 自動方式做clone
因為git的套件已經安裝好了，所以這個步驟可以直接以自動的方式做clone的動作，點擊「clone or download」將裡面的網址(https://github.com/DemoProgressBarTw/RubyOnRailsTest.git)複製到bash，在網址前面加上 $ git clone，你就會發現資料都download下來了。
  
 
 
download下來的資料夾在桌面上都會看得到，當然資料夾裡面的檔案內容也都可以看得到。
 
 
可能有人發現RubyOnRailsTest的資料夾裡怎麼會少一個檔案，
 
 
 
因為 ".gitgnore"是隱藏檔，雖然在外部資料夾裡看不到，但實際上這個檔是存在的。
我們也可以在bash裡以下的指令來查詢該檔案，在Desktop底下輸入查詢 
$ ls  
接著輸入查詢 
$ cd RubyOnRailsTest/
再於RubyOnRailsTest資料夾底下輸入查詢 
$ ls
然後輸入所有檔案查詢 
$ ls -al
之後就可以看到.gitgnore這個檔案是存在的，同時也可以看到.git的版本控管檔也在這裡。
 
 
c. 直接在該資料夾裡面新增檔案
首先打開RubyOnRailsTest資料夾，然後再打開文字編輯檔，新增文件，隨便輸入一段文字，例如:測試...等兩個字，然後儲存在這個資料夾裡，檔案叫Test。
 
 
 
 
 
回到bash，在RubyOnRailsTest資料夾底下輸入查詢指令 
$ ls
可以發現該資料夾內多了一個剛剛新增的文字檔 Test.rtf。
 
 
e. 在.git版本管理底下查詢資料夾狀態
在.git版本管理底下RubyOnRailsTest資料夾裡面輸入 $ git status，以查詢這個資料夾的變化(顯示查詢結果為紅色字體)
 
 
f. 避免.Ds_Store文檔重覆生成
如果是在Mac底下操作的話，每次查詢都會一直生產.Ds_Store，.Ds_Store是 Apple 為 OS X 作業系統所創造的隱藏文件，目的在於存貯目錄的自定義屬性，很多用戶會選擇去刪除，但這個文檔是會一直『復活』的。
參照以下建議做法可避免該文檔有一直復活的情況。
將.Ds_Store這個檔名複製起來，然後輸入 $ vim .gitignore，進到.gitignore裡面，然後按「i」，將檔名加進來。
 
 
 
輸入 :wq!，將其儲存起來即可。
之後在做一次 $ git status查詢，查詢狀態會告訴你，.gitignore已被修改過了(紅色字體)。
 
 
 
 
g. 記錄已修改過的.gitignore
輸入 $ git add .gitignore 加入這個修改記錄，再輸入 $ git status 查詢狀態顯示這個修改已被記錄(綠色字體)，並且等待進入版本管理的commit。
 
 
h. 版本管理記錄的commit
將剛剛修改.Ds_Store這個記錄commit至版本管理中，輸入$ git commit -m "add .Ds_Store into .gitignore"
 
 
 
commit完後就可以看到file changed跟file insertion的訊息了。
 
 
i. log查詢
輸入 $ git log 可查詢所有版本管理執行過的記錄，包含修改人、修改時間、修改序號、修改內容...等資訊，
 
 
 
j. 本地端與遠端資料夾版本管理同步
下載至本地端的版本管理資料夾與遠端版本管理資料夾是不同步的，好比本地端是一個倉庫，遠端是另一個倉庫，所以我們要進行兩邊倉庫同步的動作，這樣版本管理的內容才會是一致的。
 
從本地端傳送(push)至遠端
輸入 $ git push，然後它會要求你輸入用戶名稱及密碼，之後就會開始將本地端的資料傳送至遠端。
 
 
傳送完成後，回到遠端去看.gitgnore記錄(請先重新整理網頁)已顯示修改過。
 
 
 
k. commit新增的檔案並同步至遠端
首先要先加入剛剛新增的文字檔，輸入 $ git add Test.rtf。
 
 
如果一次要commit很多個檔案的話，可以直接輸入 $ git add --all。
但要注意的是，下all的指令容易把一些不相關的檔案也加進去。
 
 
之後輸入查詢指令$ git status，可以看到所有的檔案被加進去的記錄(綠色字體)。
 
 
再來要將加入的檔案commit上去，輸入 $ git commit -m "Add Test.rtf"，
 
 
接著就會看到檔案commit上去的記錄
 
 
接下來要將剛剛commit的檔案同步至遠端，輸入 $ git push 將訊息傳送上去。
 
 
然後回到遠端(請先重新整理網頁)你就會發現githut上多了一個Test.rtf囉!
 
 
l. 遠端修改README.md檔並同步至本地端
README.md是githut的一個使用說明記錄檔的功能。
我們可以直接在遠端上修改它，點入README.md
 
 
點選編輯並新增一個file名稱，這裡要測試git pull的動作(從遠端同步至本地端)，所以這裡命名為Test pull，下方commit changes的資訊可不填寫，直接用預設的，然後按下「commit changes」鈕。
 
 
 
 
 
commit完成後，回到githut的RubyOnRailsTest底下，點進commit記錄，就會看到在遠端githut上面多了Update README.md的記錄。
 
 
 
所以現在遠端的版本比本地端新，我們要做的是將遠端的版本同步(pull)至本地端，回到bash，輸入 $ git pull，這時會看到遠端的版本同步本地端的資訊。
 
 
 
輸入 $ git log，可查詢到剛剛Update README.md的記錄。
 
 
 
如此一來，從githut的註冊流程，到一些基本指令的操作就這樣完成囉!!
記得所有的commit 要update 遠端的話 一定要做push的動作喔!!
但是不用每次commit都push, push這動作會一次上傳所有還沒push過的commit。
 
//==============================================
所謂的remote 口語化解釋就是, 你下載下來的是"一般"的git repo，你可以"自己"commit , add ,rm 之類的使用 ，但今天如果是你想要同步兩組repo, 這時候可能就必須要用push 和 pull指令。
 
用情境來解釋,假設有兩組repo, 名稱分別叫project 和 backup，project 就是一直在做的，backup 就是遠端備份，所以你平常都是在project底下做, add, rm, commit 等指令，等你告一個段落後, 會想要一次遠端備份, 避免硬碟壞軌之類的，這時候你就會在project底下 執行$ git push，這個指令會update 所有新的commit 到 backup底下。
 
假設因為某種原因, 你的project 裡面的比 backup舊了，你不需要整個刪掉重新$ git clone,你只需要在project 底下執行,$ git pull，就會從backup 將所有新的commit 更新到project底下。
 
當然前提是 project所設定的remote 對象必須要是該backup，本文不打算說明如何設定remote。

